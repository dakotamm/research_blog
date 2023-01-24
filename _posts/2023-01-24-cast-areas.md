# Finding Cast Areas

### Goals From Last Week:
1. Implement LO cast area-finding routine - using cKDTree.

### Completed Goals:
1. Working through cKDTree.
2. Attended Puget Sound Institute meeting regarding model underpredication of stratification.

---

## Using cKDTree

KDTrees are mathematically fascinating and complex, it turns out! They are a space-partitioning data structure that is good at nearest-neighbor searches, which should be well-suited for this application. However, I have not yet been able to implement it. Below I'll talk through some of my work.

Starting with "example_cKDTree_extract.py", I have begun learning how to use this tool. I can run cKDTree as shown, filling an array with masked (missing) values with each values nearest neighbor.

However, I've found that this simple algorithm doesn't have the spatial robustness I expected. In the output below, one can see that instead of filling with the closest values in any direction, the output filled with the nearest value in the columnar-direction.

![image](https://user-images.githubusercontent.com/55995675/214395565-8bf0f266-b202-451d-bed5-aeb0a3b611f3.png)

This indicates that there is (most likely) an argument that indicates dimension of closet neighbor and/or the algorithm struggles at smallest distances to the nearest neighbor. This may make sense given the KDTree algorithm (using hyperplanes to partition tree space closer to the queried point, which may not be super precise at close neighbors).

I also looked for lat/lon specific applications of the cKDTree (instead of solely focusing on indices) in case that provided an easier pathway. I found a few examples of finding points within a certain distance of a reference point, including as shown in the figure below from another grad student's (http://qingkaikong.blogspot.com/2017/12/use-k-d-tree-to-query-points-part-2-use.html).

![image](https://user-images.githubusercontent.com/55995675/214397054-074d5c3e-d119-4d7a-be23-ad711d6e7592.png)

This student is specifying a point on a lat/lon grid and using "KDTree.query_ball_point" to find grid points within 30km of the reference point. It's a similar and useful application with reference code.

Using LO grid, I'm working with the "G1" segment and all casts in that segment from 2019. This should prove a good test space, including the hurdle of having a built-in "land mask."

In trying to implement the algorithm on my end as of today, I'm running into the following (resolvable) issues...
1. Does the i_dict and j_dict account for the land mask?
2. Generally, using the segmentation indices and cast indices. I'm getting lost in the weeds, but I can fix this in time. I'm hung up on translating between lists of indices and 2D arrays without losing important information. Realistically, I just need to learn python/numpy data structures more thoroughly. A few houghts below:
   * Converting from i_dict/j_dict for segments to 2D arrays while maintaing land mask (or, reapplying land mask later)
   * How to implemented masked array of same size with just casts? Using numbers as cast-area indicators?
   * If this works, how to apply back to LO grid (i.e., take 2D array and convert back to indices)
3. In writing this and creating plots, I just realized that I have nearly overlapping casts. I will first omit overlaps to get the algorithm running to avoid issues with "too-near" neighbors.

![Figure 2023-01-24 114046](https://user-images.githubusercontent.com/55995675/214398163-7b4c7c83-5fb4-46ad-85f8-ffafeda61246.png)

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
