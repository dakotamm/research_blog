# Average DO Concentrations, Seasonal Variation, and More

### Goals From Last Meeting:
1. Continue data exploration.
2. Continue data cleaning.

### Completed Goals:
1. Weighted average below a depth threshold, average below a depth threshold, and seasonal trends have been calculated and plotted.
2. Small bit of data cleaning!

---

## Data Exploration (Averages, Seasonal, etc.)

I've taken the last week to finally get some data exploration plots out (as was not quite prepared last week) and continue some trend exploration using different time frames. For the first set of plots, I have monthly time resolution for all parameters. I've created time series for hypoxic volume, sub-40m DO weighted average concentration, and sub-40m average concentration. I investigate the Strait of Georgia, Strait of Juan de Fuca, and Puget Sound in one set (Figure 1); then I investigate the different regions of Puget Sound (Figure 2); and finally I investigate just Whidbey Basin and Hood Canal (Figure 3). **Note:** Weighted average concentration is volume-weighted. It uses the same surface partitioning as VFC to find hypoxic volume, but it is *not* subject to provisions that filter data based on coverage condition (e.g., too few casts in one region).

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e99fa66e-ef41-4440-ad73-45253597f4a7" width="800"/><br>Fig 1. Regional monthly hypoxic volume, sub-40m weighted average concentration, and sub-40m average concentration in the Salish Sea since 1930.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4638dbff-b68d-4413-96bd-43e599c48e78" width="800"/><br>Fig 2. Regional monthly hypoxic volume, sub-40m weighted average concentration, and sub-40m average concentration in Puget Sound since 1999.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/eee5df79-03f2-495d-b4f9-7f026bb6e1d7" width="800"/><br>Fig 3. Regional monthly hypoxic volume, sub-40m weighted average concentration, and sub-40m average concentration in Whidbey Basin and Hood Canal since 1999.</p><br>

In all the plots, we note an obvious concentration of data points toward more recent years, as well as more casts (indicated by individual dot size) included in data points. Likely due to this fact, there is a large spread in oxygen concentration data even within a concentrated time period likely corresponding to seasonal variation. It is challenging, with current data availability, to discern a long-term upward or downward trend since 1930 in the Salish Sea in any region. However, the last two decades there is a discernable "peak" in DO concentrations occuring in approximately 2012, then a decrease of average DO over the last decade. This is likely similar to the trend reported in EPA reports (see: https://www.epa.gov/salish-sea/marine-water-quality#:~:text=Marine%20dissolved%20oxygen%20levels%20continue,areas%20in%20the%20Salish%20Sea.). Again, however, this trend does not appear to have a clear smoking-gun trend over the last 8 decades or so.

Next, I investigated the same three spatial breakouts (Figures 4, 5, and 6) using seasonal averaging. **For this case, I used an average parameter over seasons divided within one calendar year and averaged over the three months.** I did not rerun a VFC method to calculate this, mainly due to the issue of averaging casts that occur in the same location within a time window that I have not yet resolved. This is on my radar to solve but I haven't been able to do so yet. In either case, the seasonal time series are as follows:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/eb102ae4-340e-4db4-bd74-82a774881a99" width="800"/><br>Fig 4. Regional seasonal hypoxic volume, sub-40m weighted average concentration, and sub-40m average concentration in the Salish Sea since 1930.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/21a12cc3-763a-4783-8270-c67f2b958c8f" width="800"/><br>Fig 5. Regional seasonal hypoxic volume, sub-40m weighted average concentration, and sub-40m average concentration in Puget Sound since 1999.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/8e91cc43-296b-46cd-ac91-5fb6e6c6a197" width="800"/><br>Fig 6. Regional seasonal hypoxic volume, sub-40m weighted average concentration, and sub-40m average concentration in Whidbey Basin and Hood Canal since 1999.</p><br>

Despite searching for better built-in ways to represent seasonality, marker-differentiation was the best thing I came up with to represent seasonality in a time series. I may have to design my own plotting method to make these more readable... Either way, the same trends as the monthly breakout are readable. However, in order to understand the influence of seasonality better, I created bivariate plots to not only investigate seasonal variation but also other variable covariance. Following a similar spatial breakout as previous plots, Figures 7, 8, and 9 investigate several bivariate plots of important independent variables and calculated parameters.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/b5f8a508-f64a-46b4-a019-711f4410b709" width="800"/><br>Fig 7. Bivariate plots for regions in the Salish Sea.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/b9e3ced5-7d71-41f3-840a-21f1eb5faf58" width="800"/><br>Fig 8. Bivariate plots for regions in Puget Sound.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/a4d03779-f7e9-4797-9bdf-c554a9131234" width="800"/><br>Fig 9. Bivariate plots for Whidbey Basin and Hood Canal.</p><br>

These are kind of fun to look at, but also show a clear seasonal pattern as expected for DO-cycling. More investigation into these could be really cool!

I also plotted these using individual regions as an independent variable, as follows:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/eab88e86-42a2-4e12-8152-59c97fb32f35" width="800"/><br>Fig 10. Bivariate plots for regions in the Salish Sea with regions as independent variables.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0bac3fc8-c15f-46f1-b69e-84dd6ce4969d" width="800"/><br>Fig 11. Bivariate plots for regions in Puget Sound with regions as independent variables.</p><br>

I haven't spent too much timing combing these yet for trends, but I think these could help with extricating key analyses and analyzing variables independently.

----

## KC Data Cleaning

Since last week, I haven't made huge strides (I got sucked into data exploration!). I did, however, reach out to King County contacts to answer Jilian's and my questions about the dataset in general. Wrapping up a first pass and setting a meeting with Parker to discuss specifics is high priority for this week. I'm close!

Running list of other data sets I want to include:
* Strait of Georgia Data Centre (https://sogdatacentre.ca/atlas/citscidata/) - other than DFO.
* Collias (when Parker has cleaned it).
* ORCA buoys

---

## Bookkeeping 
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
10. Averages are only written as "below a threshold" versus within certain depth bins.
11. Write plotting functions.

### Looking Ahead:
1. Continue data exploration.
2. Finish KC data cleaning first pass - meet with Parker if necessary.
3. VFC for Aurora's LO output.
4. 
5. Readings with Aurora.
6. Reach out to Greg Johnson!

### Goals For This Week:
1. Continue data exploration.
2. Continue data cleaning.
