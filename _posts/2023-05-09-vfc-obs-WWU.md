# VFC Using Observational Data and WWU Debrief

### Goals From Last Meeting:
1. Put together lecture for WWU - 5/4/2023.
2. Consider "pitch" to WWU faculty regarding Penn Cove fieldwork; mooring ~ 1 month, shipboard sampling (understand processes controlling stratification, residence time, etc.).
3. Build out codebase for VFC using observational data.
4. Meet with Parker for code efficiency review - moved to this week.
5. Start thinking about GRC poster content.

### Completed Goals:
1. Put together lecture for WWU - 5/4/2023.
2. Consider "pitch" to WWU faculty regarding Penn Cove fieldwork; mooring ~ 1 month, shipboard sampling (understand processes controlling stratification, residence time, etc.).
3. Build out codebase for VFC using observational data.

---

## WWU Lecture Reflection

Last Thursday, 5/4/2023, Aurora and I gave a lecture to students in Sam Kastner's undergraduate class at Western Washington University in Bellingham. The students were extremely engaged and asked a lot of interesting questions! How fun!

We met with (4) faculty members after the lecture in a bit of a whirlwind. We met with Drs. Karin Lemkau, Dave Shull, Casey Saenger, and Dave Hooper. While they all had areas of specialty outside of our more comfortable physics world, it was easy and extremely eye-opening to chat with them. While I didn't have an opportunity to formally pitch for funding for a Penn Cove field campaign, I was able to start the conversation with both Sam and Casey Saenger. 

Some key takeaways:
* Students are engaged early and often for field data collection in Bellingham Bay, though certain faculty (Sam, Casey) are interested in getting them into more focused research work (like ours).
* A student asked if using proxy fished species could help understand the historic DO trends - an intriguing idea I don't know the answer to.
* Dr. Lemkau's work is very focused on pollutants (in lieu of anthropogenic nutrients). We broadly discussed modeling applications for oil-dispersal in Puget Sound.
* Dr. Shull's work on quantifying denitrification rates, nutrient burial, and DO flux in Hood Canal (Santana and Schull 2023) seems very important to our work. Admittedly, a lot of his work is currently over my head, but he provided us with some canonical literature to bolster our understanding (e.g., Sutton et al. 2013).
* Dr. Saenger is deals more in paleoclimate, and generally agreed that paleo-approaches to quantifying a "pre-anthropogenic" DO level was a bit unrealistic (but cool!). He also mentioned using N-isotopes to identify actual sources of nutrient inputs? All exciting but over my head. He asked us explicitly if we needed undergrads and general support for filling data gaps, so I told him about Penn Cove and that we'd be in touch if it makes sense.
* Dr. Hooper's work is largely to do with terrestrial ecology but is setting out to quantify the effects of riparian restoration (generally from a salmon-protection view) on non-point source nutrient influx, especially in largely agricultural areas. We talked general knowledge of Puget Sound/Bellingham Bay watersheds - which was all very informative!
* Sam was intrigued in the idea of Penn Cove fieldwork. In general, I think I need to do more thought about what's possible and how much undergrad involvement would be helpful...

Overall, it was awesome. Here's our opening slide for posterity (Figure 1).


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/a1e20fdd-10a5-494d-8fb8-7388241f18f9" width="500"/><br>Fig 1. WWU lecture title slide!</p><br>



---

## VFC Using Observational Data

I'm making strides in coming up with a seamless analysis codebase for analyzing hypoxic volume over time using cast data. My test environment this week is using DFO (dfo1) CTD DO measurements taken during 2017. I am using segments in the Straight of Georgia and for the purposes of the test, I'm combining casts within a calendar month. Figures 1-4 shows G1 in January, April, July, and October 2017.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/1251c8b3-6dc7-46ad-8958-7d994615e05a" width="700"/><br>Fig 1. January 2017 VFC subthreshold thickness for G1, 5 mg/L DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/1c51a07c-60a4-486b-afec-c8f481ded6d2" width="700"/><br>Fig 1. April 2017 VFC subthreshold thickness for G1, 5 mg/L DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0326b407-c31e-4583-9a95-03a9f5a07622" width="700"/><br>Fig 1. July 2017 VFC subthreshold thickness for G1, 5 mg/L DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e79eb801-e37c-440e-8e94-3cff2c3cb1b8" width="700"/><br>Fig 1. October 2017 VFC subthreshold thickness for G1, 5 mg/L DO.</p><br>

Figure 5 shows a time series of all segments through 2017's subthreshold volume. This is a first step in some more exciting things.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/292b87c8-0ef7-481f-afe7-113b6c84d5ed" width="700"/><br>Fig 1. October 2017 VFC subthreshold thickness for G1, 5 mg/L DO.</p><br>

Figure 5 shows a time series of all segments through 2017's subthreshold volume. This is a first step in some more exciting things.

(PS I have more images but ran out of time to add them/make them look nice).

I note that the data gaps are areas where no casts were taken, and "0" indicates no subthreshold volume calculated. We observe the expected seasonal trends! This is a good first step. In general, we see that G1 has a big spike compared to other regions, but there is some serious data patchiness. All told - onward to more detailed analysis!

Some issues:
1. G4 indexing issues (not yet diagnosed).
2. G1/G2 indexing overlap? Might be a plotting window remnant.
3. Duplicate indices within time window (two casts taken too close together too soon).
4. How do you make cool videos??? Spent way too much time on that...

Next steps are as follows:
1. Continue to build robust VFC toolbox - ESPECIALLY code efficiency.
2. Continue thought on error evaluation, but on the backburner for now.
3. Working towards Gordon Conference poster plots/figures.

---

## Bookkeeping 
* KC Spring Update - scheduled Friday, 5/26/2023
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods - need lit. review.
2. Figure out comments section on blog!!!
3. Organize literature - Endnote?
4. Figure out what to do about CEE 462.
5. Should we prepare for CERF?

### Looking Ahead:
1. More VFC with observations.
2. Parker meeting for code efficiency.
3. GRC poster + KC presentation planning.

### Goals For This Week:

