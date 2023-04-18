# VFC Domain Expansion and Understanding Spatial Errors

### Goals From Last Meeting:
1. Quals studying...
2. Debug/build out VFC code, expand to all domains/datasets.
3. Create more efficient scripts especially for cast extraction/working with larger domain - meet with Parker as necessary.

### Completed Goals:
1. Quals studying - ongoing.
2. Debug/build out VFC code, expand to all domains/datasets.

---

## VFC Domain Expansion Debugging

From last meeting, I was able to rectify bugs that prevented expanding my domain from the Strait of Georgia to the Strait of Juan de Fuca using DFO CTD cast locations conducted during June 2019. The bug was a simple and silly hardcoded error which was pulling legacy filenames.

Now I can compare errors between the VFC method and LO output in both the Strait of Georgia and Strait of Juan de Fuca using DFO CTD locations, using a subthreshold volume for oxygen as 4.0 mg/L and casts from DFO locations during June 2019. Like previous studies, I've taken casts from LO history files on the first of each month throughout 2022.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228325464-b0bf802a-86a8-4de4-b734-02f9a7daab82.png" width="300"/><br>Fig 1. LO segments in Strait of Georgia and Strait of Juan de Fuca.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/231269507-7f9b8bd4-5994-4d9b-b0e7-f9f2d02a5605.png" width="800"/><br>Fig 2. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. RMSE is shown for each segment in the Strait of Georgia.</p><br>

Et voilà - the same analysis in the Strait of Juan de Fuca!

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/232883599-46348c57-ac78-4e75-88ec-88021057f011.png" width="800"/><br>Fig 3. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. RMSE is shown for each segment in the Strait of Georgia.</p><br>

---

## VFC Preliminary Spatial Error Analysis

Given I can conduct error analysis on all segments within the DFO region, I have plotted the error for each segment as compared to other segments. Shown in Figure 4 are the normalized RMSE and the locations of each cast used. This uses the same study method as described above.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/232884693-162ea12c-4dad-4235-b574-a7a8c383133f.png" width="800"/><br>Fig 4. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. Normalized RMSE is shown for each segment in the DFO region; cast locations are also shown.</p><br>

A few thoughts:
- 'G5' segment is oddly shaped!
- Correlation with number of casts not clear?
- Correlation with bathymetry?
- Overlapping casts handling

I've also taken a foray into other datasets, specifically ecology CTD locations for the summer of 2019 (June through August). I conducted the same analysis to get normalized RMSE, applied to LO history files for the first of each month during 2022.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/232887491-f90ada41-c441-4723-b387-7a5c780f1a7b.png" width="800"/><br>Fig 5. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. Normalized RMSE is shown for each segment in the Ecology Hood Canal region; cast locations are also shown.</p><br>

We see there is similar predictive capabilities in Hood Canal and in the DFO region given the graphical comparison. However, it is clear that the sparse and overlapping cast data in Hood Canal provides less spatial coverage per unit segment area. In absolute spatial terms, however, the distribution of casts seems similar between the two domains. More analysis to follow...

As noted last meeting, I'm feeling limited by the slowness/clunkiness of some of my codes. This will require some thought, so as to be able to efficiently conduct large scale analyses.

Next steps are as follows:
1. Continue to build robust VFC toolbox - ESPECIALLY code efficiency.
2. Understand and incorporate other data sources (including revised DFO, NCEI, DOE, etc.).
3. Start working with time variability of casts...
4. Onto actual observerational data...

---

## Bookkeeping 
* WWU Lecture - scheduled for Friday, 5/4/2023
* Quals: April 24-28, 2023 - oral defense Friday, 4/28/2023 at 10am
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods - need lit. review.
2. Figure out comments section on blog!!!
3. Gordon Conference poster timeline...
4. Weird G5 segment.
5. Code slowness.

### Looking Ahead:
1. Quals next week!!!
2. Cleaning/improving VFC codebase as time allows.

### Goals For This Week:

