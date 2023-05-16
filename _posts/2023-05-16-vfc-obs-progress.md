# VFC Using Observations Progress

### Goals From Last Meeting:
1. More VFC with observations (plot updates including casts, cast regions, video).
2. Parker meeting for code efficiency.
3. GRC poster + KC presentation planning.

### Completed Goals:
1. More VFC with observations (plot updates including casts, cast regions, video).
2. Parker meeting for code efficiency.

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


<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f117c2d7-42fb-466d-a1f6-d92500b7c170" controls="controls" width="800"/><br>Fig 1. 2017 VFC subthreshold thickness for G2, 5 mg/L DO.</p><br>

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
3. Organize literature - Endnote?
4. Figure out what to do about CEE 462.

### Looking Ahead:
1. More VFC with observations.
2. KC materials draft by end of week.

### Goals For This Week:

