# Bottom Time Series for Decadal and Annual Salinity, Temperature, and DO

### Goals From Last Meeting:
1. Work on integrating new KC data into LO - README + Parker review.
2. Decadal and annual time series.
3. Work on General Exam/Paper 1 - literature review for deoxygenation in temperature urban estuaries + set up documents.
4. Formally schedule General Exam with CEE.
5. Track down more data!
   
### Completed Goals:
1. Decadal and annual time series - in progress.
2. Workingon General Exam/Paper 1 - literature review for deoxygenation in temperature urban estuaries + set up documents.
3. Tracking down more data!

---

## Cleaning Up Decadal Analysis

For this week's data analysis, I focused in on decadal analysis. Given the addition of new data and some more thoughts around depth consistency spurred by last weeks histograms, I have made the following data adjustments to my decadal repeat sampling sites:
1. I removed my "Near Alki" site from the analysis. There is so much depth inconsitency over the years. Instead...
2. I created "Near Seattle Offshore" as a site to incorporate a lot of the new KC data. This essentially spans Main Basin waters around Seattle, but avoids Elliott Bay (which KC sampled frequently) and also applies a depth filter of 60m, since shallow sites are inconsistently sampled but could skew data.
3. I added "Lynch Cove Mid", which is a central sampling location in Lynch Cove. There is some erroneous data here, so I've applied a depth filter to ensure we only have realistic depths in Lynch Cove. Via perusing nautical charts, I've come up with 45 meters as the maximum depth of this site, despite cast depths.
4. I added "Saratoga Passage Mid" without depth filtering.

Now we have a slightly different array of decadal sampling sites via which we can control for spatial variation in lat/lon space over decadal records. However, last week we did a lot of thinking about depths with hypoxia. Both Aurora's model results and my observations in 2013 showed that Puget Sound hypoxia occurs on the bottom where the water depth is 10-60 meters. This is really cool finding, but means that we must consider water depth and cast depth as controlled variables.

Additionally, reading through literature and from previous discussions, it seems obvious that we need meaningful time series for decadal trend analysis (in lieu of average decadal casts) (see Carstensen et al. 2014). In the Baltic work by Carstensen, they compare a series of time series from cast parameters. I identified a few that I think may be useful for us:
1. Bottom DO
2. Bottom temperature
3. Bottom salinity
4. Buoyancy frequency
5. Surface DO
6. Surface temperature

So at each of these sites controlled for spatial and depth variation, I should be able to come up with time histories here. For the first three, I decided to first test my canonical understanding of these properties (as well as assess our hypothesis with available data that there is a hypoxia hotspot at the bottom of 10-60m deep water). So, I created histograms that compare minimum DO to cast depth in permutations that allow me to visually see if there is mid-depth minima. I similarly created histograms for temperature, given the assumption that temperature minima occur at the bottom in Puget Sound. Finally, I created histograms comparing salinity maxima to minimum depths. The histograms for my "Near Seattle Offshore" sites are shown below for the 2010s decade for fall:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d213b97f-95a4-408c-90d6-feeab89b2ec0" width="800"/><br>Fig 1. Fall 2010s DO histograms assessing location of DO minima within casts.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f7e95e66-a3c4-4dcf-8e0b-a7ca390004bf" width="800"/><br>Fig 2. Fall 2010s CT histograms assessing location of CT minima within casts.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/7e907bbb-fab8-4c71-a7e1-ed8aa39732ab" width="800"/><br>Fig 3. Fall 2010s SA histograms assessing location of SA maxima within casts.</p><br>

A LOT to look at here, but basically this shows that during the fall in the 2010s at this site, we find that DO and CT minima occur at the bottom of casts. HOWEVER, salinity maxima do not appear at the bottom of water columns!

What this means is that for DO and CT, I can look at the bottom of each cast for consistent minima at this site during this time period. Salinity is a bit of a different story (but I want to consider bottom salinity at least in the following analysis...). These findings are consisent by visual inspection for every decadal time period and at every site (* note to self - did I check spring/fall/winter?).

The next step is an attempt on controlling for depth variation within these sites - **I'd love feedback here**. Since our decadal record is extremely spotty in all ways, I am also challenged to control the depth of the cast bottom (assuming this is near water column bottom) when creating averages and time series. The method I came up with was finding the mean and standard deviation of CAST DEPTH for each site/time period. Then, I took an average of each cast's values occurring within that depth range and called THIS value my bottom measurement for each cast. I believe this works somewhat well (or applies a level of rigor to control for cast depth). However, some sites still have considerable cast depth variation (which can be bimodal in some cases). This means that assuming normal distribution for cast depths may be erroneous. Also, some variables may not be sampled to the full depth of the cast all the time... Lots of things to consider!

In either case, I've created time series for all of my sites and across all seasons and decades for bottom SA, CT, and DO. Additionally, I've put on a 10-year rolling averages mean for each variable. I have TONS of plots that I'm happy to page through for our meeting, but I'll show an example here for fall in a select few locations:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/475c7c4b-d997-4f16-9bf0-4dacf9dd4b6d" width="800"/><br>Fig 4. Fall Near Seattle Offshore bottom SA/CT/DO with 10-year rolling mean.</p><br>

Here we can see that the Near Seattle Offshore site is not showing a super clear downward trend in DO. There are some potential outliers in salinity in the 60s (*need to investigate what's up here*). Also, we can see a possible increasing trend in temperature!

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/100277f3-515a-48f3-85e9-8cd18aeec24c" width="800"/><br>Fig 5. Fall Hat Island bottom SA/CT/DO with 10-year rolling mean.</p><br>

Near Hat Island (Whidbey Basin), I see a DO decrease and temperature increase, while salinity stays fairly constant.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/482059b4-0029-46cf-9a20-91c4d7896139" width="800"/><br>Fig 6. Fall Lynch Cove Mid bottom SA/CT/DO with 10-year rolling mean.</p><br>

At Lynch Cove Mid, I see a slight increase in bottom temperature, and there's some wonkiness in DO around 2010...but DO may actually have a bit of an increasing trend.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/69897167-cf57-4ebf-814a-bf57a401e62b" width="800"/><br>Fig 7. Fall Hood Canal Mouth bottom SA/CT/DO with 10-year rolling mean.</p><br>

However, several sites lose data in this analysis such that they no longer are multi-decadal during fall. This is almost certainly due to by "bottom value" calculations. These sites are:
1. Admiralty Sill (I believe modern sites, despite their closeness in lat/lon space, are sampled at shallower depths than earlier casts.)
2. Dana Passage (losing earlier data)
3. Hazel Point (losing modern data)
4. Hood Canal Mouth (losing modern data)
5. Saratoga Passage North (losing earlier data)
6. Port Susan Mid (really spotty on both ends)

This is a bit disappointing since I thought I had a way to control for the depth variation while still maintaining lat/lon consistency. But we plug along! Perhaps the best means of comparison is by depth-bin first instead of by lat/lon? Perhaps per basin?

---

## Annual Analysis

I also took a similar look at the annual trends we see in modern data (here from 1999 to 2019). Though there is some variation between smapling locations since 1999, there is not a whole lot of variation in *spread* throughout each basin. I can show maps if we'd like of any season and variable for each year.

Considering DO, SA, and CT, I have focused on each Puget Sound basin again. I'm not confident this is the correct approach, but to maintain consistency with decadal analysis, I performed the same bottom calculation as for decadal sites. I think assuming normality here is flawed given the lateral distribution of sampling, but I want to at least show the method. I did not perform any depth filtering for any basin here. Here's the result for fall:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d6002cfa-f4ed-4935-a89f-2f213dfb1e14" width="800"/><br>Fig 8. Fall Main Basin bottom SA/CT/DO with 1-year rolling mean.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f54bacb1-b7dd-4e91-9e69-271bf137288e" width="800"/><br>Fig 9. Fall Whidbey Basin bottom SA/CT/DO with 1-year rolling mean.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/9a262acd-a6a3-49e1-aa2c-cd4c17973e29" width="800"/><br>Fig 10. Fall South Sound bottom SA/CT/DO with 1-year rolling mean.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0b1daa50-3f3c-430a-93b8-cfa37efdca2f" width="800"/><br>Fig 11. Fall Hood Canal bottom SA/CT/DO with 1-year rolling mean.</p><br>

In Whidbey Basin, there seems to be some cyclical variation on an annual scale! Main Basin and South Sound show some variation on a multi-annual scale if you squint, and Hood Canal DO seems to be improving over time? Way more to dig into here...


---

## Data Gathering

A note that I've officially requested Ecology data from 1973-1998 after talking with Christopher Krembs and team!

Also - Taylor said she could likely have their 1975-2000 Point Jefferson data available this week.

---

## General Exam Status Update

Last week, we shuffled around my chapters a bit... (I need to update my outline.)

* **Chapter 1:** *Also Paper 1...* Analyzing Decadal, Annual, and Spatial Variation of Salinity/Temperature/DO in Puget Sound
* **Chapter 2:** Analysis of shallow cove/embayment hypoxia development and mechanisms using observations (KC Whidbey Basin data) and a high-resolution nested model! Given that most of the hypoxia we observe both from field measurements and via models is showing up in shallow regions and we now have nice data for Penn Cove, this is an important piece of the puzzle!
* **Chapter 3:** dentifying mechanisms for DO change from observations. Expand to include BGC variables. Expand to include Strait of Georgia/Strait of Juan de Fuca? Episodic timescales? (Still not so fine-tuned here.)

I've read more on the Chesapeake Bay this week (mainly Pritchard 1952). I need to read faster :) and throw my notes into my working outline.

Finally - I need to formally schedule this with the department.

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
* Ocean Sciences - no reimbursements yet for recent expenses.
* General Exam - scheduled 6/18
* OOO - 5/2-5/3
* PECS - ORAL presentation accepted! 9/23-9/27


---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. ...

