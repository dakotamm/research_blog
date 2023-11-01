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

***taylor debrief!!!



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

I can use these average casts to then fill the domain in the segment. In this case, the average casts have been used to fill DO fields in the model domain (useful both for calculated volumetric state variables and for initial conditions filling):




https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0bc926bd-2775-48c0-a970-e9cff01b31eb


***CAS7
***intelligently fill gaps
***conditions if there's too few or too shallow casts - currently using 20% depth condition
***bin size? does it matter?

### Toward 2013 Initial Conditions

data exploration ***

2012 dec casts and filling plots

***try more months


Last week I discussed a hurdle using TEF segments for VFC where despite checking through an averaging scheme, I had odd values (sometimes negative) for state variables (see previous post for more detail). This was due to the using np.empty() to create initialize a matrix, which uses random numbers to fill. Thanks Parker for finding this and helping me get through! Here's a plot of some variable filling in the Salish Sea that I was able to generate after my bug was squashed.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e667f659-f1e7-41b3-bde4-b26c16a965fe" width="400"/><br>Fig 1. Surface sigma layer DO fields [mg/L] using new VFC scheme with TEF segments.</p><br>


---

## KCWASH + Taylor Meeting Next Week

Next week, we plan to host Taylor Martin (KC) at our monthly meeting with the broader UW group (including Mike and Ben). We had initially stated that we wanted her to rehash her CEE seminar presentation from April. I'd like to assemble an agenda this week to send to her with all of our input! **What other goals should we discuss during this meeting with Taylor?**

---

## CEWA 565 Class Project Research Opportunity

For my data analysis in water sciences class, there will be a term project that is intended to put our "new" stats skills to use. We can use our own research, and I certainly intend to do so. I have a few ideas in terms of research questions that may fit the bill, but if there's something that would be more immediately important to the project (that's still the size of a class project), I'm happy to consider that. I'm thinking along the lines of:
1. Has bottom oxygen changed over time in Puget Sound/Salish Sea? (I'm thinking of the "declining trend" reported in the [2019 Salish Sea EPA Report](https://www.epa.gov/salish-sea/marine-water-quality#:~:text=Marine%20dissolved%20oxygen%20levels%20continue,areas%20in%20the%20Salish%20Sea.); I could perform some simple stats using all our data to understand if there's a difference in mean bottom DO before 2010 and after.)
2. Same as above, but hypoxic volume.
3. Pick an indicator (like rainfall, river flow) and determine covariance with a state variable like DO.

---

### Meta-Goals:

After soaring over these two hurdles, I remind us of some of the bigger goals this code architecture change will help me accomplish:
1. Create initial conditions based on observations for model runs that are more realistic than previous code architecture (excluded a lot of data areas given sparse resolution).
   * Spefically and additionally - create climatological initial conditions:
     * Perform the method for all "Decembers", say.
     * Perform the method for all years.
     * Weight the climatological "December" by statistics derived from interannual variations.
2. Apply to observational record and evaluate trends in volume-based state variables in a more systematic way than previous VFC architecture.
3. Nice, tidy, usable codebase :D.
4. (sort of goal) Confirm this all performs well compared to previous VFC architecture and observations.

Stay tuned...

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
* Taylor participating in group meeting on Wednesday 10/18.

---

### Looking Ahead:
1. Finish spatial averaging scheme in existing VFC method.
2. Create monthly and annual climatologies for gridded state variables.
3. ORCA buoys - incorporate this into trend analysis ASAP.
4. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
5. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
6. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/) Puget Sound Institute article Parker pointed toward me...)

### Goals For This Week:
1. Build code and initial first-pass of initial conditions for 2013 run.
2. Read new paper.
