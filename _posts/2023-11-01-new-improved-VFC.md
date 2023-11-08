# New and Improved VFC Spatial Averaging

### Goals From Last Meeting:
1. Build code and initial first-pass of initial conditions for 2013 run.
2. Read new paper.

### Completed Goals:
1. Code built!
2. Read Bianchi et al. (2010).
3. Met with Taylor and KCWASH 10/18 about KC data review.
4. Plugging along in class workload.

---

## New and Improved VFC Spatial Averaging

### Spatial Averaging Via Average Casts

Last time we met, my primary task was to improve the VFC spatial averaging. This is imperative for creating time series of volume-based data interpolated from observational data, as well as create initial conditions that will inform LO model runs, such as the important LO hind-cast starting in 2013 that we're gearing up to run.

Initially, my method of taking a cast and filling the LO domain was based on using first a 2D nearest-neighbor finding algorithm for **each** temporal and spatial period (usually, every month for every region), then filling each gridcell with data from the cast closest to its depth. While this allows a very granular approach and the "most optimal" spatial allocation, there were several significant drawbacks:
1. Every spatial partition may be different during each time period; this inhibits clear intercomparison between time periods.
2. There were several ad-hoc conditions that I created to prevent overfilling with oversampled data (e.g., avoiding the many casts in Saanich Inlet filling the Strait of Georgia with erroneously low DO give the relatively sparse sampling in the Strait of Georgia relative to Saanich Inlet).
3. Overlapping casts within the same time period would be overwritten and earlier data would be lost; this was a tricky problem to solve given the old architecture.
4. It was kinda klunky.

So we decided it was time to "kill my darling" and try a new method. This time, I've used OG TEF segments to partition the Salish Sea into regions, as follows:
* Northern Strait of Georgia
* Southern Strait of Georgia (including San Juan Islands)
* Strait of Juan de Fuca
* Main Basin (including Admiraly Inlet)
* Whidbey Basin
* Hood Canal
* South Sound (including Tacoma Narrows)

The new method does the following:
1. Partitions the domain into the above regions for a given time period (generally one month).
2. Uses every cast within this spatiotemporal partition is used to create a depth-binned *average* cast for each variable. To do this, I bin by depth (default is 1m bins), average each bin, and then interpolate.
3. Assigns values for each variable at gridcells as a function of their depths from the interpolated average casts.

Here are some average casts from September 2012 in Main Basin. The black lines indicate the average interpolated cast for each variable. Left arrows indicate CTD data; right arrows indicate bottle data.  **Note:** I'm using these variables since these are the variables Parker and I have discussed could be improved by using this method for initial conditions. Any observed state variables could be used with this method.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/67ef6c3e-b87f-4d8c-9756-dff17ae088bc" width="800"/><br>Fig 1. Average casts for selected state variables for Main Basin, September 2012.</p><br>

I want to point out the effectiveness of this method for controlling for extreme values, especially in Saanich Inlet. Note the "blue" cast trending toward anoxia that doesn't significantly impact the overall average. However, we should be wary of underestimating Saanich Inlet hypoxic volume in this case.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/40d0b2b5-acc8-402f-abab-2f20b1833373" width="800"/><br>Fig 2. Average casts for selected state variables for Southern Strait of Georgia, September 2012.</p><br>

I can use these average casts to then fill the whole domain with their respective values. In this case, the average casts have been used to fill DO fields in the model domain (useful both for calculated volumetric state variables and for initial conditions filling):

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0bc926bd-2775-48c0-a970-e9cff01b31eb" controls="controls" style="max-width: 600px;"></video><br>Fig 3. September 2012 DO [mg/L] in sigma layers.</p><br>

Exciting! September is an awesome test month since it has lots of casts, but not every month has the same spatial coverage. Importantly for initial conditions, December 2012 is missing values for DO in Northern Strait of Georgia and Whidbey Basin...

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/91241e90-d71f-4852-b95c-583236623d35
" controls="controls" style="max-width: 600px;"></video><br>Fig 4. December 2012 DO [mg/L] in sigma layers.</p><br>

...which brings me to a some items that still need some work:
1. We've alleviated a lot of the gappiness from previous VFC architecture by using large regional segments. To fill segments that are missing values, I could fill with the most adjacent segment, but that might be erroneous in some cases. Also a one-size-fits-all solution is unlikely to work here.
2. Currently, all of this work is developed using cas6. I have previously been able to fill initial conditions in cas7, but haven't tested this new method yet.
3. Currently I'm using a filter that casts must exceed 20% of water depth or greater in the cast location. This allowed me to circumvent a few interpolation bugs, namely: only (1) data point in a cast and cast depth less than the minimum bin size. Since these casts are likely either one-off surface samples or "failed" casts, I feel comfortable using this condition to exclude them from use in averaging casts.
4. I'm using 1m bin-sizes. Any reason for bigger/smaller?


### Toward 2013 Initial Conditions

To get effective initial conditions for 2013, we must evaluate the ability of this method to fill data in a reasonable and realistic way. At first pass, one could use December 2012 values for initial conditions (I can show plots here to illustrate this, but didn't include here for blog readability), but the data is spatially sparse and has limited nutrient, DIC, and alkalinity data. Parker has mentioned using a different model to fill DIC and alkalinity. To increase the spatial coverage across all variables, I can increase the temporal range to include more casts. To guide this work, I conducted a brief time series study of data availability, binned by month:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/adf37cbe-50d3-4ea2-810a-2cddfb629209" width="800"/><br>Fig 5. 2012 cast data availability - DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/465af8de-5f77-4696-ac0a-cf1ded31d7b3" width="800"/><br>Fig 6. 2012 cast data availability - temperature.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ee8b8c86-3a48-4169-8d31-d61ef56f9e20)" width="800"/><br>Fig 7. 2012 cast data availability - salinity.</p><br>


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/8bc33f89-a8e0-4603-aacc-0128f3556f8e" width="800"/><br>Fig 8. 2012 cast data availability - NO3.</p><br>


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/2048948b-73ba-4bca-a80a-99d167f2311b" width="800"/><br>Fig 5. 2012 cast data availability - NH4.</p><br>

Here we see some data with increased availability during summer months. Expanding the time range to 4 or 6 months before the start of the 2013 run may allow for more cast data, though it may not perfectly represent winter conditions.

Alternatively, we'd discussed a climatological approach, where I gain understanding of interannual variability of state variables, and can apply a modifier to a climatological "December" condition based on this interannual variability. I need more time to noodle on the best way to do this, given that December 2012 is not uncommon in terms of data coverage.

Next week, I'd like to have some initial conditions options ready to discuss!

---

## KCWASH + Taylor Meeting Debrief

Two weeks ago, we got to meet with Taylor from KC about her data analysis that had been in part presented at the CEE 500 seminar in April. What a cool learning experience! Not only is it validating to see some trends I've discerned be reflected in King County's dataset, but it's excellent to learn a bit about their analysis and statistical techniques. It pairs well with CEWA 565 (Data Analysis in Water Sciences), which is very statistics-focused. I'm excited to bring the stats I'm learning and into my own data analysis.

Also, it was great to get an update regarding Whidbey Basin data collection from KC, though it's a bummer that summer sampling frequency will decrease. I'd like to prioritize incorporating KC data into our LO database soon, and taking a look at mooring data in more depth (including ORCA).

I also appreciate the shout to get me out on a cruise! Finger crossed to make that happen at some point.

---

## Questions Toward Paper 1

Leaving this on here for posterity:

1. Is there an observable multi-decadal trend in DO throughout the whole Salish Sea?
   * So far, we've seen that there is really sparse data (in current datasets) before the 2000s. With this data, we can't really make out an upward or downward trend in the Salish Sea as whole, or in the Strait of Georgia, Strait of Juan de Fuca, and Puget Sound as a whole.
2. Are there observable multi-decadal trends in DO throughout different regions? How do regions compare and contrast in DO trends?
   * We DO see some variation since 2000; however, the trend is increasing DO peaking at 2012 and then a decrease. Some regions seem to show a slight decline since 1999 (like South Sound) and some regions show a "mountain" pattern (like Hood Canal).
3. Does DO co-vary with temperature, salinity, NO3, etc.? What are the most significant predictors of DO, if there are any?
4. What's the correlation between environmental indicators and events (i.e., the Blob, PDO, ENSO) that correlate with these trends?
5. Are there significant events that warrant further study, like the Blob?
   * 2015 seems less spicy than anticipated so maybe!

---

## Bookkeeping 
* Vacation: 12/18-12/22

---

### Looking Ahead:
1. Create monthly and annual climatologies for gridded state variables.
2. ORCA buoys - incorporate this into trend analysis ASAP.
3. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
4. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
5. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/) Puget Sound Institute article Parker pointed toward me...)

### Goals For This Week:
1. Finish incorporating initial conditions!
