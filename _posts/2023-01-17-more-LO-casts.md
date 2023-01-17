# More LO Casts

### Goals From Last Week:
1. Use segmentation in lieu of lat/lon bounding for segmenting LO grid. 
2. Investigate methods to determine "cast" area.
3. Starting with DO, get volume-based average DO + hypoxic volume measurements + compare to LO grid "source-of-truth" (with error estimation).

### Completed Goals:
1. LO casts using proper segmentation.
2. Investigated GeoPandas as option for assigning area to cast (potentially more complex than using LO grid methods, see below).

---

## Using Segments for LO Casts in the Strait of Georgia

From last week, I modified my LO cast scheme to use proper LO segments and use Parker's new "fast" cast function. I have been able to pull all casts in the Strait of Georgia region using 2019 as the dfo lat/lon database and a given history file (01:00UTC on 11/30/2022) as the LO grid and basis of data.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/212982815-3b128424-ee1b-4683-84be-3d0bfdaec0d9.png" width="900"/><br>Fig 1. Sample LO casts from DFO locations during 2019 using an LO history file for 11/30/2022 01:00 UTC. Cast locations, surface temperature and salinity vs. bottom temperature and salinity (blue and orange, respectively, subplot 2), and dissolved O2 with depth are shown. </p><br>

This functionality allows me to segment further into smaller, more usable areas for initial volume-estimation method development. Below is segment "G1" which corresponds to the San Juan Island region.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/212983887-0f7a8874-f3aa-4235-a633-00e1dd5b388c.png" width="900"/><br>Fig 2. Sample LO casts from DFO locations near the San Juan Islands during 2019 using an LO history file for 11/30/2022 01:00 UTC. Cast locations, surface temperature and salinity vs. bottom temperature and salinity (blue and orange, respectively, subplot 2), and dissolved O2 with depth are shown. </p><br>


## Finding Cast "Areas"

The next step in the process toward volume-based estimates is getting the area attributable to each cast (in this case, casts on the LO grid). While using the LO grid data, Parker recommended an adaptable routine which can find the cast closest to each gridcell. This seems a useful solution using the LO grid.

When extending the volume-based estimates to observational data, I have begun to look at a package called GeoPandas, which extends pandas for robustness with geodetic data. A specifically interesting functionality is that it easily computes the centroid of a given area in lat/lon space. Ideally, the reverse of this process would be useful - i.e., given centroids, find areas.

This is one method I'm looking into; otherwise, I can potentially apply the same method using the LO grid for both LO casts and obs casts, or draw polygons via a different method.

For the upcoming week, I will:
1. Implement a routine to assign LO gridcells to nearest casts and determine area.
2. Investigate methods that are not reliant on the LO grid.

---

## Miscellaneous/Bookkeeping 
* EFM Talk scheduled for Thursday, March 2, 2023 (20 minute presentation).
* Quarter Planning...(in progress)
  * Remaining from last quarter:
    * Come up with estimation scheme using LO data.
  * Dig into obs data management.
  * Prepare for KC meetings.

---

### Issues/Questions:
1. Segments - is the entire LO domain assigned segments?
2. DFO data curation - leave to Kate & Parker?

### Looking Ahead:
1. Impelement LO cast area-finding routine.
2. Investiage area finding methods that aren't reliant on LO grid (if that makes sense).

### Goals For This Week:
