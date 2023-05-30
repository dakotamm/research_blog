# KC Debrief and VFC Big Stdies

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

Any other comments, critiques, takeaways, etc. for my work? I appreciate it!

---

## VFC Using Observational Data Progress

Since last week, I've been streamlining my codebase, writing a library of functions to facilitate different domains, combining and working with observational sources, and overall working out the kinks. I also had a meeting with Parker on Friday regarding code efficiency. A few takeaways:
1. Section timing is imperative to being able to make code sections more efficient.
2. Fancy indexing might be a helpful means of improving working with large grids.
3. Avoiding loading grids multiple times may be helpful.

Overall, there are a few issues I'm still working through:
1. Isolating clunky code segments and working through inefficiencies.
2. Using multiple sources, data types.
3. Easily creating datetime bounds.
4. Using pcolormesh with fancy indexing (note: G3 error).
5. FFMPEG - how do I slow down videos?

For now, I'll show some progress I've made in debugging. G2 now shows only segment values. I've ensured the method only uses i and j pairs within the appropriate segments, and that the surface-to-casts methods are re-assigning correctly for each time period. The following movie shows subthreshold thicknesses for DO < 5.0 mg/L calculated for month time-frames of CTD data from DFO during 2017 for segment G2.


<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f117c2d7-42fb-466d-a1f6-d92500b7c170" controls="controls" style="max-width: 800px;"></video><br>Fig 1. Subthreshold thicknesses for G2 given DFO CTD data throughout 2017.</p><br>

I've recalculated the time series of subthreshold volumes in the folliwing figure:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f1318037-cea0-48f8-bc0c-2133caa6009d" width="700"/><br>Fig 2. Subthreshold volumes for segments in the Strait of Geogia given DFO CTD data from 2017.</p><br>
  
As a note, I've expanded this process to using ecology data with success! I'll provide figures and videos asap.

Next steps are (still) as follows:
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
2. Organize literature - Endnote?
3. Figure out what to do about CEE 462.
4. Work out ffmpeg timing kinks.

### Looking Ahead:
1. More VFC with observations.
2. KC materials draft by end of week.

### Goals For This Week:
1. KC materials.
2. More VFC with observations.
