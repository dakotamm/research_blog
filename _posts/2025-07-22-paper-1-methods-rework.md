# Penn Cove Profiles

This work is part of revising my Methods section in Paper 1 and incorporating GRL reviewer feedback.

---

## Confirming Theil-Sen Slopes

From last week, I'd mentioned wanting to thoroughly prove to myself (and reviewers) that Theil-Sen slopes are a good statistical choice for monotonic trends in this case. First, I revised some old processesing scripts to calculate a linear regression and then 95% confidence intervals to be able to compare these to Theil-Sen slopes with 95% confidence. The following plot is rough and meant just to illustrate the process:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/c8e5d283-5f74-43a6-ade7-153f250eb3ca" width="800"/><br>Fig 1. Point Jefferson loDO season surface and deep CT/SA/DO showing two different monotonic trend calculations; mkts = Theil-Sen slope, linreg = linear regression (indicated with larger dots, both with 95% confidence intervals indicated by smaller dots). Gray indicates not significant at 95% confidence level.</p><br>

Without belaboring by showing a million plots, I used these to visually inspect the different results. In all season/site combinations, there was no statistically significant difference between the two metrics. However, sometimes one method would provide a statistically significant slope different than 0, while the other wouldn't. No one method dominated this discrepancy in significance. I had already investigated this, but I wanted fresh eyes on this to ensure that they don't give wildly different answers.

As we've previously discussed, Theil-Sen slopes are more robust to outliers than linear regressions and also are more suitable for non-normal residuals. I plotted histograms of the linear regression residuals to confirm that indeed the residuals, like most real-world data, are not normally distributed. That being said, these actually aren't terribly non-normal, but there is some skew and the existence of outliers still makes Theil-Sen slopes a better choice. Here's an example of Point Jefferson's residual histograms, rough but fit for visual inspection:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/474d3106-6ec6-4f29-a028-a00478183156" width="800"/><br>Fig 2. Point Jefferson loDO season surface and deep CT/SA/DO linear regression residual histograms; residual is on the x-axis, binned count is on the y-axis.</p><br>

With all this, I can more confidently explain in my Methods section why Theil-Sen slopes were chosen to understand monotonic trends in this data.

---

## Thoughts on DO Seasonal Filtering

One of the reviewer's comments from my GRL submission really dug into the fact that I was filtering DO measurements to each year's median value and below. This was intended to control for the interannual variability of DO cycling within my "low DO" season from August to November. To understand this in a bit more depth. Let's start with a plot to discuss. It looks like horrible spaghetti but it was the most helpful view of this that I tried... I have all other season/site combination plots accessible for viewing during the meeting if need be.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/3073305f-3bf0-4a05-8957-14db98ed4568" width="800"/><br>Fig 3. Point Jefferson loDO season deep DO per yearday, all samples vs. filtered median and below, colored by year; yellow = older, blue = newer.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b3d38172-b590-4273-91bf-d21edfc8e359" width="800"/><br>Fig 4. Lynch Cove loDO season deep DO per yearday, all samples vs. filtered median and below, colored by year; yellow = older, blue = newer.</p><br>

There are a few things that this plot elucidates for me:
1. There is a fairly clear pattern of a DO minimum around Day 280. This is very similar at the Near Seattle site, and Carr Inlet also has somewhat of a visible pattern with a minimum around the same day. Lynch Cove seems to find an earlier minimum around Day 250. Saratoga Passage is much messier and do not have a clear pattern.
2. Point Jefferson and Near Seattle have the highest temporal resolution, specifically in terms of sampling events per year.
3. This means that at these sites, the median is a more meaningful value. At other sites and during other seasons, the median may be skewed toward one end of the range or another, which could lead to some biasing.
4. Given the temporal resolution variability between sampling years, it's challenging to always be able to see a "reoxygenation" time. In some cases, earlier sampling means that the last value measured during this season is the minimum. This bias makes it really challenging to apply filtering for reoxygneation timing on an individual year basis.

At this point, I'm having a hard time figuring out what a better process would be. Some options I've considered:
* Option 1: Filter to a minimum period for each year based on the individual year's reoxygenation timing. If this is not resolved, either take the minimum or omit the year. The latter would result in data loss, but this occurs in the existing scheme as well.
* Option 2: Filter to the overall minimum period. This is sort of what we're doing anyway by defining a season (August-November). We could constrain this further per site. This would be challenging at Saratoga Passage however, and may result in some artifacts from interannual variability still.
* Option 3: Just take the yearly minimum cast? Even more data loss this way and it doesn't account for timing differences.
* Option 4: Filter to the median DO value and below for the whole dataset (at each site for each season). This removes the potential bias introduced by yearly sampling timing differences, but implies that there is a constant median throughout the dataset, which is contradictory to any slopes over time.
* Option 5: Just keep my first scheme, or change what filtering is applied (could be 75th percentile, perhaps). The intent of this was to control for this variability in this first place! Without better resolution, it's really hard to compare the DO value right before reoxygenation apples-to-apples across years without knowing that timing for each year.

NOTE: I could use ORCA data to try and constrain reoxygenation timing better. I have a feeling this is a bit of a can of worms which could constitute its own study (which could be really intersting, but is maybe outside of this scope). Also this doesn't work at every site.

Personally I think the blunt approach of Option 5 is the best attempt to remove the variability without needing only highest resolution data and without introducing implicit assumptions about the data shape. It is also the DO values that we care the most about - the lowest ones. The risk would be years that didn't sample near the annual minimum, but the data is sadly not perfect, that's why we're doing a monotonic trend test that is robust to outliers.




