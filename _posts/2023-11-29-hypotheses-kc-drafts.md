# Hypothesis Testing and KC Draft Review

### Goals From Last Meeting:
1. Debug initial conditions.
2. Work on data analysis for course project and KC meeting.
   
### Completed Goals:
1. Scope change from initial conditions.
2. Work on data analysis for course project and KC meeting.

---


## LO Initial Conditions Pivot and Using Paths for Data Analysis

Parker and I met before Thanksgiving for some coaching on initial conditions debugging, and it was decided that using VFC for initial conditions is likely overkill, and the team opted to go with Parker's method of path segments (essentially, creating a polygon around the LO domain in question) and filling initial conditions data from casts within that segment. Admittedly, I had hoped to solve this problem and put VFC to good use, but using this new method really opened up the doors for me to spend time with statistical analysis! Using outdated TEF sections was challenging, and though I did work through a lot of hurdles in my VFC codebase, this has certainly been an easier route to more productive data analysis at present.

Using Parker's path method and "bypassing" VFC temporarily, I'm working toward a final project in CEWA 565 (Data Analysis) and our upcoming King County meeting this week. For reference, here are the paths I'm using to segment the LO domain. They are as follows:
1. Salish Sea
2. Strait of Georgia
3. Puget Sound
4. Strait of Juan de Fuca
5. North Strait of Georgia
6. South Strait of Georgia
7. Whidbey Basin
8. Main Basin
9. South Sound
10. Hood Canal

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6c7ef216-47b0-4534-919b-195f3838ad5e" width="800"/><br>Fig 1. Domain partitions using path.</p><br>

This certainly makes it easy to make custom sections! I envision using smaller segments for areas like Lynch Cove in the future.


---

## Statistical Analysis and Hypothesis Testing

Concurrently with a final project in CEWA 565, I've started to apply some basic statistical testing to Puget Sound. The analyses I've conducted so far are not overly complicated, but get at some important questions. Since I'm working in Puget Sound, I'm working with CTD and bottle data from Dept. of Ecology and bottle data from NCEI Salish Sea; these datasets span 1999-2019.

For these analyses, I've enabled various data partitions to be made. Like with my previous analyses, I'm using **monthly** time resolution. First, I've conducted analyses in the following regions:
1. Puget Sound (as a whole)
2. Whidbey Basin
3. Main Basin
4. Hood Canal
5. South Sound

I'm using depth-averaged variables at the following partitions:
1. Full depth (average over the whole water column)
2. <35m ("shallow")
3. >=35m ("deep")

I've also analyzed each region and each depth-averaged variable considering different temporal partitions:
1. All months
2. January, February, March ("winter")
3. April, May, June ("spring")
4. July, August, September ("summer")
5. October, November, December ("fall")

### Test 1: Is there a difference between mean DO before and after 2010?

Given the EPA*** report stating a downward trend since 2010, I have conducted a simple hypothesis test to confirm if there is a statistically significant change. I am using a "two-tailed, two-sampled z-test" for this. I've confirmed that each partition analyzed meets the minimum data requirements for using a z-test (data is approximately normally distributed, 30 or more data points) in lieu of t-test, say. The null hypothesis is that there is no difference in mean DO before and after 2010; the alternative is that there has been a change. Finally, I set a confidence level of 95%. Here's some example output for Puget Sound, full-depth, all-months:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e89b5e36-815c-4efe-8403-293f02459bff" width="800"/><br>Fig 2. Puget Sound pre- and post-2010 z-test of mean DO (full-depth, all-months).</p><br>

This is showing a normalized PDF of the **difference** between the post-2010 mean and the pre-2010 mean. A positive value corresponds to an **increase** in DO. The red line is the test statistic. Since the test statistic is not more extreme than the 95% confidence rejection regions, there is **not** a statistically significant change in mean (we can't reject the null). Other test permutations are summarized as follows:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/47b8623c-f858-48d0-a2dd-2f60b2a8a26d" width="800"/><br>Fig 2. Puget Sound pre- and post-2010 z-test of mean DO (full-depth, all-months).</p><br>

***

## VFC Refinement

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
