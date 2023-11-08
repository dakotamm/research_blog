# Initial Conditions Progress :) and Setback :(

### Goals From Last Meeting:
1. Incorporate new VFC spatial averaging into LO/forcing/ocn00 framework.

### Completed Goals:
1. VFC spatial averaging works with LO ocean forcing files!
2. Side Quest: Set up on apogee and klone.

---

## Initial Conditions Update

Last week, I presented an improved VFC spatial averaging method! As discussed, the next step was to incorporate this method into the LO architecture that creates LO forcing files. I was able to integrate my framework into my LO_user copy of "forcing/ocn00," pulling heavily from methods in my "VFC_functions", and produce preliminary initial conditions, which I sent to Parker on Friday so we could review simultaneously. I ran a (1)-month window and a (2)-month window (taking the time period a month before and after a target date, or two months before and after a target date; in this case, the target date was 1/1/2013). In these preliminary tests, I created an initial condition every state variable for which there was observational data available. If there was no observational data available for that variable in the region and time period, the "existing" initial condition was left in place. (This is the same as I've done before, just with this new method!)

At first pass, there was no redflags! However, in creating more in-depth plots to review the initial conditions and present them here, I found something strange... (suspense builds)...

To illustrate the issue, I'll represent the following plots that show all the *maximum depths* of casts for each variable, for each region, for each year, etc. Note that the "sorting" that puts each cast into their respective regions is based on the i/j indices, which is based on TEF segments, which are tied to the specific grid that is referenced when calling the function. In this case, I used **cas6**, for reasons I can get into but don't need to here. The following plots are relevant to an initial condition set to start 1/1/2013, thus I'm pulling months from both late 2012 and early 2013:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6232e137-51c8-45c4-95d6-be4fb4787b5d" width="300"/><br>Fig 1. Hood Canal casts with DO for 2012.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4bcf6f77-ae0f-4d61-a565-437e14a7c7fe" width="300"/><br>Fig 2. All casts with DO for 2013.</p><br>

Note the casts in December 2012 and January 2013 in each region!

Now, if I use the testing method I presented last week, I get a good match between the number of casts I expect to see in Hood Canal in December 2012 from Figure 1 and the casts that create an average for the region. Note this is also using **cas6**.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3b85659c-a404-4c31-bd45-c73eb9f4cf32" width="800"/><br>Fig 3. December 2012 average casts and cast locations for Hood Canal.</p><br>

To create the initial conditions, I used **cas7** initially, since I had built this method to be grid agnostic. However, an ominous plot gave me pause:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/510dc2c3-7121-484c-9fe7-4e41c0ed8d6e" width="800"/><br>Fig 4. 1-month window inital conditions for January 1, 2013 DO average cast and cast locations for Hood Canal using cas7.</p><br>

Hood Canal :( where are your casts?! Figures 1-3 indicate that there should be casts in Hood Canal during this time period. My first intuition was that perhaps my methods were not as grid-agnostic as I thought, so I tried the initial conditions with **cas6**...

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ae02fbf9-d526-42ea-b522-e3eca2b7c807" width="800"/><br>Fig 5. 1-month window inital conditions for January 1, 2013 DO average cast and cast locations for Hood Canal using cas6.</p><br>

There should be more than two casts! The plot thickens...

I identified this bug today and have not yet worked through it. I'm sure it's something silly I've created in implementing my methods into the forcing/ocn00 framework. I'll work through it and fix the cause this week, so I can proceed with evaluating the hotly-sought initial conditions. I'd love any thoughts anyone has, and can review in more detail if need be.

*Sidenote: The reason I'm using different grids is because I have legacy scripts that are using "exfun" (which doesn't support cas7), instead of "ffun". I haven't made my own "*fun" yet, but that would probably be a good idea given that it is contributing to my confusion here. (On another note, the reason that cas7 seems unsupported by exfun is because of the -g and -gtagex change. Is -g the way of the future? What are the reasons for using this differently?)


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
* KC Quarterly Review: 11/30
* Vacation: 12/18-12/22
* Ocean Sciences: 2/18/-2/23

---

### Looking Ahead:
1. Create monthly and annual climatologies for gridded state variables.
2. ORCA buoys - incorporate this into trend analysis ASAP.
3. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
4. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
5. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/) Puget Sound Institute article Parker pointed toward me...)
6. Penn Cove nitrogen budget with WWU + Penn Cove nested model...
7. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. Debug initial conditions.
2. Spend time on homework...
