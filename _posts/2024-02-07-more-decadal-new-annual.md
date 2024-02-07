# Puget Sound Repeat Sampling Location Trends and Some Annual Variation

### Goals From Last Meeting:
1. Exclude data outside of two standard deviations from "average" casts.
2. Find and analyze locations with multi-decadal sampling history.
3. Explore interannual variability in average casts since 2000.
4. Refine Ocean Sciences poster outline.
   
### Completed Goals:
1. Exclude data outside of two standard deviations from "average" casts.
2. Find and analyze locations with multi-decadal sampling history.
3. Explore interannual variability in average casts since 2000.
4. Refine Ocean Sciences poster outline.
   
---

## Temporal Trends at Puget Sound Sampling Sites with Long Time Histories

After last week, I was able to accomplish a few goals that we've discussed. First, I have **excluded data outside of two standard deviations of the binned averages**, then recalculated the mean and 95% confidence intervals. Upon evaluation of individual sampling sites, there were no massive outliers; I will continue this procedure and careful scrutiny of erroneous values for each region and period.

Extending outward from Hood Canal, I have selected several more sites in Puget Sound that have time histories extending back at least through the 1950s. There are potentially other sampling sites, but the following provide decent coverage of Puget Sound for this pass of analysis. They are as follows:
* Hood Canal
  * Hood Canal Sill
  * Hazel Point
  * "Shallow" Lynch Cove
* South Sound
  * Budd Inlet
  * Dana Passage
  * "Mid" Carr Inlet
* Main Basin
  * Admiralty Sill
  * Central Basin Near Edmonds
  * Central Basin Near Alki
* Whidbey Basin
  * Near Hat Island
  * Northern Saratoga Passage (near Penn Cove)
  * "Mid" Port Susan - *I made an exception here because this one comes up a lot. It only has data since the 1960s.*
 
The following figure shows the sampling clusters.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6922e58d-828a-48df-a1a0-9f6bdc459e8b" width="600"/><br>Fig 1. Selected DO bottle sampling locations with long time histories.</p><br>

Now I'm going to throw you a bunch of plots for each of these locations! First Hood Canal:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/9c101ca9-41d3-4198-b682-6b4a062c8024" width="800"/><br>Fig 2. Hood Canal Sill decadal/seasonal average casts (CIs for 1930s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e839d81f-59c0-4f19-aa89-3a8f5d974cab" width="800"/><br>Fig 3. Hazel Point decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/fa9c0408-475d-47c4-aa9d-bf20c7194daa" width="800"/><br>Fig 4. Lynch Cove Shallow decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

Now South Sound:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ab8c0e56-9b67-4162-a6ea-0ead0574d296" width="800"/><br>Fig 5. Budd Inlet decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4e85fc34-e2b3-45c7-a91d-da5a964d56f6" width="800"/><br>Fig 6. Dana Passage decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f58e46e3-780d-4cbc-b5a9-d74efbfa382f" width="800"/><br>Fig 7. Carr Inlet Mid decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

*Something weird is happening at Budd Inlet (potentially I'm missing some large outliers). I need to check this in more depth.*

On to Main Basin:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ceca665b-0670-426b-9543-365c2a4b9fed" width="800"/><br>Fig 8. Admiralty Sill decadal/seasonal average casts (CIs for 1930s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/de87c5c3-1c99-4908-b867-ce2e0121f644" width="800"/><br>Fig 9. Near Edmonds decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/02698fa5-c870-4be0-a184-0f995854122e" width="800"/><br>Fig 10. Near Alki decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

*Perhaps bottle sampling at the sill is only at shallow depths in recent years? Perhaps I should incorporate CTD data too.*

And finally Whidbey Basin:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/42772ca6-4ab4-417a-8127-780b72ea45fb" width="800"/><br>Fig 11. Hat Island decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/76b19996-90a2-48cf-8997-b99c4f51c64b" width="800"/><br>Fig 12. Saratoga Passage North decadal/seasonal average casts (CIs for 1950s and 2010s).</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/51c5ceeb-b99f-449d-931f-cc73169784ed" width="800"/><br>Fig 13. Port Susan Mid decadal/seasonal average casts (CIs for 1960s and 2010s).</p><br>

*Port Susan is pretty darn sparse...*


---

## Interannual Variation Exploration

Another item that came out of last week was trying to create smaller time increment seasonal depth-averaged casts. So I've employed a similar process for all basins in Puget Sound (given spatial consistency!) from 2000 to present. I'll focus on Hood Canal for brevity of this post, but I have all the other plots and can gladly share.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ff9d9421-3caf-4352-ab2a-6bc5f17c6b5a" width="800"/><br>Fig 13. Hood Canal (sans Lynch Cove) yearly/seasonal average casts since 2000.</p><br>

*Add CIs if have time.**




---


## Ocean Sciences Poster Outlining

**EFM Poster Review moved to 2/15. I'd like to have a poster draft by end of the week!**

Here's my big question: "Is DO (also CT/SA) changing over time in Puget Sound?"

Motivation/Background:
* EPA 2019 trend seems to suggest decrease in DO over time - does larger swath of data corroborate?
* Explain why there is focus on this...
  * Increase in population corresponding to increase in N-load? (read and ref. Ecology report)... BUT leading order source of N is ocean!

*Fill in further planning for tomorrow.**

Here's some of my big answers:
* In most places, no not really! DO isn't really declining over time (though CT seems to show a warming trend so far in Hood Canal).
* In places where trends emerge at a first pass, more rigorous data analysis shows that data sampling location may be confounding trends observed. This is particularly true (where I've looked) in Hood Canal, where later sampling has moved south toward the end of Hood Canal. Trends aggregating al of Hood Canal show some changes, but spatially normalized analysis shows that, in fact, it's just lower DO toward the end of Hood Canal. (I should look at other locations and/or all of Puget Sound... But the only place we really saw a strong decline over time is Hood Canal, at least at first pass.)

Which brings me to the "SO WHAT":
* Don't really have enough data to say anything with certainty, and what we've looked at so far does not really support changes in DO...
* So if DO is not really changing (that we can tell)...what else is changing? -> CT!
* What is causing CT trends? -> ...climate change probably (shocking)...

********

---


## Miscellaneous

Next steps:
* Regional analyses like above for Hood Canal

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
