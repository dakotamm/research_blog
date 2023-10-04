# Improving VFC Spatial Averaging - Continued

### Goals From Last Meeting:
1. Move ahead with Option #2 - use TEF segments in existing VFC method.
2. Confirm audit version of CEWA 562.
3. Read Sutton et al. (2013).

### Completed Goals:
1. Move ahead with Option #2 - use TEF segments in existing VFC method.
2. Confirm audit version of CEWA 562.
3. Read Sutton et al. (2013).

---

## VFC Spatial Averaging - Option 2

Last week, I laid a roadmap for potential improvements to VFC spatial averaging schemes. In particular, I laid out three code architecture options. I had previously been working to implement Option 1 (using nearest-neighbor domain segmentation per spatiotemporal bin) with spatial averaging. However, we decided that Option 2 (using pre-existing TEF segments as spatial bins) allows greater comparison means of temporal comparison and potentially greater code efficiency.

I have worked the last week to try to get Option 2 up and running, which was a significant code architecture debate. I think I'm on the right path, BUT I have some hurdles remaining before I show results.

### Code Architecture Explanation

Though the change seems simple, I did a fair bit of thinking to get this running efficiently. The domain is divided into 37 segments per the TEF workflow, which are given by arrays of i and j indices. For the purposes of this example, say I've binned for April 2017 for segment J1 (in the Strait of Juan de Fuca). There are over 2000 individual surface cells in this segment, all with 30 sigma layers. There are three casts taken in this bin.

The architecture I've chosen to tackle this (after exploring several options) is creating weighted averages iteratively using a mask for bins based on cast depths. I've created depth bins based on each individual cast, and then create a mask for the array of i/j indices that make up a segment where the depth of the gridcells masked is within that bin. Iteratively, I can add the arrays built by binning and masking for each cast, and then take an average at each element. This is fast and *seemingly* reliable. (This option avoids making an "average" cast given varying sampling depths and large matrix manipulations.)

### Hurdle 1 (Bug)

Unfortunately, I have run into a hurdle with this code architecture. For some reason, I'm getting negative average values when I add values binned and masked for each cast then divide by the number of casts. I have checked that all values are positive and that no gridcells are unmasked (by design). This is SUPER odd and only occurs after several iterations. I believe this is a **copy vs. deep copy** issue (love those), and I have not yet debugged it.

### Hurdle 2 (Upcoming)

The next hurdle I anticipate after debugging Hurdle 1 is how to fill "cast-less" segments - or what options should be incorporated. We've talked about a few so far:
1. Create bigger segments (basin-sized).
2. Combine segments without data with filled segments.
   * Combine with next segment (in dictionary order), unless end segment?
   * Combine with two closest segments, if within the same basin (otherwise just one).
   * What if there are multiple segments without data?
3. Interpolate between adjacent filled segments (requires adjacent filled segments).

### Meta-Goals:

After soaring over these two hurdles, I remind us of some of the bigger goals this code architecture change will help me accomplish:
1. Create initial conditions based on observations for model runs that are more realistic than previous code architecture (excluded a lot of data areas given sparse resolution).
   * Spefically and additionally - create climatological initial conditions:
     * Perform the method for all "Decembers", say.
     * Perform the method for all years.
     * Weight the climatological "December" by statistics derived from interannual variations.
2. Apply to observational record and evaluate trends in volume-based state variables in a more systematic way than previous VFC architecture.
3. Nice, tidy, usable codebase :D.
4. (sort of goal) Confirm this all performs well compared to previous VFC architecture and observations.

Stay tuned...

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
* Fall Quarter Classes: "auditing" Mike's limnology class (CEWA 562) and data analysis in water sciences (CEWA 565).
* Taylor participating in group meeting on Wednesday 10/18.

---

### Looking Ahead:
1. Finish spatial averaging scheme in existing VFC method.
2. Create monthly and annual climatologies for gridded state variables.
3. ORCA buoys - incorporate this into trend analysis ASAP.
4. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
5. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
6. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/) Puget Sound Institute article Parker pointed toward me...)

### Goals For This Week:
1. Finish spatial averaging scheme in existing VFC method.
