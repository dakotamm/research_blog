# Initial Conditions Troubleshooting

### Goals From Last Meeting:
1. Debug initial conditions.
2. Spend time on homework...
   
### Completed Goals:
1. Still working on debugging IC grid issue.
2. Need to do my homework :).

---

## Quick Summary of What I've Been Up

Last time I gave Ben and Mike a research update was too long ago (during the August King County debrief)! Briefly, I want to summarize what my goals and findings have been since then...

### Data Exploration After King County August Update

At the King County meeting, I presented some preliminary data analysis that evaluated DO trends similar to the [2019 EPA Salish Sea Marine Water Quality Report](https://www.epa.gov/salish-sea/marine-water-quality#:~:text=Marine%20dissolved%20oxygen%20levels%20continue,areas%20in%20the%20Salish%20Sea.). I also began the evaluation of seasonal and regional trends in bottom DO. Mike asked if I'd made any T/S plots for the region, so to round that out with Mike here, here's a brief review of preliminary T/S diagrams I made to explore the different T/S/DO correlations in Hood Canal (selected due to its hot discussion topics).

In these plots, I'm using 1999-2018 DOE CTD casts and NOAA NCEI OCADS bottle data (i.e., NANOOS and WOAC cruises conducted about 3x/year). These values represent monthly and regional averages of the average bottom 20% of each casts' maximum depth. Given spatiotemporal resolution variability, there are different numbers of cast that inform each one of these plots.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/97255b8b-a46d-4c99-a730-4c2a3e318c1b" width="500"/><br>Fig 1. Hood Canal T-S diagram with 1999-2018 data, colored by season and sized by [DO].</p><br>

This plot is really interesting for a couple of reasons. Briefly, fall has the warmest and saltiest bottom water and summer and spring seem to have the coolest and freshest bottom water! It seems that there is potentially a complex stratification interaction occuring, along with the possibility of deepwater intrusions. Potentially, Hood Canal may be acting as a three end-member system, with rivers, mixing, and deep-water intrusions potentially creating a complex interaction between temperature, salinity, and DO.

Breaking down this plot to see seasonal trends, I created T/S plot by season:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/9bfd7d20-b83d-4295-9455-8c896cd6a529" width="800"/><br>Fig 2. Hood Canal T-S diagram with 1999-2018 data, columns by season and colored by [DO].</p><br>

Without going into too much depth, this inspired us to look toward a more mechanistic understanding of Hood Canal, which should start with a literature review on my part (pending me having more bandwidth!). This furthered discussion toward my first paper (as well as my General Exam, targeting Spring next year...). Here are some science questions that this data exploration initiated, which may serve to form a paper:

1. Is there an observable multi-decadal trend in DO throughout the whole Salish Sea?
   * So far, we've seen that there is really sparse data (in current datasets) before the 2000s. With this data, we can't really make out an upward or downward trend in the Salish Sea as whole, or in the Strait of Georgia, Strait of Juan de Fuca, and Puget Sound as a whole.
2. Are there observable multi-decadal trends in DO throughout different regions? How do regions compare and contrast in DO trends?
   * We DO see some variation since 2000; however, the trend is increasing DO peaking at 2012 and then a decrease. Hood Canal, however, shows different trends than Main Basin - how do these compare and contrast?
3. Does DO co-vary with temperature, salinity, NO3, etc.? What are the most significant predictors of DO, if there are any?
4. What's the correlation between environmental indicators and events (i.e., the Blob, PDO, ENSO) that correlate with these trends?
5. Are there significant events that warrant further study, like the Blob?

I have not spent time since late summer on observational data analysis, but I would love to pick this back up soon!

### Pivot to LO Initial Conditions

After this initial data analysis, we decided that I would spearhead a brief detour in my data analysis and work on LiveOcean initial conditions to create a new "baseline" 2017 model run alongside Aurora's traps integration. My goal was to apply my VFC (volume-from-casts) framework to fill state variables (i.e., salt, temperature, DO, NO3, NH4, DIC, and TA) from more observations. Previous initial conditions relied on only Ecology observations within the Salish Sea. Building this took some time, but I was able to create initial conditions using windows around January 1, 2017. However, the spatiotemporal resolution of casts especially during winter months and in large areas such as the Strait of Georgia led to questionable initial conditions. Also, the code architecture (VFC) was questionable for this application...

### VFC Refinement

Part of creating these initial conditions elucidated some issues that arise with my VFC method that I've spent some time the last year developing. In particular, I was unable to easily capture overlapping casts (more detail can be found in previous blogposts...) and the method was fairly inefficient, as each different spatiotemporal segment required a new nearest-neighbor search to be performed and the grid to be uniquely segmented. This created different grid partitions which led to more gappy initial conditions (i.e., sections missing data given data low data availability) and data loss if casts were overlapping in a given period (say, using two-month windows where Ecology samples monthly in the same location!). So, I spent time rewriting my VFC method to use Parker's TEF segments and create static grid segmentation (that is, temporally constant).

Additionally, this refinement uses linearly interpolated "average" casts for each spatiotempoeral segment. These average casts are depth-binned averages of all casts in within the given spatiotemporal segment. For example, here's a plot of September 2012 in Hood Canal. There are plots to show the locations of applicable casts, data profiles, and then the average casts for each variable in black.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/bd8ddfeb-3819-401b-b327-25cdd2e78f85" width="800"/><br>Fig 3. Hood Canal September 2012 average casts example.</p><br>

This method has proven robust and allows for more direct temporal comparisons, since domain segmentation is now static in time. Plus, it's faster! Now back to initial conditions...

### Back to LO Initial Conditions

Focusing now on an LO hindcast starting in 2013, I'm progression towards making initial conditions for January 1, 2013. We've established that the lack of resolution for variables such as TIC and TA may prohibit using observations alone to fill Salish Sea initial conditions, but the applicability of higher resolution observational data may still be valuable. I integrated the new VFC framework into the initial conditions, and I thought I was there! I had spiffy new initial conditions, but last week I identified that there were some issues. In particular, modifications I'd made to accommodate a new LO grid may have messed up the indices I use to define regions... I will discuss this further in my "Research Update" section.

### Literature Reviews

Aurora, Parker, Alex, and I have been doing weekly-ish literature reviews. In particular, we've explored local and large-scale climate forcing in Puget Sound, nutrients and hypoxia in Chesapeake Bay and Gulf of Mexico, and Strait of Georgia nitrogen budgets (which has been great!).

### Other Things

* Applied and accepted for poster session at Ocean Sciences - need to scope!
* Hosted Taylor at UW to discuss KC data findings (really cool!).
* Learned a bunch about lakes - fish are not leaves! :)
* Statistics and data analysis - term project on Puget Sound DO coming soon...
* Working (slowly) on incorporating King County water quality monitoring data

### Future Potential Research Avenues
* King County data analysis...
* Penn Cove nitrogen/DO budget (potential fieldwork with Western Washington University, nested LO model)

---

## Initial Conditions Progress Update

Since last time, I was able to figure out why I was getting inconsistent regional casts between different LO grids (shown last week for Hood Canal). I plotted the regional breakout I've been using between cas6 and cas7 (colors and numbers are simply meant to differentiate segments)...

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/4253fe0d-1f1f-4001-b1b5-d607fdd182e2" width="300"/><br>Fig 4. Salish Sea regions based on TEF segments for cas6.</p><br>

So cas6 regions look reasonable! However...

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/db101fc8-48bf-469f-9392-3f8578d3c633" width="300"/><br>Fig 5. Salish Sea regions based on TEF segments for cas7.</p><br>

For cas7, we see that, for some reason, Hood Canal and the Strait of Juan de Fuca are considered the same region. In fact, Strait of Juan de Fuca contains all the indices that comprise Hood Canal. Obviously this is...not good. I modified the method that creates TEF segments for cas7 myself since the grid update added Swinomish Channel and Agate Pass, rendering the previous version of the TEF segment building method unable to create segments for this grid. It seems I implemented but an imaginary fix.

LO has left TEF in the dust in favor of TEF2, so I have two options for VFC going forward:
1. Debug my TEF segmentation method for cas7 that is causing regions to get lost.
2. Integrate TEF2 and get with the times! We can see in the following figure created by Parker to test my initial conditions that it uses polygons drawn around segments instead of rectilinear, manual lat/lon bounds as are used in TEF.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f36b83df-960a-4121-ae65-8eb1c4e6a109" width="800"/><br>Fig 6. Salish Sea regions and associated state variable profile data (plot by Parker).</p><br>

I believe that going with TEF2 is the better way forward (and keeps with the current state of LO).

I'm humbled by all the code mistakes and reworks that have bubbled to the surface in this initial conditiosn process, but bugs are made to be squashed and code is meant to be rewritten, so onward I go!

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
2. Final quarter push.
