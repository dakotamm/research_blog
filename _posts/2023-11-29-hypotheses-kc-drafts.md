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
3. >35m ("deep")

I've also analyzed each region and each depth-averaged variable considering different temporal partitions:
1. All months
2. January, February, March ("winter")
3. April, May, June ("spring")
4. July, August, September ("summer")
5. October, November, December ("fall")

### Test 1: Is there a difference between mean DO before and after 2010?

Given the EPA*** report stating a downward trend since 2010, I have conducted a simple hypothesis test to confirm if there is a statistically significant change. I am using a "two-tailed, two-sampled z-test" for this. I've confirmed that each partition analyzed meets the minimum data requirements for using a z-test (data is approximately normally distributed, 30 or more data points) in lieu of t-test, say. The null hypothesis is that there is no difference in mean DO before and after 2010; the alternative is that there has been a change. Finally, I set a confidence level of 95%. Here's some example output for Puget Sound, full-depth, all-months:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e89b5e36-815c-4efe-8403-293f02459bff" width="400"/><br>Fig 2. Puget Sound pre- and post-2010 z-test of mean DO (full-depth, all-months).</p><br>

This is showing a normalized PDF of the **difference** between the post-2010 mean and the pre-2010 mean. A positive value corresponds to an **increase** in DO. The red line is the test statistic. Since the test statistic is not more extreme than the 95% confidence rejection regions, there is **not** a statistically significant change in mean (we can't reject the null). Other test permutations are summarized as follows:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/47b8623c-f858-48d0-a2dd-2f60b2a8a26d" width="400"/><br>Fig 3. Summary of z-test for pre- and post-2010 DO mean difference. Increase indicates a statistically significant increase in DO concentration wiht 95% confidence.</p><br>

### Test 2: Is there a trend in DO concentration over time?

I had initially intended this as a check on my first test, but came to some interesting findings... I'm using a least-squares linear regression and calculating a 95% confidence interval on the slope and on data spread. The null hypothesis is a flat slope of a regression line, or no trend; alternate is a trend in either direction. For Puget Sound, full-depth, all-months:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c8564c8d-2564-4aa7-bad8-c60ed873f7db" width="600"/><br>Fig 4. Puget Sound linear regression of DO (full-depth, all-months) with confidence intervals.</p><br>

Graphically, the purple dashed line represents the null hypothesis (i.e., slope of 0 of trend line). A couple of takeaways:
1. The null hypothesis is actually outside of the confidence interval, so we should, in theory, reject the null and say that there **has**, likely, been a downward trend overtime. These results conflict the findings in Test 1...
2. The r^2 values are attrocious - so **this is probably not a good test**. However, it does indicate that the EPA*** report claim of "declining trend" is somewhat erroneous over this time period.

**Note: My next step here is to redo these plots before and after 2010 and see what we get. Also, some outlier removal may clarify this...but on what basis? TBD.**

Here's a summary of permutations indicating direction of statistically significant trend.

![image](https://github.com/dakotamm/dakotamm.github.io/assets/55995675/7e75d2af-0985-42ab-9cdd-c47b7b4eddaf)

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c8564c8d-2564-4aa7-bad8-c60ed873f7db" width="400"/><br>Fig 5. Summary of linear regression significant trends of DO.</p><br>


### Test 3: Is a polynomial fit a better approximation of data?

Here I tried to improve r^2 predictive capability by using a least-squares polynomial fit (third-order, in this case). Here's an example of that with Puget Sound, all-months, full-depth:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/3f1c1126-68e8-4089-9b3e-03b8dfdae8be" width="600"/><br>Fig 6. Puget Sound polynomial regression of DO (full-depth, all-months).</p><br>

There is moderate improvement in r^2, but it's still pretty bad. The data is definitely spread and not loving fitting to even a third-order polynomial. **Next steps?**


### Test 4: How well do NO3, temperature, and stratification predict DO?

I haven't fully summarized these results, but I've conducted a least-squares linear regression against NO3 within the specific data partition... Here's an example from Puget Sound, full-depth, all-months:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0f85b52e-ade7-451b-bbb1-7172268a0e95" width="600"/><br>Fig 6. Puget Sound linear regression of NO3 vs. DO (full-depth, all-months).</p><br>

Definitely not a good predictor...but this is not considering lag of NO3 availability and oxygen depletion in the biogeochemical cycling; rather it's just a first pass.

Now, performing the same analysis using temperature as a predictor:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6bab230c-2904-4e9a-a366-25cd2b749ebd" width="600"/><br>Fig 7. Puget Sound linear regression of temperature vs. DO (full-depth, all-months).</p><br>

This is definitely a better predictor, as expected given Henry's Gas Law!

Finally, I tried to proxy stratification by differencing deep salinity and shallow salinity (I know there are much better ways...). Needless to say this was not the best predictor either, but here it is:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/9592c8cc-b614-460e-a0ad-756f7368f99c" width="600"/><br>Fig 7. Puget Sound linear regression of temperature vs. DO (full-depth, all-months).</p><br>

A loose positive trend??? As stratification increases, so does DO? This is definitely not yielding anything very useful yet, but it's a start!

---

## KC Drafts

I sent my slides and report for review last night. I included a few plots from above, but overall would appreciate the help with the narrative through this preliminary data analysis. Thanks!

---

## Bookkeeping 
* KC Quarterly Review: 11/30
* CEWA 565 Project Presentation: 12/5
* Working Remote: 12/6-12/8
* Vacation: 12/18-12/22
* Ocean Sciences: 2/18/-2/23
* General Exam Timeline?
  
---

### Looking Ahead:
1. ORCA buoys - incorporate this into trend analysis ASAP.
2. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
3. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
4. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/) Puget Sound Institute article Parker pointed toward me...)
5. Penn Cove nitrogen budget with WWU + Penn Cove nested model...
6. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. KC Meeting on Thursday
2. CEWA 565 presentation on 12/5 (wrap up the quarter!
