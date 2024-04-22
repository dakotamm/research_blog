# Observed DO Minima and General Exam Updates

### Goals From Last Meeting:
1. Work on integrating new KC data into LO - README + Parker review.
2. Penn Cove observations vs. model comparisons.
3. Make histograms like Aurora's comparing depth and DO for 2013.
4. Work on General Exam/Paper 1 - literature review for deoxygenation in temperature urban estuaries + set up documents.
5. Formally schedule General Exam with CEE.
   
### Completed Goals:
1. Made histograms like Aurora's comparing depth and DO for 2013.
2. Working on General Exam/Paper 1 - literature review for deoxygenation in temperature urban estuaries + set up documents.
3. Formally schedule General Exam with CEE.

---

## Recent Progress Summary

### General Exam + Paper 1

The beginning of the quarter has been a lot of work toward planning my General Exam and first paper. In typical fashion, my first paper is largely my first thesis chapter. Alex and Parker and I have spent time assessing the feasibility of these scopes and I have a working outline of my first paper, as well as a burgeoning introduction/literature review section for my general exam. Currently, a quick summary of my working thesis scope is as follows:

* **Chapter 1:** *Also Paper 1...* Analyzing Decadal, Annual, and Spatial Variation of Salinity/Temperature/DO in Puget Sound
* **Chapter 2:** *This is either a Chapter 2 or a Part 1b...* Identifying mechanisms for DO change from observations. Expand to include BGC variables. Expand to include Strait of Georgia/Strait of Juan de Fuca? Episodic timescales?
* **Chapter 3:** *This could also be a Part 2...* Analysis of shallow cove/embayment hypoxia development and mechanisms using observations (KC Whidbey Basin data) and a high-resolution nested model! Given that most of the hypoxia we observe both from field measurements and via models is showing up in shallow regions and we now have nice data for Penn Cove, this is an important piece of the puzzle!

My goal is to have a draft of my first paper by the time I defend my General Exam in June! Feeling the pressure for sure :).

### New KC Data

The last few weeks, I've brought in KC's data that I've collected both via their databases and also from direct communication with Taylor and Greg at KC. Here's a list of what I have now:

1. Taylor's "old KC site" bottle data (1965-2000)
2. KC's non-QCed bottle data (1965-present)
3. KC's non-QCed Whidbey Basin CTD data (2022-present)
4. KC's QCed CTD data excluding Whidbey Basin (1998-present)

I'm also waiting for a Point Jefferson KC sampling set from the 1970s-2000s that Taylor has described to me!

I've processed this using a similar process to other data sources in the LO ecosystem. As I can, I'm working on cleaning this up for use by other LO users and also writing a nice README :).

Note: I have plots for every decade, year, season, and variable for all of this data. Plots show location and values colored by sampling agency and data type.

### Decadal-to-Annual Resolution in New Data

It's been great to get new data and assess what it can do for my scoped analyses. What we've encountered as a primary difficulty is lack of temporal and spatial resolution to our data. In particular, it's hard to get time series extending through the entire timerange (1930s onward) in specific locations. The biggest dearth of data is the 70s-90s, especially for DO data. New historic KC data adds signficiant spatial resolution in and around King County. Note: This is typical of all the additional KC data. Here's an example from summer 1969 DO data showing the locations of sampling.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/8500f00c-1ce5-4b8a-9745-eaeafe3db43a" width="800"/><br>Fig 1. Summer 1969 DO data from various sources and locations within Puget Sound.</p><br>


### Penn Cove Feasibility Assessment

I conducted a spatial and temporal quick dive into KC's 2022-2024 monitoring data in Whidbey Basin. This would then inform whether or not it makes sense for me to dive into the specific mechanisms at play in these shallow areas that seem to be highlighted as hypoxia hotspots in the Salish Sea Model (and to some extent in LO as well). Given the lack of long-term data in these areas, a high-resolution model could be used to specifically target Penn Cove as an example for important mechanisms for hypoxia in these regions.

First, I looked at the available CTD sampling that KC has conducted since 2022. KC has 9 sites in Whidbey Basin, with 4 in and around Whidbey Basin. The sites are as follows:
* SARATOGARP (outside of Penn Cove in Saratoga Pass)
* PENNCOVEENT (at the mouth of Penn Cove)
* PENNCOVEECW (midlength of Penn Cove, shallow and nearshore)
* PENNCOVEWEST (at the head of Penn Cove)

I'll present all four sites, but the most comparable sites exclude PENNCOVECW given its shallowness! Note for the following figures I'm only filtering out erroneous negative values (no other filtering applied).

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4c6ff27a-53a2-4b39-b6e1-6cd6754c9a30" width="800"/><br>Fig 2. Time series of sampled variables at KC CTD site SARATOGARP.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/bb447235-cdb5-4460-8805-69ca21719997" width="800"/><br>Fig 3. Time series of sampled variables at KC CTD site PENNCOVEENT.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/dc934bf2-4385-4f2f-bbc6-170e7b3e081b" width="800"/><br>Fig 4. Time series of sampled variables at KC CTD site PENNCOVEWEST.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ed3f032b-2e3b-4f24-8cae-fb4fc12cd72c" width="800"/><br>Fig 5. Time series of sampled variables at KC CTD site PENNCOVECW.</p><br>

Some quick observations from the four sites:
* We can see some clear seasonal patterns, but not a ton of interannual variation. It seems like both years have similar magnitudes of DO change seasonally. These lag chlorophyll maxima. NO3 depletion lags chlorophyll maxima as well.
* Across the four sites, there is similar temperature time series except for one potential outlier in the Saratoga Pass site. The shallowest site does see the highest maximum temperature.
* At all the sites, there is a similar pattern for max chlorophyll in time, with 2022 having more sustained high chlorophyll levels. However, DO does not seem to be lower in 2022...
* Outside of Penn Cove, NO3 maxima are higher and show less variability despite similar chlorophyll variability across sites. Additionally, DO minima are lower and less variable, but do not show hypoxia. Finally, lower salinity minima are observed.
* Comparing the head and the mouth of Penn Cove - both show hypoxia develop. The head site has more variability in DO with lower minima. Hypoxic development at the head leads hypoxic development at the mouth. At the head, there is an increase above hypoxic levels in October 2022, surrounded by two months of severely low DO. This rebound is not evident at the mouth of Penn Cove.
* The shallowest site in the middle of Penn Cove does not development of hypoxia! However, it does show lower chlorophyll peaks in 2023, corresponding with higher DO.
* At all sites, there is not a visually apparent annual-to-decadal trend in any variable.

Following in some of the footsteps already laid down by members of Parker's group, I could create a high-resolution nested model for sensititivty analysis and experimentation to identify important mechanisms driving hypoxia in these potential hotspot shallow cove/embayments. Some lingering questions: Would a model of this shallow area require further work on benthic processes and fluxes? Does this work with WWU field observation thoughts in Penn Cove?

---

## 2013 DO Minima Histograms

From last week, Aurora had some really cool 2D histogram plots for all of her model run in 2013. She identified what appeared to be a hotspot for modeled hypoxia bottom hypoxia in areas 10-50 meters deep. This lines up really well with KC observations in Penn Cove, and I also made some histograms to match Aurora's analysis. To begin, here's all of the sampling locations in 2013:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/52850a6c-98e6-4018-bc0e-3645fd3a89fd" width="600"/><br>Fig 6. 2013 DO sampling locations, colored by source and type.</p><br>

Here's a plot of cast DO minimum vs. cast minimum depth:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/87f794e7-92d0-43c1-a2a6-9767ea17dd89" width="600"/><br>Fig 7. 2013 Puget Sound DO minima vs. depth minima.</p><br>

We asked the question last week regarding the location of these DO minima (if potential mid-depth minima might confound these histograms). Here's a similar histogram, but the deepest DO measurement to cast minumum depth (effectively bottom DO):

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6cfb0946-628c-413b-9150-60d46372104f" width="600"/><br>Fig 8. 2013 Puget Sound bottom DO vs. depth minima.</p><br>

Finally, a histogram comparing the minimum DO measurement to the cast depth at which that measurement is taken:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c15f0202-ec60-4267-80cb-6a190fc1d5d6" width="600"/><br>Fig 9. 2013 Puget Sound DO minima vs. depth at DO minima.</p><br>

These all look pretty much identical! That means that the minimum DO is found at the minimum depth most of the time, according to our field observations. This also is really consistent with model results - that the hypoxic DO minima are at the bottom of regions between 10 and 50 meters deep! This is also really consistent with our findings in shallow areas like Penn Cove (and encourages me to move forward with that scope of work even more).


---

## General/Paper Progress

This week I've put some time into literature review, though not quite as much as I've wanted! So far, I've been beefing up the outline (shared with Alex and Parker last week via Google Docs) regarding mechanisms driving hypoxia in different temperature estuaries. So far, I've mainly reviewed the Baltic Sea and I'm starting on the Chesapeake as of Monday afternoon! Some lingering questions...

1. Chapter structure? See outlines.
2. Any focus on SOG in my thesis?!
3. Episodic events? (ORCA buoys, Penn Cove/Port Susan moorings)


---


## Miscellaneous

Thoughts for posterity:
* New paper: Alin et al. (2024) - WOAC OA/DO trends 2014-2018
* Review Collias publications for early data context.
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)
* Taylor to provide 1970-2000 Point Jefferson data.


---

## Bookkeeping
* Ocean Sciences - reimbursements submitted
* Schooner Series...
* General Exam - scheduled 6/18
* OOO - 5/2-5/3


---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. ...

