# New Depth Thresholds and Yearly Averages for DO Concentration

### Goals From Last Meeting:
1. Continue data exploration - individual seasonal plots, yearly averages, new depth threshold based on percentage of water column.
2. Continue data cleaning - KC/Whidbey.
3. High priority - initial conditions for 2017 run with TRAPS (work with Aurora).

### Completed Goals:
1. Seasonal breakouts plotted per region.
2. Redid depth-averaging with bottom 20% of water column.
3. Yearly averages overlaid.

---

## Data Exploration Continued

Over the last week, I sent intermediate progress in data cleaning following last week's feedback from the weekly meeting. First, I recalculated the bottom averages using the bottom 20% of the water column, so as to capture shallower regions such as Lynch Cove. Then, I broke out the scatter plots to show trends in individual seasons, as discussed. For brevity, I'm just showing the average in the bottom 20% of the water column from observations. Again, these are calculated monthly.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/1348c4bb-4f06-44dd-95bb-5a658bf4752c" width="800"/><br>Fig 1. Salish Sea regional bottom 20% of water column DO average.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/7dc35a6c-55b2-4624-803a-c9c820ff1601" width="800"/><br>Fig 2. Puget Sound regional bottom 20% of water column DO average.</p><br>

Next, I overlaid the yearly averages on seasonal averages (in the bottom 20% of the water column), shown again broken out by season.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/5ddd7672-8bae-4f34-8693-6b7709868c07" width="800"/><br>Fig 3. Strait of Juan de Fuca bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/374dd824-b68e-44ed-ab2c-637f47f2e149" width="800"/><br>Fig 4. Strait of Georgia bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/32ab504c-7fea-4af5-8949-dc0dff85182a" width="800"/><br>Fig 5. Puget Sound bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/9330549d-522c-4898-a170-2f2349a8f6a1" width="800"/><br>Fig 6. Admiraly Inlet bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/b845d348-647d-469f-b9b4-9202d501dd75" width="800"/><br>Fig 7. South Sound bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3e65179e-d2fb-4357-9b90-43202e284049" width="800"/><br>Fig 8. Main Basin bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4c430ade-32ff-4334-9eb8-d1d693171040" width="800"/><br>Fig 9. Whidbey Basin bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/885284bb-11bf-4ed5-b23a-cce239ff4065" width="800"/><br>Fig 10. Hood Canal bottom 20% of water column DO average; seasonal and yearly temporal averages.</p><br>

In some cases, such as Main Basin, there is some downward trend observed. However, most areas do not show this a clear downward trend. There is a clear low in most regions during 2015, which was a "Blob" year. I'm excited to plot these against environmental indicators to get some notion of what may correlate with these trends.

----

## KC Data Cleaning and 2017 Initial Conditions Using Observational Data

This is the second week of not too much progress on this data cleaning front (nor the added initial conditions effort) - I need to figure out how to parallelize data exploration and data engineering efforts. I have reviewed King County's email clarifying data questions and will incorporate their responses into getting KC's dataset clean and usable.

For the initial conditions effort, I have explored the files at LO/forcing. The output format for initial condition files seems to make sense and a lot of the structure using CTDs to extrapolate and infill data is similar to my VFC method.

However, I have a few questions:
1. What's most current? ocn0 or ocn00?
2. Should I prioritize cleaning KC data to use with this method? Or write this method first?

**My goal is to have the highest priority item up and running this week, and then the next item completed the following week.**

*Running list of other data sets I want to include:*
* Strait of Georgia Data Centre (https://sogdatacentre.ca/atlas/citscidata/) - other than DFO.
* Collias (when Parker has cleaned it).
* ORCA buoys

---

## Bookkeeping 
* KC Quarterly Update - Thursday, August 17, 2023
* August 21 - September 15, 2023 remote work...

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
3. KC meeting planning.
4. VFC for Aurora's LO output.
5. Readings with Aurora.
6. Reach out to Greg Johnson!

### Goals For This Week:
1. Initial conditions for 2017 - high pri.
2. Plots with horizontal year average for DO, T, S.
3. Questions for Paper 1.
