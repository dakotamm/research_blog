# Improving VFC Spatial Averaging

### Goals From Last Meeting:
1. Dive into spatial averaging in VFC method - toward constructing climatologies and understanding interannual variation. This requires a significant code rewrite.
2. Meet with UBC on 9/20.
3. Read Scully 2013.

### Completed Goals:
1. Dived into spatial averaging in VFC method - toward constructing climatologies and understanding interannual variation. This requires a significant code rewrite.
2. Met with UBC on 9/20.
3. Read Scully 2013.

---

## VFC Spatial Averaging Efforts

Last week, we talked at length about the usefulness of 2017 intial conditions built using VFC methodology, and spatial averaging and resolution challenges inherent in my VFC method. For the former, we decided that a two-month time window (as has been used) likely doesn't capture enough data, particularly in deep areas with long-residence times (e.g., Strait of Georgia). We discussed a few methods to improve this with the existing codebase:
1. Increase the size of the time-window to capture more data (higher spatial resolution, lower temporal resolution).
2. Create climatological initial conditions:
   * Perform the method for all "Decembers", say.
   * Perform the method for all years.
   * Weight the climatological "December" by statistics derived from interannual variations.
  
All of this, however, may be but bandaids. The latter portion of the discussion focused on spatial averaging and resolution challenges in the VFC method, and how to improve that. We discussed that the current method segment the 2D surface domain into nearest-neighbor partitions using the specific cast locations in that bin. This, at the time, was the most logical way to assign discrete cast values to three-dimensional space. However, given the structure of the current codebase, there are a few challenges:
* The nearest-neighbor code is fairly slow, especially if we deal with many segments and many time bins.
* The nearest-neighbor code works within a specified segment. This means that the domain has to be bounded using i/j indices. Larger domains with more casts run slower.
* The surface partitioning uses individual cast numbers and locations, which also corresponds to the data applied for each partition. Currently, if two casts exist in the same location within a specified time bin, the latter cast overwrites the former. Effectively, the data from the first cast is lost.
   * Note: In the case of the initial conditions for 2017, this was not the case; there were no repeated casts.
* There is not interpolation between partitions.
* There is no extrapolation of data at depth - if a water column in a partition exceeds the depth of its representative cast, then the deepest value of the cast is applied for all depths below.

So - there are some significant drawbacks to the code (as expected in a first attempt). We brainstormed a few additional concepts:
1. Use an "average spatial segmentation" - perhaps from an entire years worth of casts or monthly climatology. This avoids the redrawing step.
2. Use pre-allocated segments (such as TEF) and average the field within each segment.
3. Using pre-allocated segments, one could "combine" segments if one had insufficient data.

In all of these cases, the spatial averaging issue (i.e., what to do when casts overlap each other) must be rectified!

In order to wrap my head around all of these ideas, I created a rough concept map for myself. Wade into my thought processes at your own risk.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3405720a-38fe-46d1-85e6-72e5340d0876" width="800"/><br>Fig 1. Mapping possible options for VFC spatial handling.</p><br>

For this week, I've focused on optimizing **Option 1** since the code exists and I would like to have the option to use nearest-neighbor finding. Also this issue has been bugging me for awhile and I'd like to bring it full circle with this current codebase. That being said, I see many advantages of Option 2; perhaps killing my darlings will be a better choice.

For spatial averaging in Option 1, I've used a fairly "non-invasive" option of creating pseudo-casts for surface partitioning, then applying averaged to that partition. I'm still working out some kinks and will have more to show later this week.

Regardless of the direction chosen, we'll need to rigorously assess how the method performs. From our conversations last week, I will compare these modeled casts to the observational data, especially as spatial averaging is applied.

---

## Notes on UBC Meeting

Last week, I met with Tall and Susan at UBC to introduce myself to Tall and understand Tall's work and scope. Briefly, they described that he's working to rectify some issues they're seeing with oxygen overprediction in Saanich Inlet and Hood Canal specifically, especially understanding whether physical or biogeochemical models are "out of tune".

I was able to provide our Ecology CTD casts so as to inform their observational database. Susan recommended the following sources for us to add to our list:
1. Pacific Salmon Foundation (citizen science, data only down to 100 meters but twice monthly during salmon seasons)
2. Broadly - CIOOS Pacific (looks like a lot including BC ferries data?)

Overall, good to meet Tall and connect with our Canadian colleagues.

---

## Questions Toward Paper 1

Leaving this on here for posterity:

1. Is there an observable multi-decadal trend in DO throughout the whole Salish Sea?
   * So far, we've seen that there is really sparse data (in current datasets) before the 2000s. With this data, we can't really make out an upward or downward trend in the Salish Sea as whole, or in the Strait of Georgia, Strait of Juan de Fuca, and Puget Sound as a whole.
2. Are there observable multi-decadal trends in DO throughout different regions? How do regions compare and contrast in DO trends?
   * We DO see some variation since 2000; however, the trend is increasing DO peaking at 2012 and then a decrease. Some regions seem to show a slight decline since 1999 (like South Sound) and some regions show a "mountain" pattern (like Hood Canal).
3. Does DO co-vary with temperature, salinity, NO3, etc.? What are the most significant predictors of DO, if there are any?
4. What's the correlation between environmental indicators and events (i.e., the Blob, PDO, ENSO) that correlate with these trends?
5. Are there significant events that warrant further study, like the Blob?
   * 2015 seems less spicy than anticipated so maybe!

---

## Bookkeeping 
* Classes start this week: Mike's limnology class and data analysis in water sciences.
* Taylor participating in group meeting on Wednesday 10/18.

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. CTD/bottle duplicate DO in ecology set - clean this in VFC (output not affected, only number of casts included).
3. Weird "1-cast = np.nan hyp_vol" issue comes up on 4/2017, 5/2019, and 6/2019. May be an averaging problem.
4. Data cleaning (1950 DO concentrations).
5. Write VFC-specific command-line tags.
6. Weighted averages are not doing a linear interpolation between gridcell depths yet.
7. Averages below threshold depth are only written for obs data so far.
8. Write plotting functions.

### Looking Ahead:
1. Finish spatial averaging scheme in existing VFC method.
2. Explore other options for spatial averaging.
3. Create monthly and annual climatologies for gridded state variables.
4. ORCA buoys - incorporate this into trend analysis ASAP.
5. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.

### Goals For This Week:
1. Move ahead with Option #2 - use TEF segments in existing VFC method.
2. Confirm audit version of CEWA 562.
