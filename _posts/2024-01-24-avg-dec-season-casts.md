# Preliminary Average Seasonal Decadal Casts

### Goals From Last Meeting:
1. Map of sampling locations per decade.
2. Average seasonal decadal SA/CT/DO casts with confidence intervals and smoothing depth-averaged bins, overlaid on same axes.
3. Submit Ocean Sciences + computer reimburesements.
   
### Completed Goals:
1. Map of sampling locations per decade.
2. Average seasonal decadal SA/CT/DO casts with confidence intervals and smoothing depth-averaged bins, overlaid on same axes.
3. Submitted Ocean Sciences + computer reimburesements.
   
---

## Rebinning + Seasonal Decadal Casts

This week, I'll start with my "north star" plot - this is the SA/CT/DO seasonal decadal average casts with relaxed depth-binning in **Hood Canal**. After playing around with some plotting styles, I found only highlighting extreme confidence intervals to be the most readable. Here's with coloring the 1940s and 2010s average cast confidence intervals.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3b34a6fd-9e83-4330-ad36-4d155b5d6083" width="800"/><br>Fig 1. Hood Canal SA/CT/DO seasonal decadal average casts with 95% confidence intervals.</p><br>

I don't know about you but I am kind of excited about this plot! This means that there is a statistically significant difference (with 95% confidence) that there is a significant change at regions where these casts do not overlap. Notably, all seasons show a decrease in DO at approximately 20m and deeper... 

**Note:** These are not the smoothest casts, and I'm still manually finagling depth-binning... There could be more work there to get more "realistic" casts...

---

## Decadal Cast Locations

Given the above, we can now have some confidence that the trends we're observing are not influenced by a change in sampling depth over time exclusively. However, a change in sampling location may explain some variation. Here's plots of seasonal sampling locations for DO per season in Hood Canal in the 1940s and 2010s.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f60fc614-09af-4e15-8b4f-dd01a2919e94" width="800"/><br>Fig 2. Hood Canal seasonal decadal DO sampling locations in the 1940s.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/7fa0b138-030a-4044-a0b0-4dea32273e0d" width="800"/><br>Fig 3. Hood Canal seasonal decadal DO sampling locations in the 2010s.</p><br>

**I'll add a video if I can debug why ffmpeg isn't working for me, after successfully making a million videos for me today. Worst case I can show these pngs.**

**Note:** Though there are few dots, this generally does represent repeat sampling in this location. I have not found instances where this is not the case.

So there is definitely a change in Hood Canal in sampling location and spread over time. Since the 1940s largely sampled closer to the mouth of Hood Canal, these may be less suscetible to low DO naturally since they may have higher flushing rates... But there is also more potential for deep-water intrusions over the entry sill (though the casts may not be deep enough to capture this...)

I'm thinking of how to control for this, and limiting trends to only overlapping areas may be the most straightforward way... Should I implement smaller polygons? Seems a very granular approach.

---

## Some Notes on Data Quality

In looking at Hood Canal and Lynch Cove, I was perplexed by some deep casts that seemed out of place in Lynch Cove. Here's some figures that show what erroneous cast depths I'm talking about...

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/19ec4aff-36a8-4a7c-a34d-731b4ec5dd90" width="800"/><br>Fig 4. Lynch Cove SA/CT/DO seasonal decadal averages casts with erroneous deep casts.</p><br>

This is weird because...Lynch Cove is only about 45 meters deep at max! So I manually went through and found ~10 casts that had erroneous depths (up to 175m) and I removed them from the dataset. I haven't gone through every area yet and run similar checks, but this is certainly something to keep in mind. Perhaps a filter based on the max depth of LO grid at cast locations would make this less manual?

---

## Miscellaneous

Next steps:
* Control for lat/lon change in cast locations over time.
* Regional analyses like above for Hood Canal
* Interregional comparison of sampling depths!!!
* Explore large CI data points
* Clean up plotting - how to show this succinctly?

Thoughts for posterity:
* Review Collias publications for early data context.
* Zooming in on Hood Canal trends (most apparent change in CT/SA/DO over time) - focus on hypotheses for trends here, build tools for whole system analysis.
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)
* Skagit data + trends


---

## Planning

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
  * Aim for three chapters...
  * Where does Penn Cove stuff fit? Learning how to run LO?
  * Incorporating reading...especially Riche et al. 2014 and Moore and Mantua 2008 (likely reading bulk **after** Ocean Sciences).
  * **Need to assemble committee! Evidently Michelle can GSR**
  * **Firmer grasp of timeline after Ocean Sciences**

---

## Bookkeeping 
* Ocean Sciences: 2/18/-2/23
  * Booked: flights, accommodations - **reimbursements pending**
  * **Should I do a "digital poster"?**
* New computer :) - **reimbursements pending**
* PECS - on the radar

---

### Looking Ahead:
1. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
2. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
3. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
4. Penn Cove nitrogen budget with WWU + Penn Cove nested model...
5. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. See next data analysis steps above.
