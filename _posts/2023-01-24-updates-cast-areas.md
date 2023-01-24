# Updates + Finding Cast Areas

### Goals From Last Week:
1. Implement LO cast area-finding routine - using cKDTree.
2. Next: hypsography (e.g., hypoxic volume, average DO concentration in areas)!

### Completed Goals:
1. Working through cKDTree.

---

## Updates Since Last Full Group Meeting

*Primary Goal:* Using observational data, understand trends in dissolved oxygen and associated state variables over time in the Salish Sea.

*How I'll Do This:* Using available CTD cast and bottle data, create hypsographic (volume-based) estimates of state-variables.

For the past several months, I have been learning the tools available (LO, python as a whole, observational data sets, etc.) The first step in the direction of my primary goal is to understand data structures and formats, in particular CTD casts and bottle data obtained by a variety of groups.

Focusing first on DFO data in the Strait of Georgia, I started with a clean sandbox: using LO casts instead of observational data. This allows a "check" - I can use LO data to check my estimates of state variables since LO has all available state variable data.

First, I learned how to extract state variables from LO, looking at selected dates and trends over time:

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/207697706-a5c0cddc-41b9-44d4-88f7-7c4328fe20be.gif" width="400"/><br>Fig 1. Bottom dissolved oxygen from LO from 11/15/2022 through 11/30/2022, all at 01:00 UTC.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/207698439-2579f9e9-7ddd-47ed-a1da-0bef34dad6b1.png" width="600"/><br>Fig 2. Total hypoxic volume (< 2.0 mg/L) from LO from 11/15/2022 through 11/30/2022, all at 01:00 UTC.</p><br>
  
<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/207698500-8cde9f3d-4cd6-455c-956a-b256a5163536.png" width="600"/><br>Fig 3. Average DO concentration from LO from 11/15/2022 through 11/30/2022, all at 01:00 UTC.</p><br>

Then I learned how to extract "observational-esque" casts from LO. These will serve as my test casts, which I can compare to LO output. In this case, I've used a selected year of DFO data (2019) and applied it to one history file within LO, for ease of use on a local machine.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/212983887-0f7a8874-f3aa-4235-a633-00e1dd5b388c.png" width="900"/><br>Fig 4. Sample LO casts from DFO locations near the San Juan Islands during 2019 using an LO history file for 11/30/2022 01:00 UTC. Cast locations, surface temperature and salinity vs. bottom temperature and salinity (blue and orange, respectively, subplot 2), and dissolved O2 with depth are shown. </p><br>

Now, I'm working on an algorithm that can find the nearest cast to each LO grid point. This will enable me to extend cast attributes to an area and volume of the model. Using these methods, I hope to be able to create lovely plots such as these:

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/214405473-379d709d-1758-467f-8cf3-6215d060c9c5.png" width="600"/><br>Fig 5. Sample plots from various sources (indicated) regarding Baltic Sea hypoxia using hypsographic methods. </p><br>


## Using cKDTree (This Week)

From last week, using LO grid as the basis for area estimation with model or observational data is a good starting point; it allows easy indexing with gridcells and fairly high-resolution bathymetry. To find the closest cast to each grid cell (to find an area to which cast data applies), we discussed the use of KDTrees.

KDTrees are mathematically fascinating and complex, it turns out! They are a space-partitioning data structure that is good at nearest-neighbor searches, which should be well-suited for this application. However, I have not yet been able to implement it. Below I'll talk through some of my work.

Starting with "example_cKDTree_extract.py", I have begun learning how to use this tool. I can run cKDTree as shown, filling an array with masked (missing) values with each values nearest neighbor.

However, I've found that this simple algorithm doesn't have the spatial robustness I expected. In the output below, one can see that instead of filling with the closest values in any direction, the output filled with the nearest value in the columnar-direction.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/214395565-8bf0f266-b202-451d-bed5-aeb0a3b611f3.png" width="300"/><br>Fig 6. Snippet from cKDTree example output.</p><br>

This indicates that there is (most likely) an argument that indicates dimension of closet neighbor and/or the algorithm struggles at smallest distances to the nearest neighbor. This may make sense given the KDTree algorithm (using hyperplanes to partition tree space closer to the queried point, which may not be super precise at close neighbors).

I also looked for lat/lon specific applications of the cKDTree (instead of solely focusing on indices) in case that provided an easier pathway. I found a few examples of finding points within a certain distance of a reference point, including as shown in the figure below from another grad student's blog. They are specifying a point on a lat/lon grid and using "KDTree.query_ball_point" to find grid points within 30km of the reference point. It's a similar and useful application with reference code.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/214397054-074d5c3e-d119-4d7a-be23-ad711d6e7592.png" width="300"/><br>Fig 7. Example using KDTree.query_ball_point (finding points within a certain distance on a lat/lon grid) from http://qingkaikong.blogspot.com/2017/12/use-k-d-tree-to-query-points-part-2-use.html.</p><br>

Now, using LO grid, I'm working with the "G1" segment and all casts in that segment from 2019. This should prove a good test space, including the hurdle of having a built-in "land mask."

In trying to implement the algorithm on my end as of today, I'm running into the following (resolvable) issues...
1. Does the i_dict and j_dict account for the land mask?
2. Generally, using the segmentation indices and cast indices. I'm getting lost in the weeds, but I can fix this in time. I'm hung up on translating between lists of indices and 2D arrays without losing important information. Realistically, I just need to learn python/numpy data structures more thoroughly. A few houghts below:
   * Converting from i_dict/j_dict for segments to 2D arrays while maintaing land mask (or, reapplying land mask later)
   * How to implemented masked array of same size with just casts? Using numbers as cast-area indicators?
   * If this works, how to apply back to LO grid (i.e., take 2D array and convert back to indices)
3. In writing this and creating plots, I just realized that I have nearly overlapping casts. I will first omit overlaps to get the algorithm running to avoid issues with "too-near" neighbors.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/214398163-7b4c7c83-5fb4-46ad-85f8-ffafeda61246.png" width="300"/><br>Fig 8. Casts in segment G1 (2019 DFO reference year).</p><br>



---

## Bookkeeping 
* KC Meeting scheduled for Friday, February 17, 2023
* EFM Talk scheduled for Thursday, March 2, 2023 (20 minute presentation).
* Quarter Planning...(in progress)
  * Remaining from last quarter:
    * Come up with estimation scheme using LO data.
  * Dig into obs data.
* Gordon Conference Abstract - tracking mid-February for draft.


---

### Issues/Questions:
1. 

### Looking Ahead:
1. Implememnt LO cast area-finding routine using cKDTree.
2. Next: hypsography (e.g., hypoxic volume, average DO concentration in areas).
3. 

### Goals For This Week:
1.
