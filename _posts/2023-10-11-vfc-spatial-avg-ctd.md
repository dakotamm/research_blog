# Improving VFC Spatial Averaging - Continued Again

### Goals From Last Meeting:
1. Fix TEF sections bug discussed last week!
2. Read Moore et al. (2008).

### Completed Goals:
1. Bug fixed.
2. Read Moore et al. (2008).

---

## VFC Spatial Averaging

### Bug Fixing

Last week I discussed a hurdle using TEF segments for VFC where despite checking through an averaging scheme, I had odd values (sometimes negative) for state variables (see previous post for more detail). This was due to the using np.empty() to create initialize a matrix, which uses random numbers to fill. Thanks Parker for finding this and helping me get through! Here's a plot of some variable filling in the Salish Sea that I was able to generate after my bug was squashed.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e667f659-f1e7-41b3-bde4-b26c16a965fe" width="400"/><br>Fig 1. Surface sigma layer DO fields [mg/L] using new VFC scheme with TEF segments.</p><br>


### Prioritizing 2013 Initial Conditions and Robust Code

Yesterday, Parker and I met for a very fruitful code review. We discussed the goal of using initial conditions calculated from observations in a well-vetted manner to create an LO hindcast starting in 2013. This is my highest priority at the moment, and will ideally require few more steps of code development before vetting calculated initial conditions. Of course, the code I develop is equally applicable to VFC and observational data analysis, and so this task is beneficial for all of my workstreams.

Additionally, we discussed making my averaging scheme a bit more robust. As discussed in some depth, my current averaging scheme creates arrays for every cast within each segment and time period, sums the values in each gridcell, and then divides them by the number of casts (a weighted average). While this is a simple average, it may not be the most logical or robust way to calculate an average conditions within a segment. Some improvements to the code from yesterday's discussion to be implemented are as follows:

1. Instead of individual TEF segments, use **regions**. This will allow all regions to be filled for the purposes of initial conditions:
   * Northern Strait of Georgia
   * Southern Strait of Georgia (including San Juan Islands)
   * Strait of Juan de Fuca
   * Main Basin (including Admiraly Inlet)
   * Whidbey Basin
   * Hood Canal
   * South Sound (including Tacoma Narrows)
2. Use bottle cast data only for simplicity and prioritize the following variables for initial conditions:
   * Temperature
   * Salinity
   * DO
   * NO3
   * NH4 (if enough information at depth)
   * DIC (if enough data)
   * TA (if enough data)
   * Else: 0 initial fields
2. Create an average cast within pre-defined depth bins (in lieu of binning based on cast depths themselves). If there are unfilled bins, interpolate between bins. Maintain shallow casts (i.e., don't exclude on basis of not casting to full depth of the water column).
3. Map the bins onto gridcells for each region.
4. Potentially expand time range if not enough data available for initial conditions.
5. Review plots of all casts in region/time period vs. average calculated cast.

This will be a process of refinement as code improvements are made. Ultimately, these improvements will allow an effective and realistic initial condition for LO hindcasting starting in 2013.


---

## KCWASH + Taylor Meeting Next Week

Next week, we plan to host Taylor Martin (KC) at our monthly meeting with the broader UW group (including Mike and Ben). We had initially stated that we wanted her to rehash her CEE seminar presentation from April. I'd like to assemble an agenda this week to send to her with all of our input! **What other goals should we discuss during this meeting with Taylor?**

---

## CEWA 565 Class Project Research Opportunity

For my data analysis in water sciences class, there will be a term project that is intended to put our "new" stats skills to use. We can use our own research, and I certainly intend to do so. I have a few ideas in terms of research questions that may fit the bill, but if there's something that would be more immediately important to the project (that's still the size of a class project), I'm happy to consider that. I'm thinking along the lines of:
1. Has bottom oxygen changed over time in Puget Sound/Salish Sea? (I'm thinking of the "declining trend" reported in the [2019 Salish Sea EPA Report](https://www.epa.gov/salish-sea/marine-water-quality#:~:text=Marine%20dissolved%20oxygen%20levels%20continue,areas%20in%20the%20Salish%20Sea.); I could perform some simple stats using all our data to understand if there's a difference in mean bottom DO before 2010 and after.)
2. Same as above, but hypoxic volume.
3. Pick an indicator (like rainfall, river flow) and determine covariance with a state variable like DO.

---

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
1. Build code and initial first-pass of initial conditions for 2013 run.
2. Read new paper.
