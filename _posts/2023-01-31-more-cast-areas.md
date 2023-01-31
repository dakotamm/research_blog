# More Finding Cast Areas

### Goals From Last Week:
1. Implememnt LO cast area-finding routine using cKDTree.
2. Next: hypsography!

### Completed Goals:
1. Implement KDTree

---

## Using KDTree

This week, I was able to implement the KDTree to assign LO grid area to LO cast locations. KDTree uses a nearest-neighbor algorithm to find the index of the closest neighbor of a certain gridcell.

Using the DFO data to inform cast locations, Parker's cKDTree example, and a lot of time parsing McKinney's Python indexing section, I was able to get the KDTree to run on the LO domain. For this initial implementation, I first removed any duplicate sampling sites for now (i.e., restricting the temporal domain such that each location is unique). Then I used masked arrays to create a "target" tree (a 2D array with land mask) and a "query" tree (a 2D array with only cast locations unmasked). Then I was able to assign each gridcell the value of its nearest neighbor (in this case, the arbitrarily cast number). In all, there are 14 casts and now 14 segments of the "G1" domain segment, shown below.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/215870976-a2f8f81f-f153-43c0-ab37-a1e664f4fb00.png" width="900"/><br>Fig 1. KDTree assigning areas to (14) cast locations in G1 segment.</p><br>

The main issue is that, while the "land mask" is expressed throughout the process, the KDTree query seems to ignore it. Assigning water in bays (e.g., Deer Harbor at Orcas Island) is nonphysical and thus is a problem with using this algorithm to assign water quality observations to specific water volumes. While I don't believe KDTree can do this, the most logical way to do this would be to specify the algorithm must "go around" masked areas.

Some discussions and unrelated learning brought me to the world of Voronoi tesselations... They are useful in unstructured space (which would be trickier to mesh with our LO grid-based approach). But there seems to be some literature/internet knowledge on how to work around obstacles when assigning a polygon to a point.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/215873002-099b9732-1b85-47b5-adac-a19f5db837e1.png" width="400"/><br>Fig 2. Voronoi tesselation from https://en.wikipedia.org/wiki/Voronoi_diagram.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/215873963-468d510c-c703-40fd-b304-9be7dcab3f21.png" width="400"/><br>Fig 2. Voronoi tesselation avoiding obstructions from 
https://stackoverflow.com/questions/51708955/centroidal-voronoi-tesselations-around-obstacles.</p><br>

Some points of discussion: 
1. Ways to specify path around "land mask" for nearest-neighbor finding...Voronoi tesselations? That seems to abandon the LO grid approach.
2. At what point am I spinning my wheels in the algorithmic details? Not yet, I don't think, but I want continue conversations about how to prioritize effectively.

---

## Bookkeeping 
* KC Meeting scheduled for XX, February XX, 2023
* EFM Talk scheduled for Thursday, March 2, 2023 (20 minute presentation).
* Quarter Planning...(in progress)
  * Remaining from last quarter:
    * Come up with estimation scheme using LO data.
  * Dig into obs data.
* Gordon Conference Abstract - tracking mid-February for draft.
  * I may have a conflict with Sunday/Monday of conference dates.

---

### Issues/Questions:
1. Checking in - am I going the right direction with all of this?
2. DFO data - should I continue to clean/work on this?

### Looking Ahead:
1. Figure out nearest-neighbor with obstacle avoidance, if possible, for assigning LO areas to casts.
2. Next: hypsography!

### Goals For This Week:
1.
