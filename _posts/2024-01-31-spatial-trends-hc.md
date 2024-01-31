# Hood Canal Spatial Variability Exploration

### Goals From Last Meeting:
1. Explore spatial variation over time as a potential driver for trends in DO/SA/CT.
2. Start thinking Ocean Sciences poster outline.
   
### Completed Goals:
1. Explored spatial variation over time as a potential driver for trends in DO/SA/CT.
2. Started thinking Ocean Sciences poster outline.
   
---

## Spatial Variation in Hood Canal Exploration

From last week's async review (as I was languishing - thank you for your awesome comments regardless!), we discussed exploring spatial variation in sampling location over time as a possible driver of the trends we're seeing in Hood Canal. **Note: This is where my data analysis has gotten a little bespoke to Hood Canal, and so the results aren't generalizable to other regions readily.** This comes from maps I made last week showing a clear change in sampling locations within Hood Canal overtime. In general, earlier sampling was conducted closer to the mouth of Hood Canal, whereas modern sampling takes a consistent distribution down its length.

First, I want to confirm a bit of intuition that we've discussed. In general, we believe the dissolved oxygen decreases as we toward Lynch Cove along Hood Canal due to less exchange possibility with the rest of Puget Sound via the mouth (longer residence times at a "dead end"). To confirm this, I focused on 2010s sampling. First, a map of all bottle cast locations measuring DO...

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f8708b90-e5f8-4e7a-be3c-067fca3f3ebf" width="600"/><br>Fig 1. Hood Canal (sans Lynch Cove) 2010-2019 DO bottle cast locations.</p><br>

This shows that there is a pretty even distribution of routinely-monitored locations along the length of Hood Canal. Now, I compared each cluster (binning by latitude ranges specific to these sampling locations) by comparing a depth-averaged, seasonal decadal representative profile for CT/SA/DO.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/a52276c5-ad95-440e-877f-cfd632b2e757" width="800"/><br>Fig 2. Hood Canal (sans Lynch Cove) 2010s seasonal decadal average casts, binned by latitude range.</p><br>

This shows a pretty clear correlation between DO and latitude. There is a clear, significant difference between the northernmost and southernmost sampling locations (higher DO in the north). This confirms our intuition for this decade.

Now, we explore whether or not sites at the same latitude show a trend in time. There are two sites that have consistent sampling throughout the time history. At each site, I created a seasonal decadal average cast for each location. For the site nearest to the mouth of Hood Canal:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/570d6d6c-218a-4e9e-9dcb-40d7e3377f00" width="600"/><br>Fig 3. Mouth of Hood Canal DO bottle sampling locations.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0650c36a-e453-4cc8-970a-79296d1eef83" width="800"/><br>Fig 4. Mouth of Hood Canal seasonal decadal average casts.</p><br>

We see that there is **not a statistically significant difference between 1930s and 2010s** seasonal decadal average casts. Focusing on the other site:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/bc8ffe48-1fd0-4bee-aebf-f520c8f4d957" width="600"/><br>Fig 5. Hazel Point DO bottle sampling locations.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/701219c8-fbf3-4b61-a88f-e3611f393cd2" width="800"/><br>Fig 6. Hazel Point seasonal decadal average casts.</p><br>

Here, we see that there is **not a statistically significant difference between 1950s and 2010s** seasonal decadal average casts, with the exception of a low DO minimum around 20 meters.

Where does this leave us? Mainly saying that a lot of the trends we thought we were seeing in Hood Canal DO are most likely due to changing in sampling location over time. CT tends to tell a different story (in that warming does appear fairly signficant, especially in the fall)!

---

## Ocean Sciences Poster Outlining

I'm excited to show some valiant data work finally! But I've been very myopic in Hood Canal and my efforts have yielded essentially no DO trend. So I'm not entirely sure what the story should be.

Here's my big question: "Is DO (also CT/SA) changing over time in Puget Sound?"

Here's some of my big answers:
* In most places, no not really! DO isn't really declining over time (though CT seems to show a warming trend so far in Hood Canal).
* In places where trends emerge at a first pass, more rigorous data analysis shows that data sampling location may be confounding trends observed. This is particularly true (where I've looked) in Hood Canal, where later sampling has moved south toward the end of Hood Canal. Trends aggregating al of Hood Canal show some changes, but spatially normalized analysis shows that, in fact, it's just lower DO toward the end of Hood Canal. (I should look at other locations and/or all of Puget Sound... But the only place we really saw a strong decline over time is Hood Canal, at least at first pass.)

Which brings me to the "SO WHAT":
* Don't really have enough data to say anything with certainty, and what we've looked at so far does not really support changes in DO...
* So if DO is not really changing (that we can tell)...what else is changing? -> CT!
* What is causing CT trends? -> ...climate change probably (shocking)...

...I feel like I'm missing a punchline... :)

**Existential Crisis:** Is what I'm focusing on sufficient for this poster? Should I focus somewhere else?
* Interannual variability drivers?
  * River flow? Atmospheric data? Shelf processes? ENSO?

...but ultimately I have some confidence in the answer to my initial question! I'll call it a science-win for the day!

---


## Miscellaneous

Next steps:
* Regional analyses like above for Hood Canal
* Interregional comparison of sampling depths!!!
* Explore large CI data points

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
* *Possible* Ocean Sciences Poster Review: 2/8
* Ocean Sciences: 2/18/-2/23
  * Looks like reimbursements so far are approved!
  * **Should I do a "digital poster"?** - may be more effort than it's worth...
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
