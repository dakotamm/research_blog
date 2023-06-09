# KC Debrief, VFC Big Strides, and Early GRC Poster Thoughts

### Goals From Last Meeting:
1. KC materials.
2. More VFC with observations.

### Completed Goals:
1. KC materials - presented on Friday, 5/26/2023.
2. More VFC with observations.

---

## KC Meeting Debrief

Last Friday we had our quartertly update with King County. I felt that I presented a good chunk of progress since our last meeting with them. There were a lot of thought-provoking questions and suggestions, which were great. In general, I'll note a few takeaways:
* KC Whidbey Basin Monitoring, Port Susan mooring(?), and Coupeville mooring data are available for use - Taylor Martin will distribute the link for us.
* Susan Allen recommended I incorporate field observations from the Strait of Georgia Date Centre (https://sogdatacentre.ca/atlas/citscidata/).
* Mike Brett emailed me after my presentation regarding my misuse of the terms "bias" and "error" in my discussion of method viability, recommending I review Stow et al. (2003) to refresh my discussion. I appreciate this critique and I agree - I really need to brush up on not only my statistical knowledge, but what is appropriate in my discussions.
* Discussion in the chat advocated for use of the term model "evaluation" vs. "validation" - this comes up a lot and I will practice honing my terminology.
* Two further refinements for the VFC method seem important (and will be something I'll effort in future revisions):
  * Checking that observational casts go full depth.
  * Handling DO concentration "inversions".
* Parker pointed out that Whidbey Basin tends to have higher "sampling error" than Strait of Georgia -  I need to do more investigation on this trend.

Any other comments, critiques, takeaways, etc. for my work? I appreciate it!

I presented the following revised timeline to track:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6ca38c64-e443-4cf8-b53c-a02fc7af7043" width="700"/><br>Fig 1. Updated timeline from KC Spring 2023 update.</p><br>

**Note:** I also want to keep noted potential Penn Cove/Whidbey Basin fieldwork proposals - this is something that I have not thought much more about and want to keep on our radar if it makes sense.

---

## VFC Big Strides

Since there was no meeting and no blogpost last week, I'll narrate the progress I made to present to KC. In general, I refined the VFC method codepackage to work with LO history, VFC using LO casts, and VFC using observational data. It now works with all (5) databases that are currently nicely cleaned in the LO ecosystem, which are:
1. WA DOE bottle
2. WA DOE ctd
3. DFO bottle
4. DFO ctd
5. NCEISalish bottle

I can subdivide the domain into any division based on the i/j indices for LO segments. For the KC analysis, I subdivided it on "basins" (i.e., sections based on segment letters, like all "G" segments for the Strait of Georgia). This allowed me to analyzed distinct basins and used a lot of casts to inform the analyses I presented. As a reminder, that analysis was conducted as follows:
1. 2017 study year
2. all (5) data sources used
3. monthly time-binning (using a single LO history file for the whole month on the first day of the month).
4. focusing on DO threshold < 5.0 mg/L

For each of the basins with data, the following figures show an animation of the subthreshold thickness LO history (top, blue), VFC with LO casts (middle, purple), and VFC with observational data (bottom, green). Note that for LO casts, the same locations as observational data is used.

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ce9b8d57-facd-407d-9389-69448eaf4110" controls="controls" style="max-width: 400px;"></video><br>Fig 2. Subthreshold thicknesses for Strait of Georgia.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/04254614-9aff-4e85-abc2-df73eb1d5a03" controls="controls" style="max-width: 400px;"></video><br>Fig 3. Subthreshold thicknesses for Strait of Juan de Fuca.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d2165b10-c559-4673-9a8b-9e4c3edaf75a" controls="controls" style="max-width: 400px;"></video><br>Fig 4. Subthreshold thicknesses for Admiralty Inlet.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/dab2968c-f6ce-4f1e-bdd7-ff6ae6a383c0" controls="controls" style="max-width: 400px;"></video><br>Fig 5. Subthreshold thicknesses for Whidbey Basin.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/09157868-23f0-483e-828c-ce43c234b706" controls="controls" style="max-width: 400px;"></video><br>Fig 6. Subthreshold thicknesses for Main Basin.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/100af1b8-d7cd-4b59-9957-8b02915f155b" controls="controls" style="max-width: 400px;"></video><br>Fig 7. Subthreshold thicknesses for South Sound.</p><br>

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/271c404d-c3bb-45d4-a521-e864a6bb4cba" controls="controls" style="max-width: 400px;"></video><br>Fig 8. Subthreshold thicknesses for Hood Canal.</p><br>

Given these subthreshold thicknesses, we can further the analysis by creating time series for each month for each data analysis type in each region. We can also conduct error analysis for both sampling error (the deviation of the VFC conducted with LO casts from the LO history file) and the modeling error (the deviation of the LO history file from observational data VFC). I used normalized RMSE over the whole year to proxy both of these measurements, normalizing by the range of values in the "observed" dataset.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/98c6ade8-16a2-46f7-a6f1-66987afa17f5" width="800"/><br>Fig 9. Strait of Georgia time series and error estimates.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/2dc3468e-d8d9-4afc-bec0-f8e6516dbaa9" width="800"/><br>Fig 10. Strait of Juan de Fuca time series and error estimates.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/1ca14ec1-8e46-4883-9e81-14ddce9bde8a" width="800"/><br>Fig 11. Admiralty Inlet time series and error estimates.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/23253659-8ddd-4b2a-ba46-cb63f172144e" width="800"/><br>Fig 12. Whidbey Basin time series and error estimates.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/03e2e038-dbf6-433e-b339-f880ba94a6a3" width="800"/><br>Fig 13. Main Basin time series and error estimates.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6f092389-3e34-4010-8284-9a54b548416b" width="800"/><br>Fig 14. South Sound time series and error estimates.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/b10179f9-c732-4f8f-9e13-308563be9dff" width="800"/><br>Fig 15. Hood Canal time series and error estimates.</p><br>

We can summarize the spatial variation in normalized RMSEs (as proxy for sampling, left, and modeling error, right) in the following plot.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6dad8e55-e9d0-4796-bd75-b1e2f2305ca6" width="800"/><br>Fig 16. Normalized RMSE proxies for sampling error and modeling error for all of 2017 (determined using monthly subthreshold volumes).</p><br>

We can understand more deeply and look at the spatiotemporal variation of monthly "error" by plotting the percent difference of the observed and predicted values (LO history vs. VFC using LO casts for sampling error, left, and VFC using observational data and LO history files for modeling error, right), shown in the following figure.

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4a1d282d-56bd-4006-83ee-1502bf9397e1" controls="controls" style="max-width: 800px;"></video><br>Fig 17. Percent error to proxy sampling error (left) and modeling error (right) for subthreshold volumes throughout 2017.</p><br>

Finally, to understand the trends in observed subthreshold volumes over the year, this preliminary analysis yields the following time history of subthreshold volumes normalized by each basin's total volume. This doesn't have error bars and is merely representative of the beginning of larger analyses.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f7538108-7281-4efb-89f7-6896d62003d5" width="700"/><br>Fig 18. Normalized subthreshold volumes per basin throughout 2017; color indicates relative basin total volumes.</p><br>

This is the first step among many steps, but at least is a fun and exciting first look at some observational data. Here are some next steps (some from the KC meeting, but generally):
* Get set up to run on Apogee - in lieu of using just one history file to represent a month for personal computer space efficiency, start working with the full suite of model data and perform analyses more quickly.
* Incorporate variable inversions + cast depth checking.
* Start looking at interannual variability.
* Investigate differences in time-binning.
* Investigate Whidbey Basin vs. Strait of Geogia (e.g.) differences in error (Whidbey Basin tends to have less throughout the year).
* Apply uncertainties to measurements of subthreshold volumes estimated with VFC.
* Refine statistical understanding and presentation of errors and biases - what's the best way to do this?
* Conduct analysis of hypoxic volume (<2.0 mg/L).
* Conduct analyses of different domains, time periods, and state variables of interest.
* Continue refinenement of codebase and work towards making it more time efficient.
* Clean and incorporate more data (especially KC Whidbey Basin data).
* Define GRC poster scope.
* Synthesize trends -> paper draft toward end of 2023???
* Work with Ben/Aurora on what I can build to be helpful!

---

## GRC Poster Thoughts

After the KC meeting push, I'm looking towards drafting by GRC poster by the end of next week. A rough outline is as follows:

* Title: Spatiotemporal Trends of Dissolved Oxygen in the Salish Sea
  * Caveat preliminary analysis...
  * Motivation of DO in Salish Sea - why it's important to understand trends, factors that might influence
  * Rough Option 1:
    * Describe VFC method in depth, discuss sampling error, emphasize obs data analysis technique
  * Rough Option 2:
    * Depends on how far I can get with trend analysis...
    * Interannual variability - start proposing drivers???
    * Covariation of DO with other state variables?
  * Trends in DO over all available years...
  * Trends in DO over one year (discuss natural variability?)
  * Tie in with model - modeling error?

I would love to discuss this in more depth, but will effort a draft and evaluate these options as I put it together.

---

## Bookkeeping 
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* CEE PhD Performance Reviews: due 6/30/2023
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. Organize literature - Endnote?

### Looking Ahead:
1. GRC poster draft - target by end of next week.
2. CEE PhD Performance Review - draft by end of next week.
3. Continue analysis and refinement of VFC method.

### Goals For This Week:
1. Incorporate DO inversion handling + shallow casts usage.
2. Run hypoxic and interannual conditions.
3. GRC poster draft - target by end of next week.
4. CEE PhD Performance Review - draft by end of next week.
