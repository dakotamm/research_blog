# Initial Conditions Progress and Temperature/Salinity Exploration

### Goals From Last Meeting:
1. Continue data exploration - individual seasonal plots, yearly averages, new depth threshold based on percentage of water column.
2. Continue data cleaning - KC/Whidbey.
3. High priority - initial conditions for 2017 run with TRAPS (work with Aurora).

### Completed Goals:
1. Seasonal breakouts plotted per region.
2. Redid depth-averaging with bottom 20% of water column.
3. Yearly averages overlaid.

---

## 2017 Initial Conditions Using Observational Data

This week has largely been focused on getting initial conditions for 2017 LO with TRAPS up and running. I'm close!

A current blocker for using the new cas7 grid is being able to segment the domain. While there are a few ways I could tackle this, the way that requires the least change to my existing methods includes using the same segments as indicated in LO/extract/tef/flux_fun. These segments would align with the delineation I've had in cas6. Talking to Parker, it seems the problem is likely caused by the addition of the Swinomish Channel into cas7, which requires a different bounding for Strait of Georgia segments.

Another question I have is how to handle the domain outside of the Salish Sea (which we've agreed is outside of my initialization scope using my interpolation methods from VFC). I'll need to consider how it is currently handled (set by Hycom) and how to not interfere with that process.

---

## Data Exploration Continued

Following feedback from last week and given effort put into the initial conditions effort, I have only a few plots. I've plotted the bottom 20% of cast average for DO, temperature, and salinity for Puget Sound regions with seasonal averages and then a horizontal line indicating the full time series average. There are many ways to visualize this, but this is another attempt! 


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3e3c8885-d8df-41c8-b5c8-86229cef3e2e" width="800"/><br>Fig 1. Main Basin regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/db47510a-4342-4bf0-9bf5-0ac312a1d4af" width="800"/><br>Fig 1. Admiralty Inlet regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3e3c8885-d8df-41c8-b5c8-86229cef3e2e" width="800"/><br>Fig 1. South Sound regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ebd2dd04-09c9-440a-9eab-2351e2ebe8af" width="800"/><br>Fig 1. Whidbey Basin regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/dc130c08-7255-4249-938d-39a8ed272297" width="800"/><br>Fig 1. Hood Canal regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

There are some interesting trends to dissect here! The biggest one is that bottom low temperature and high salinity correlate with the low DO found in 2015, which seems to be a standout year (and a Blob year). This is likely due to highly stratified conditions given the warm surface water...but certainly warrants further study and discussion. 

---

## Questions Toward Paper 1

From last week, I was asked to make my data exploration a little more honed via asserting questions that I might seek to answer in my first paper, which is helpful! So here's my first hack:

1. Is there an observable multi-decadal trend in DO throughout the whole Salish Sea?
   * So far, we've seen that there is really sparse data (in current datasets) before the 2000s. With this data, we can't really make out an upward or downward trend in the Salish Sea as whole, or in the Strait of Georgia, Strait of Juan de Fuca, and Puget Sound as a whole.
2. Are there observable multi-decadal trends in DO throughout different regions? How do regions compare and contrast in DO trends?
   * We DO see some variation since 2000; however, the trend is increasing DO peaking at 2012 and then a decrease reaching a low during 2015 (Blob year). Some regions seem to show a slight decline since 1999 (like South Sound) and some regions show a "mountain" pattern (like Hood Canal).
3. Does DO co-vary with temperature, salinity, NO3, etc.? What are the most significant predictors of DO, if there are any?
4. What's the correlation between environmental indicators and events (i.e., the Blob, PDO, ENSO) that correlate with these trends?
5. Are there significant events that warrant further study, like the Blob?
   * 2015 seems to be a spicy year - so maybe!

---

## Bookkeeping 
* KC Quarterly Update - Thursday, August 17, 2023
* August 21 - September 15, 2023 remote work

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. Organize literature - Endnote?
3. CTD/bottle duplicate DO in ecology set - clean this in VFC (output not affected, only number of casts included).
4. Weird "1-cast = np.nan hyp_vol" issue comes up on 4/2017, 5/2019, and 6/2019. May be an averaging problem.
5. Data cleaning (1950 DO concentrations).
6. Averaging casts in same location.
7. Write VFC-specific command-line tags.
8. Weighted averages are not doing a linear interpolation between gridcell depths yet.
9. Averages below threshold depth are only written for obs data so far.
10. Write plotting functions.

### Looking Ahead:
1. Initial conditions for 2017 by end of this week.
2. Finish KC data cleaning first pass - meet with Parker if necessary.
3. KC meeting planning - draft by end of week 8/11.
4. VFC for Aurora's LO output.
5. Readings with Aurora.
6. Reach out to Greg Johnson!

### Goals For This Week:
1. Initial conditions for 2017 - high pri.
2. Plots with horizontal year average for DO, T, S.
3. Questions for Paper 1.
