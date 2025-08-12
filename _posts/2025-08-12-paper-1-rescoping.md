# Revising Paper 1 Scope

---

## Aside - Whidbey Basin Model Update

Before jumping into Paper 1 complexities, I have a few updates on the Whidbey Basin model! I made grid changes as we discussed in our last meeting, including:
* Adjusting Deception Pass bathymetry - now 3 gridcells wide and matching bathymetry better (it's deeper than I thought)

* Small channel cut (1m deep x 1 gridcell) at Camano Island
* New smoothing algorithm used

I ran a test configuration called wb1_test3_xn11b that ran 12/31/2016-1/2/2017. The basic results for the surface are shown below.

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/e186e75f-780d-4ffb-9cf6-2149deeb2908" controls="controls" style="max-width: 800px;"></video><br>Fig 1. Surface salinity, temperature, and currents for wb1_test3_xn11b.</p><br>

I haven't delved much more into this, but I did start building a 2017 run for the same grid. Unfortunately, I only got to 3/7/2017 in my ocnN forcing build. I'm not sure why this is, but it did take a long time!!! atm00 and riv00 built no problem for the whole year. Should I be running ocnN forcing build somewhere else?

Once I get the forcing built, I'd like to move on to running all of 2017 and then comparing it to obs.

---

## Paper 1 Scope Discussion

What began as an investigation of salinity hypotheses has really bloomed into a messy potential scope expansion. There's quite a few things bouncing around in my head so I want to try to capture them.

### Estuaries & Coasts' Take on Statistics

One big note that has been impacting the way I think of trends is Estuaries & Coasts' submission requirement that we NOT use terms like "statistically significant" and instead just show the trend and the confidence intervals and report sample size and p-value. This comes from [this paper](https://link.springer.com/article/10.1007/s12237-019-00679-y) and gives could examples. On one hand, I really like that this allows us to not discard results given the messiness and inconsistency of our sample sizes. On the other hand, it fully changes how I've discussed and preseented results and trends so far. So let's keep that in mind as I move through the other potential scope modifications.

### Salinity Mechanisms - A Big, Confusing Mess

Last week I tried to organize a whole bunch of plots trying to understand salinity mechanisms. Here, I'm going to try to distill this to a more usable format.

I'll start with a reminder of the hypothesis I presented in my GRL submission, which was called out on being too speculative. That is as follows:
* Trends in long-term salinity are driven by changes in river flow timing.
  * Skagit River flow is not changing over time if the full year is considered.
  * However, WINTER flow is increasing over time and SPRING flow is decreasing over time.
  * Given the residence time of Puget Sound on the order of months, changes in the preceding season are reflected in the bottom salinity measurements of the following season.
  * Thus: decreasing spring flow = increasing fall bottom salinity.
* The Problem:
  * This would imply that spring salinity should decrease given winter flow increase, but that isn’t reflected in the data.
  * This also assumes a residence time without actually evaluating the correlation of river flow with salinity.
 
Here's a reminder of Skagit River trends (more winter flow, less spring flow):

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/fcb9d801-4c83-4414-b58f-c1c8e427cb6" width="800"/><br>Fig 2. a) Skagit Theil-Sen slopes + monthly time history; b) decadal average hydrographs.</p><br>

Here's a reminder of salinity trends for all seasons, depths, and sites:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/3f5f739b-182e-4a54-99c6-9b0be5a1239d" width="800"/><br>Fig 3. Theil-Sen slopes with 95% confidence for SA for surface/deep, all seasons, and all sites.</p><br>

Okay so I'm going to try to think of this as having two levers to pull with the Skagit to cause the trends that we see in salinity: increasing Dec-Mar flow and decreasing Apr-Jul flow. To do this, I made an extreme amount of plots to try to see which river season best predicts salinity for all seasons, sites, and depths using simples linear regression and r^2 values. I specifically evaluate how well THIS season and LAST season predict salinity, respectively. I'm referencing this messy but extensive [slide deck](https://docs.google.com/presentation/d/18IeU8d_8Iy0tXGPBZkustNAkvrGydCEF/edit?slide=id.p41#slide=id.p41) that I shared last week.

Though Estuaries & Coasts has rules against this, let's just look at the statistically significant trends, and evaluate how well my hypothesis holds at each site:
* DEEP
  * Apr-Jul
    * Sub-Basins
      * Lynch Cove - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
  * Aug-Nov
    * Main Basin
      * Near Seattle - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
    * Sub-Basins
      * Carr Inlet - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
      * Saratoga Passage - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
* SURFACE
  * Apr-Jul
    * Main Basin
      * Point Jefferson - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
      * Near Seattle - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
    * Sub-Basins
      * Carr Inlet - DECREASING
        * predicted best by DEC-MAR flow - this makes sense since Dec-Mar flow is increasing
      * Saratoga Passage - DECREASING
        * predicted best by APR-JUL flow - this doesn't sense since Apr-Jul flow is increasing
        * somewhat predicted best by DEC-MAR flow - this makes sense since Dec-Mar flow is increasing
        * ???
  * Aug-Nov
    * Main Basin
      * Point Jefferson - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
      * Near Seattle - INCREASING
        * predicted best by APR-JUL flow - this makes sense since Apr-Jul flow is decreasing
    * Sub-Basins
      * Saratoga Passage - DECREASING
        * predicted best by APR-JUL flow - this doesn't make sense since Apr-Jul flow is decreasing
        * ???
  * Dec-Mar
     * Main Basin
       * Near Seattle - INCREASING
         * predicted best by DEC-MAR flow - this doesn't make sense since Dec-Mar flow is increasing
         * ???
     * Sub-Basins
       * Saratoga Passage - DECREASING
         * predicted best by DEC-MAR flow - this makes sense since Dec-Mar flow is increasing

So, my hypothesis sort of explains most of the trends. But:
* Why does it not hold at all sites?
* Why are some sites/seasons more sensitive to THIS season's river flow vs. LAST season's and vise versa?
* Why does the surface have more significant trends? But it also has trends that don't match the regression predictions?
* What if we consider not just the "statistically signifcant" trends?

Note that I also evaluated this with Ecology sites and used GAM (smoothing regression) to see how correlated the time series of salinity and different seasonal river flow are. These are all in the slidedeck and we can talk about them more if so.

All this to say - I have no idea how well this fits the story, nor how to succinctly get all this across. Help!

### Adding More Seasons & Depths to My Results

For completeness (and as a result of my salinity investigation), I've been forced to reckon with trends from other seasons and other depths, as opposed to just fall at the bottom in my first submission. Here's those trends from my GRL submission supplement:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/80c7aeca-327c-40ed-956f-73d5ec9d9e0c" width="800"/><br>Fig 4. All sites/seasons/depths/variables Theil-Sen slopes with 95% confidence intervals.</p><br>

Should I include other trends in the Results? Mechanisms? Discussion? I've considered presenting all the results, but then discussing just mechanisms for my fall, bottom trends. Thoughts?

If I do consider all the trends, then I've tried to look at some of the aggregate trends to see if there are any patterns. Here's a graphic that takes some staring at, but ultimately there aren't any clear patterns in these trends:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/4b0121b3-c070-41aa-ba40-02d2072caabe" width="800"/><br>Fig 5. All sites/depths/variables Theil-Sen slopes arranged by season.</p><br>

Is this type of investigation worth adding to the scope of Paper 1?

### Considering Removing Near Seattle Site

Since this is so challenging to understand and Near Seattle is such a different site than others (much bigger, not really one sampling location), and often doing something a bit different than Point Jefferson, I recreated the same plot without NS:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a7ba689a-dcf7-4ca2-8ce8-3668182c6f11" width="800"/><br>Fig 6. All sites/depths/variables Theil-Sen slopes arranged by season WITHOUT Near Seattle.</p><br>

Is it worth potentially focusing just on Point Jefferson, instead of having to explain differences between the two sites when we're claiming they represent a system average?

### Changing Surface Definition

This doesn't have a plot - but is 5m the correct definition for a surface layer? Should I be basing it off the pycnocline, or an assumed pycnocline? Should it vary per site?

### Considering Shorter Scale Trends

I summarized some thoughts here in a recent [blogpost](https://dakotamm.github.io/research_blog/2025/08/05/long-term-GAM.html). Since this I've removed some outliers and also have done the same analysis as part of the salinity investigation with Ecology sites (higher resolution). Ultimately I haven't done much interpretation, but should we consider adding a discussion of shorter term trends? Coherent trends? Mechanisms for these?
