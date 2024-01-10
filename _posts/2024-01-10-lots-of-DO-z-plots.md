# Lots of Plots - Temporal/Regional Exploration of DO and Sampling Depth

### Goals From Last Meeting:
1. Use number of casts as DOF for confidence intervals.
2. Explore finer depth-binning.
3. Create seasonal and yearly averages for DO/sampling depth exploration.
4. Explore source/data type correlation with sampling depth.
5. Create average DO cast profiles for time periods/seasons.
6. Lots of plots!
   
### Completed Goals:
1. Used number of casts as DOF for confidence intervals.
2. Explored finer depth-binning.
3. Created seasonal and yearly averages for DO/sampling depth exploration.
4. Explored source/data type correlation with sampling depth.
5. Created average DO cast profiles for time periods/seasons.
6. Lots of plots!
   
---

## Number of Casts as DOF for Confidence Intervals and Finer Depth-Binning

**I am only going to show Hood Canal plots in this blog - it would be way too long otherwise! I do have all other plots available to chat about during our meeting! Honestly there's a lot to see here. This data lion has bitten off more than she can chew for one blog post!**

First, I have updated my scripts to use the number of casts as degrees-of-freedom for the confidence intervals (in lieu of using total data points previously). This will give us a better idea of the variation in time of averaged values, in lieu of using number of data points (which may be oversampled in depth by CTDs!). Yay!

Second, I increased the depth-resolution by creating finer bin sizes (10 total), as follows:
* <5m
* 5-10m
* 10-15m
* 15-30m
* 30-50m
* 50-75m
* 75-100m
* 100-150m
* 150-200m
* \>200m

This helps us see trends in more specific portions of the water column, which are likely to be more homogenous than larger bins. Binning can only get us so far, but this is a useful first pass!

I've selected a few bins to show (there are many more plots that I'm not showing!):

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/41bc6146-5105-4fcc-a869-2f5bce67381a" width="800"/><br>Fig 1. Hood Canal SA/CT/DO monthly average time series <5m depth.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/84c99886-2ed0-41d5-adb3-ad86f78db007" width="800"/><br>Fig 2. Hood Canal SA/CT/DO monthly average time series 30-50m depth.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f1bf4c03-1265-4652-b40d-9887773cc0fe" width="800"/><br>Fig 3. Hood Canal SA/CT/DO monthly average time series 150-200m depth.</p><br>

We can see that in the surface bin, there is substantially more variation than in deeper bins. This makes sense for a couple of reasons: a) there are more samples in shallower regions since not all casts go to the maximum depth and b) the surface is more bioactive and subject to environmental forcing like wind-driven mixing. We expect a lot more variation, and we're seeing it!

There's a lot to parse, but there isn't an apparent downward trend in surface DO. There is a downward trend in surface salinity over time, however! **Look into further...**

However, in the 30-50m range, there appears to be some decrease over time (also a wickedly large CI - **to investigate further***).

At depth, there is less data, but it's less variable over all. We do not observe a downward trend here readily.

---

## Seasonal Averaging!

Previously, I've focused heavily on monthly averages. Now, I'm recreating the same plots as above with seasonal averages! Before, I showed similar plots that used monthly averages but selected for specific seasons. The following represent true thre-month averages, broken out by season.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/903dfcbb-5531-4360-8b8f-4e28b1a27878" width="800"/><br>Fig 4. Hood Canal SA/CT/DO seasonal average time series <5m depth.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d018196c-5af3-4ba0-a4b2-96ae602d1592" width="800"/><br>Fig 5. Hood Canal SA/CT/DO seasonal average time series 30-50m depth.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d6eb391f-807f-4400-b726-30d5576d32e2" width="800"/><br>Fig 6. Hood Canal SA/CT/DO seasonal average time series 150-200m depth.</p><br>

*Data visualizations under construction! Please excuse my tiny fonts and improper axes :D.*

