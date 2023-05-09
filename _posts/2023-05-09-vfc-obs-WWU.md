# VFC Using Observational Data and WWU Debrief

### Goals From Last Meeting:
1. Put together lecture for WWU - 5/4/2023.
2. Consider "pitch" to WWU faculty regarding Penn Cove fieldwork; mooring ~ 1 month, shipboard sampling (understand processes controlling stratification, residence time, etc.).
3. Build out codebase for VFC using observational data.
4. Meet with Parker for code efficiency review - moved to this week.

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



---

## VFC Progress and Plan

Given the time spent on preparation and taking quals, I have not made huge progress on research. From our last meeting, we set my directive toward starting to plunge into observational data, instead of spending more time trying to minutely quantify VFC errors using solely LO casts. I want to note for posterity that there are a few kinds of error that I'm discussing:

1. **Sampling Error** - given a fraction of sampled points in the domain, how closely can we approximate the domain?
  * This is what I've been doing with using the VFC method within the LO domain. Since we can only have full domain knowledge about a model, this is the only way to approach this question.
  * Eventually, however, the domain is "real-life," and estimates made using the LO domain will inform the confidence we have in our VFC methods using real observational data.
  * This could be captured taking "n" points out of the domain in LO and varying "n" until the VFC method and LO output converge. However, this simple implementation doesn't represent the spatial biases represented in real-life sampling (i.e., general undersampling of shallow areas).
2. **Modeling Error** - given observational data CTD/bottle casts and model CTD/bottle casts/full domain output, how closely does the model reproduce real-life?

Both are important, but neither have meaning unless I actually start working with observational data. So onwards! The next order of business is what we've termed the "money-plot;" a time-series of hypoxic volume in the Salish Sea over as long as we have record, and compared to the LO output at available times.

Since quals finished Friday, I've been reconnecting to research and figuring out how to use observational data for the VFC method. Stay tuned throughout the week for more.

Next steps are as follows:
1. Start using observational data in VFC method (likely using DFO in specific domains again).
2. Continue to build robust VFC toolbox - ESPECIALLY code efficiency.
3. Continue thought on error evaluation, but on the backburner for now.
4. Working towards Gordon Conference poster plots/figures.

---

## Bookkeeping 
* WWU Lecture - scheduled for Thursday, 5/4/2023
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
1. Plugging back into research, start using observational data in VFC method!
2. Meet with Parker if available this week for code efficiency review.

### Goals For This Week:
1. Put together lecture for WWU - 5/4/2023.
2. Consider "pitch" to WWU faculty regarding Penn Cove fieldwork; mooring ~ 1 month, shipboard sampling (understand processes controlling stratification, residence time, etc.).
3. Build out codebase for VFC using observational data.
