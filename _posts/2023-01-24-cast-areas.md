# Finding Cast Areas

### Goals From Last Week:
1. Implement LO cast area-finding routine - using cKDTree.

### Completed Goals:
1. Working through cKDTree.
2. Attended Puget Sound Institute meeting regarding model underpredication of stratification.

---

## Using cKDTree

Starting with "example_cKDTree_extract.py", I have begun learning how to use this tool. I can run cKDTree as shown, filling an array with masked (missing) values with each values nearest neighbor.

However, I've found that this simple algorithm doesn't have the spatial robustness I expected. In the output below, one can see that instead of filling with the closest values in any direction, the output filled with the nearest value in the columnar-direction.

![image](https://user-images.githubusercontent.com/55995675/214395565-8bf0f266-b202-451d-bed5-aeb0a3b611f3.png)


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
1. Figure out of cKDTrees will work in this application.

### Goals For This Week:
1. Impelement LO cast area-finding routine - using cKDTree.
2. Track 1-month for Gordon Conference abstract draft.
