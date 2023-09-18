# More Initial Conditions Review and Beginning Literature Dive

### Goals From Last Meeting:
1. Vacation :)
2. Discussed more effective data-visualization for ICs using property-property plots, showing casts locations, etc.
3. Review MacCready et al. (2021) for starting structured literature review.

### Completed Goals:
1. Vacation :)
2. Some improved data viz for ICs.
3. Literature list + prioritization.

---

## 2017 Initial Conditions for LO Run Review

Since last meeting (and since being unable to attend last week due to travel chaos), I was able to implement a first pass of the 2017 LO initial conditions using observational data. Preliminary review deemed them not totally unreasonable and usable for starting the run; however, I'd still like to review it here! I modified the following variables for initial conditions based on data availability:
1. Temperature
2. Salinity
3. Oxygen
4. NO3 (calculated as NO3 + NO2 measured)
5. NH4
6. chlorophyll
7. TIC (assumed to be DIC measured)
8. alkalinity

In theory, I should have not changed anything outside of the Salish Sea region, and regions where there was no data availability should default to use the original data field (I'm simply overwriting with new VFC-type data filling). There are some areas where bio variables seem to look different, even though there are now bio casts present. I think this is largely due to a dependence on these bio fields on salinity or temperature, which may already be set by different casts in an "apply CTD casts to initial conditions" step. I'll have to look into this further. **Note:** This is using two months of cast on either side of a selected date (January 1, 2017 in this case) and I'm using similar "minimum casts" condition as I do in volume calculations, such as:
1. Saanich Inlet casts can't count for more than 10% of the Strait of Georgia domain.
2. A single cast can't account for more than 60% of a region.

The following animations show the results of the initial conditions for each variable I modified for each layer, with "original" and "new" shown side by side.

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/504c08ea-c0d1-4e53-a569-535bf7e6812b
" controls="controls" style="max-width: 800px;"></video><br>Fig 1. 2017 salt IC method comparison.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c286b9b6-4d60-459d-8c95-a42600e582e4" controls="controls" style="max-width: 800px;"></video><br>Fig 2. 2017 temperature IC method comparison.</p><br>


<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/a53e632a-e782-4423-b5ae-a79a568f7a42
" controls="controls" style="max-width: 800px;"></video><br>Fig 3. 2017 DO IC method comparison.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d97081b8-efcb-433e-a1d1-9f4b2adcd80e
" controls="controls" style="max-width: 800px;"></video><br>Fig 4. 2017 NO3 IC method comparison.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/94b6f532-b59e-460e-a61d-559a2d0c2bf1" controls="controls" style="max-width: 800px;"></video><br>Fig 5. 2017 NH4 IC method comparison.</p><br>

<p style="text-align:center;"><video
src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/00f02125-f681-4bd5-83a3-fd95be7a356c" controls="controls" style="max-width: 800px;"></video><br>Fig 6. 2017 chlorophyll IC method comparison.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c394c3b7-1ec7-4e31-9de5-7829e7f325e1
" controls="controls" style="max-width: 800px;"></video><br>Fig 7. 2017 TIC IC method comparison.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/49ae5b4b-07ed-4847-9e4e-fdea470f8cf5" controls="controls" style="max-width: 800px;"></video><br>Fig 8. 2017 alkalinity IC method comparison.</p><br>

Next steps for this initial conditions include:
1. Confirming that there are no bugs in start-up with TRAPS 2017 run.
2. Confirm there are no weird boundary issues occuring given the overwrite with new VFC method in the Salish Sea.
3. Confirm if the initial conditions are realistic (perhaps separate bio variables' salinity dependence?).
4. Refactor code to be nice and usable in LO main.

---

## Literature Review Planning

### Hood Canal

A few weeks ago, we discussed some trends we're seeing in temperature, salinity, and DO in various Puget Sound regions. Specifically, zooming in on Puget Sound seems prudent since it is producing the lowest DO measured and has some interesting, non-intuitive trends both in time series and T-S end-member analysis. Alex suggested a literature review of Hood Canal hydrodynamics to start answering questions such as: What are the key processes influencing Hood Canal temperature and salinity? How does this impact Hood Canal DO? Specifically, sill morphodynamics and freshwater influx likely have varying spatiotemporal influence on T-S we observe via estuarine circulation. This effort will inform the next further Hood Canal data exploration.

### Salish Sea Indicators

Another area of literature review that will inform the efforts in Paper 1 is various physical indicators that may impact trends we observe in the Salish Sea (particularly in DO). We discussed terms like the "Blob" and "Pacific Decadal Oscillation" capture a swath of covarying indicators; Alex recommended looking into sources that explore these indicators. Exploring what's out there and what's published already will allow me to pursue these correlations in data exploration and in my Paper 1 effort.

For both of these review efforts, I have running lists when I find good sources. I need to prioritize reading on a schedule and perhaps holding myself to deadlines and deliverables for the reading I do...

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
* August 21 - September 15, 2023 remote work
  * Days Off: Thursday, 9/5 - Friday 9/6...maybe all next week? :) (I can do definitely do some hours but will have a less consistent schedule.)
  * Excused from next week's meeting!
* OSM abstracts due 9/13...

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. Organize literature - Endnote or Bibtex.
3. CTD/bottle duplicate DO in ecology set - clean this in VFC (output not affected, only number of casts included).
4. Weird "1-cast = np.nan hyp_vol" issue comes up on 4/2017, 5/2019, and 6/2019. May be an averaging problem.
5. Data cleaning (1950 DO concentrations).
6. Averaging casts in same location.
7. Write VFC-specific command-line tags.
8. Weighted averages are not doing a linear interpolation between gridcell depths yet.
9. Averages below threshold depth are only written for obs data so far.
10. Write plotting functions.

### Looking Ahead:
1. ORCA buoys - incorporate this into trend analysis ASAP.
2. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
3. VFC for Aurora's LO output.
4. Readings with Aurora (e.g., Santana & Shull, Sutton et al.).
5. Reach out to Greg Johnson!
6. OSM abstracts???

### Goals For This Week:

