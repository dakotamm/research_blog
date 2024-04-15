# More New KC Data and Further General Scoping

### Goals From Last Meeting:
1. Bring in new KC CTD data from Greg at KC.
2. Summarize Penn Cove scope feasibility.
3. Summarize decadal resolution from all available KC data.
4. Schedule meeting with Taylor about Whidbey scope feasability if necessary after this meeting.
5. Planning/writing general exam.
6. Schedule General Exam officially.
   
### Completed Goals:
1. Brought in new KC CTD data from Greg at KC - follow up with Taylor for additional data chunk...
2. Summarized Penn Cove scope feasibility.
3. Summarized decadal resolution from all available KC data.
5. Planning/writing general exam ongoing.
6. Schedule General Exam with committee - need to formally schedule with CEE.

---

## More New KC Data

This week, I brought in all the new QCed CTD data that Greg Ikeda sent via Dropbox file request on 4/8/2024. It's cool to finally have access to this. Now all the new sources are as follows:

1. Taylor's "old KC site" bottle data (1965-2000)
2. KC's non-QCed bottle data (1965-present)
3. KC's non-QCed Whidbey Basin CTD data (2022-present)
4. KC's QCed CTD data excluding Whidbey Basin (1998-present)

I've processed this using a similar process to other data sources in the LO ecosystem. All of this is available on my LO_user and I can effort cleaning this for use in LO as a whole if that is desired.

Note: I have plots for every decade, year, season, and variable for all of this data. Plots show location and values colored by sampling agency and data type.

---

## Penn Cove Feasibility Assessment

In planning for my General Exam, scoping the feasibility of a Chapter 3 involving Penn Cove has been really important and has taken some time to realize. Last week, Alex and I discussed doing a spatial and temporal quick dive into KC's 2022-2024 monitoring data in Whidbey Basin. This would then inform whether or not it makes sense for me to dive into the specific mechanisms at play in these shallow areas that seem to be highlighted as hypoxia hotspots in the Salish Sea Model (and to some extent in LO as well). Given the lack of long-term data in these areas, a high-resolution model (like Jilian's Hood Canal nested model) could be used to specifically target Penn Cove as an example for important mechanisms for hypoxia in these regions.

First, I looked at the available CTD sampling that KC has conducted since 2022. KC has 9 sites in Whidbey Basin, with 4 in and around Whidbey Basin. The sites are as follows:
* SARATOGARP (outside of Penn Cove in Saratoga Pass)
* PENNCOVEENT (at the mouth of Penn Cove)
* PENNCOVEECW (midlength of Penn Cove, shallow and nearshore)
* PENNCOVEWEST (at the head of Penn Cove)

I'll present all four sites, but the most comparable sites exclude PENNCOVECW given its shallowness! Note for the following figures I'm only filtering out erroneous negative values (no other filtering applied).

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4c6ff27a-53a2-4b39-b6e1-6cd6754c9a30" width="800"/><br>Fig 1. Time series of sampled variables at KC CTD site SARATOGARP.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/bb447235-cdb5-4460-8805-69ca21719997" width="800"/><br>Fig 2. Time series of sampled variables at KC CTD site PENNCOVEENT.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/dc934bf2-4385-4f2f-bbc6-170e7b3e081b" width="800"/><br>Fig 3. Time series of sampled variables at KC CTD site PENNCOVEWEST.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ed3f032b-2e3b-4f24-8cae-fb4fc12cd72c" width="800"/><br>Fig 4. Time series of sampled variables at KC CTD site PENNCOVECW.</p><br>

Some quick observations from the four sites:
* We can see some clear seasonal patterns, but not a ton of interannual variation. It seems like both years have similar magnitudes of DO change seasonally. These lag chlorophyll maxima. NO3 depletion lags chlorophyll maxima as well.
* Across the four sites, there is similar temperature time series except for one potential outlier in the Saratoga Pass site. The shallowest site does see the highest maximum temperature.
* At all the sites, there is a similar pattern for max chlorophyll in time, with 2022 having more sustained high chlorophyll levels. However, DO does not seem to be lower in 2022...
* Outside of Penn Cove, NO3 maxima are higher and show less variability despite similar chlorophyll variability across sites. Additionally, DO minima are lower and less variable, but do not show hypoxia. Finally, lower salinity minima are observed.
* Comparing the head and the mouth of Penn Cove - both show hypoxia develop. The head site has more variability in DO with lower minima. Hypoxic development at the head leads hypoxic development at the mouth. At the head, there is an increase above hypoxic levels in October 2022, surrounded by two months of severely low DO. This rebound is not evident at the mouth of Penn Cove.
* The shallowest site in the middle of Penn Cove does not development of hypoxia! However, it does show lower chlorophyll peaks in 2023, corresponding with higher DO.
* At all sites, there is not a visually apparent annual-to-decadal trend in any variable.

Based on some email correspondence with Alex, we think this could be a good evaluation dataset for a nested model and a promising Chapter 3 focused on Penn Cove drivers of hypoxia. Perhaps I could work closely with Jilian on this model development and then perform sensitivity analysis for various interannual drivers (e.g., Skagit flow, temperature, wind). What could be challenging is incorporating nutrients...if it's a nested model, could I incorporate boundary conditions based on Aurora's with and without anthropogenic nutrients? Would a model of this shallow area require further work on benthic processes and fluxes? Does this work with WWU field observation thoughts in Penn Cove?

---

## Decadal-to-Annual Resolution in New Data

For Paper 1 (and Chapter 1/2 of my General Exam), I will focus heavily on decadal/annual trends in observations. What we've encountered as a primary difficulty is lack of temporal and spatial resolution to our data. In particular, it's hard to get time series extending through the entire timerange (1930s onward) in specific locations. The biggest dearth of data is the 70s-90s, especially for DO data. Taylor provided some data from historic KC monitoring stations (and promised a bit more that is still forthcoming). This data adds signficiant spatial resolution in and around King County. Note: This is typical of all the additional KC data. Here's an example from summer 1969 DO data showing the locations of sampling.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/8500f00c-1ce5-4b8a-9745-eaeafe3db43a" width="800"/><br>Fig 5. Summer 1969 DO data from various sources and locations within Puget Sound.</p><br>

However, this data really only seems to add DO data from 1965-1975 in this specific location, though SA and CT samples are collected throughout the 1986. Perhaps data is missing? I've followed up with Taylor here, and also have checked in on some outstanding data she mentioned collected near Point Jefferson from the 1970s-1990s.

I'm a a little chagrined since I thought we'd be able to fill in some of the temporal and spatial gaps especially on decadal timescales. However, this may not be the case and of course I'll work with it! However, I've done some digging and I know there is at least some other data lurking out there... In Moore et al. (2008) they cite Ecology monitoring stations since 1993 in their paper, and mention this set extends back to 1973. That would be really helpful! I emailed Jan Newton after Ocean Sciences to follow up on some chats we had about data in this time period during the conference, but I haven't heard back.

---

## Next Steps - I Gotta Start Writing :)

So now that I've done some data incorporation and feasibility assessing, I am getting the itch to put pen to paper for my Paper 1 and General Exam. I attached a working outline to my agenda email this week. Here's a few general thoughts:

1. Chapter structure? See outlines.
2. LaTex for paper writing
3. Any focus on SOG in my thesis?!
4. Episodic events? (ORCA buoys, Penn Cove/Port Susan moorings)


---


## Miscellaneous

Thoughts for posterity:
* New paper: Alin et al. (2024) - WOAC OA/DO trends 2014-2018
* Review Collias publications for early data context.
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program) - Taylor provided more KC monitoring data in this time.


---

## Bookkeeping
* Ocean Sciences - reimbursements submitted
* Schooner Series...
* General Exam - scheduled 6/18


---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. ...