Both by creating seasonal averages and visualizing data by season separately, we see some more interesting trends. Importantly, lowest DO is observed during fall. Unlike the monthly visualizations above that were not separated by season, we can see a surface trend of decreasing SA and increasing CT over time, in each season. However, DO is not observed to be decreasing overtime in any season; in fact, fall DO looks to be increasing at the surface!

However, at mid-depth, we see that although SA is fairly constant overtime, CT appears to be slightly increasing, and DO appears to be decreasing. At depth, subtle warming is observed.

---

## Yearly Averaging!

I can also look at the same data but with yearly averages. This doesn't really help elucidate more granular trends, but is a useful way to look quickly at interannual variation.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d929ada7-77b3-4f1a-b67e-7eebab317449" width="800"/><br>Fig 7. Hood Canal SA/CT/DO monthly average time series <5m depth.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/b440049c-d126-4c6d-83b9-d26682a5a70e" width="800"/><br>Fig 8. Hood Canal SA/CT/DO seasonal average time series 30-50m depth.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/628f02f5-92e6-4033-b615-863bd53ed283" width="800"/><br>Fig 9. Hood Canal SA/CT/DO seasonal average time series 150-200m depth.</p><br>

There are significant confidence intervals that are fairly consistent in size (likely due to seasonal variation inherent in an annual average). These trends reflect what was observed in the the seasonal breakout above, but on even less granular timescales.

---

## Exploring Sampling Depth Variation

Changing gears slightly - now I'm exploring sampling depth for DO over time. Previously, I'd used some pretty thich depth-bins and hadn't looked at different temporal resolution or time periods. The following plots show monthly, seasonal, and yearly sampling depth averages for each depth bin (defined above). Then, I've plotted the mean depth PER CAST, also binned as above. Plotting these against each other, I can see how central each mean is within the depth bin.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0c4baeeb-343c-4511-b718-952a99583d20" width="800"/><br>Fig 10. Hood Canal monthly average DO sampling depth and all binned depth averages (binned), colored by depth bin.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/22426840-a531-43a0-b90e-fa344bf8de33" width="800"/><br>Fig 11. Hood Canal seasonal average DO sampling depth and all binned depth averages (binned), colored by depth bin.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/14cf2b86-fa1e-4bdb-96f9-e64bb7c86c95" width="800"/><br>Fig 12. Hood Canal yearly average DO sampling depth and all binned depth averages (binned), colored by depth bin.</p><br>

There is significantly more variation when taking monthly averages (as makes sense). But if we look within some groups of years (pre-1945, post-1995, and in between, say), we can see that they tend towards fairly similar values that do not change much within those broader time periods. For clarity, I'll continue this discussion using seasonal depth averages.

Now, the following plots show the same information, but broken out by season to observe any seasonal trends in sampling depth for DO.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/b921fa6d-b13e-43f1-8c07-32056924788c" width="800"/><br>Fig 13. Hood Canal seasonal average DO sampling depth and all binned depth averages (binned), colored by season.</p><br>

There is not significant interseasonal variation, in my opinion! This consistency is helpful, but also requires further analysis.

Looking at slightly more information, the seasonal breakout is now colored by data source (or, sampling agency):

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f318d2d0-ea96-4114-9219-15617418e0d4" width="800"/><br>Fig 14. Hood Canal seasonal average DO sampling depth and all binned depth averages (binned), colored by source.</p><br>

Other than temporal variability, there is not a particular skew of one data source toward certain depth ranges. Again, this requires further analysis.

---

## Average Casts During Time Periods/Seasons

Finally, another ask from last week was to create DO vs. Z profiles from data and create binned averages PER season and time period (somewhat of a "climatological cast". This follows on from above, observing that mean sampling depth is consistent within year groupings, but not perfectly aligned between them. I've defined some time periods as follows:
* Pre-1945
* 1945-1980
* 1980-1995
* 1995-On

Creating these profiles will allow us to see where sampling depth and DO variation occurs between samples and if adjustments for sampling depth are necessary when comparing DO data. The following plots show average casts and all data points for each time period and season. Note there is no data in Hood Canal between 1980 and 1995.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/09d8ef6d-df78-495a-9513-f4c76994da41" width="800"/><br>Fig 12. Hood Canal DO vs. depth for all seasons pre-1945; all data is plotted and average in 1-m bins.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/61d908e0-4981-4903-bbfc-9eadc09fd804" width="800"/><br>Fig 13. Hood Canal DO vs. depth for all seasons 1945-1980; all data is plotted and average in 1-m bins.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/9986ad2d-bcf0-4fed-bcfa-2bd77f6f61de" width="800"/><br>Fig 14. Hood Canal DO vs. depth for all seasons 1995-on; all data is plotted and average in 1-m bins.</p><br>

Clearly there is way more high-resolution data in modern times which tends to smooth out the average casts. In all cases, the "widest" casts (further from mean) seem to be from the earliest years within the time period. We note the importance of using seasonal breakouts for these average casts, as there is significant variation between seasonal average casts.

**A regression-type fit may be more appropriate than this average binning for smoothness of average casts!)**

These are somewhat hard to compare how I've presented them. The key finding here will be the changes in these average casts in different time periods, and if they can be used to "correct" sampled data based on depth so as to allow depth-consistent comparisons of DO measurements.

---

## Miscellaneous

Next steps:
* Regional analyses like above for Hood Canal
* Interregional comparison of sampling depths!!!
* Explore large CI data points
* Clean up plotting - how to show this succinctly?

Thoughts for posterity:
* Review Collias publications for early data context.
* Zooming in on Hood Canal trends (most apparent change in CT/SA/DO over time) - focus on hypotheses for trends here, build tools for whole system analysis.
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)
* Skagit data


---

## Planning

Last week, we chatted about Ocean Sciences and the direction for Paper 1. Here's some summary:

* 2/22: Ocean Sciences Poster
  * Focus on Puget Sound observed DO/CT/SA trends and uncertainty
    * Exclude King County data, ORCA buoys, Whidbey mooring data for now (mooring data could provide short-time scale analysis/later hypothesis testing)
    * Analysis of correlation with physical environmental data (like river flow)
    * Potentially use volume-weighted averages?
  * **Main focus through February**

* Spring/Summer 2023: Paper 1
  * Continuation of Ocean Sciences poster...
    * Long term trends in Puget Sound DO (similar to Riche et al. 2014, Moore et al. 2008)
    * Emerging story of changing atmospheric and environmental conditions
      * Low river flow leads to less efficient exchange flow and longer residence times may be associated with lower DO
        * Less stratified, saltier over time, warmer over time?
  * Some collaboration with Stefano and PSI - but largely take the lead and time I need to write this paper. Yay!
  * Presentations at the end of summer to/with PSI?

* Spring 2023: General Exam (Thesis Proposal)
  * Part 1: Paper 1 content!
  * Part 2: ??? specific regional analyses
  * Since I already have a Masters (albeit in a different group), how many "chapters" are warranted? I've heard two for pre-existing MSCEs...
  * Where does Penn Cove stuff fit? Learning how to run LO?
  * Incorporating reading...especially Riche et al. 2014 and Moore and Mantua 2008 (likely reading bulk **after** Ocean Sciences).
  * **Need to assemble committee! Evidently Michelle can GSR**
  * **Firmer grasp of timeline after Ocean Sciences**

---

## Bookkeeping 
* Ocean Sciences: 2/18/-2/23
  * Need to register! **Should I sign up for the Student Presentation Evaluation Program (SPEP)? Feedback, but can't see other posters during session...**
  * Booked: flights, accommodations - **need to reimburse**
* New computer! :)
* PECS - on the radar

---

### Looking Ahead:
1. ORCA buoys - incorporate this into trend analysis ASAP.
2. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
3. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
4. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
5. Penn Cove nitrogen budget with WWU + Penn Cove nested model...
6. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. See next data analysis steps above.
