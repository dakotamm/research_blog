# Bathymetry + Learning

### Goals From Last Week:
1. Reach out to Susan Allen regarding DFO data.
2. Review bathymetry datasets for volume-based estimates.
3. Reach out to Kate Hewitt/Greg Johnson for estimation schemes.
4. Pull in updated DFO dataset (from UBC group, now publically available).
5. Continue lit. review.

### Completed Goals:
1. Reached out to Susan Allen regarding DFO data.
2. Reviewed bathymetry datasets for volume-based estimates.
3. Reached out to Kate regarding estimation schemes.
4. Continued lit. review.

---

## LO Bathymetries

In reviewing bathymeteries and topographies used for LiveOcean, I found the following two bathymetries for the northern Salish Sea/Strait of Georgia. There are higher resolution bathymetries for Puget Sound, but these are the two I found applicable to the DFO study region. I'd like to select one of these bathymeteries for beginning to estimate state variables using DFO data.

The first appears to be from Salish Seacast's ERDDAP server, collected from: https://salishsea.eos.ubc.ca/erddap/griddap/ubcSSnBathymetryV17-02.html (in 2019, according to the README). The finest resolution is approximately 272m.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/201752591-c3548b67-334b-4efb-8f81-9463cab9032d.png" width="1200"/><br>Fig 1. Salish Seacast bathymetry (pulled 2019).</p><br>

The second is the "Cascadia_Gridded" dataset with most recent README in 2010. It's a combination of PSDEM, Cascadia USGS, and Smith-Sandwell Cascadia bathymetry. The finest resolution in the Strait of Georgia region is approximately 250m.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/201754363-11d66596-b92c-4cf1-97af-689ba5b23928.png" width="1200"/><br>Fig 2. "Cascadia_Gridded" (circa 2010).</p><br>

A few questions:
- When I find Salish Seacast's resolution - should I use the finest mesh in Strait of Georgia?
- Advantages to using LO-native grid (assuming that's Cascadia_Gridded)?

This should be easy to adapt down the line, but want a nice starting bathymetry!

**Note from Discussion**: The cas6 grid is what LO uses to run - we decided that would be the best bathymetry to use to allow easier comparisons from observational data to the model. We also discussed changing tracks slightly to start coming up with hypsographic methods to use LO output data in the region encompassed by DFO data (Strait of Georgia) - I'll have to start wrangling LO outputs and start to understand tidal-averaging, noting the "extact/lowpass" filters on current outputs. In parellel, I'll start to pull down DFO data from the CIOOS ERDDAP server and making that pretty.

## Literature Review

I've started pulling sources (and will put them on a UW student license of Endnote). So far, the following study areas look promising:
1. VIMS - lots of work on Chesapeake Bay hypoxic volume; substantially different bathymetry (Bever et al. (2019), CBEFS as a whole)
2. Gulf of Mexico (e.g., Scavia et al. (2019))
3. Baltic (e.g., Carstensen et al. (2014))
4. Strait of Georgia (esp. using and citing DFO data: Olson et al. (2018))

---

### Issues/Questions:
1. Parker's thoughts on conferences...
2. A little more literature review before reaching out to Greg Johnson (PMEL) - next week?

### Looking Ahead:
1. Confirm bathymetry.
2. Pull in DFO dataset from CIOOS Paciric ERDDAP server -> usable format.
3. Reach out to Greg Johnson if necessary (next week) - hold on this until I know more about these methods.
4. Continue lit. review.

### Goals For This Week:
1. Use cas6 (LO) grid - learn how to use/plot/etc.
2. Begin to understand LO daily output formats + lowpass tidal-averaging.
3. Bring down and organize DFO data from CIOOS ERDDAP server (take notes).
4. Get Endnote up and running.
5. Meet with Kate (scheduled for Tuesday, 11/22/2022).
