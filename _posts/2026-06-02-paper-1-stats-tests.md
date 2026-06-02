# Fortifying our Paper 1 statistical methods

From a combination of reviewer comments and consulting with the STATS department, I've been able to dive in more depth about our statistics for long-term trends in DO, temperature, and salinity. I'll present this in a few sections. With all of this, I'm new to the stats, so I'm happy to chat with anyone more about this! I think the best place for all of this will be a "Sensitivity Analysis" section, added to my Methods (or maybe somewhere else? Discussion?).

## Question 1 - Are slopes different before and after 1990 (historical vs. modern sampling eras)?

I tackled this first by just calculating TS slopes on either side of 1990 vs. the full range, then learning a bit more about statistics and conducting a few tests to determine the actual differences between slopes. This plot is every slope reported in Paper 1, but the points highlighted show where there is a statistically significant difference from the slopes calculated using just pre- or post-1990 data. The asterisks are the kicker - these pass what is called a Benjamini-Hochberg (BH) correction on top of the z-test for statistical significance between slopes. This basically reduces the rate of false detection. I can talk through this in more depth!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b1660be0-f9dc-48c9-a7db-237c9d48190f" width="800"/><br>Fig 1. Theil-Sen slopes for each site, season, variable, and depth with era differences highlighted.</p><br>

Where there is an asterisk is where we have statistical backing for a regime shift. Clearly, this is not many places which means we should be safe to say that our long-term slopes are not just an artifact of more recent sampling driving slopes. The slopes that are different are all salinity signals, indicating increasing salinity after this 1990 era switch. TBD on if we can provide an interpretation here with the data available.

## Question 2 - Is there serial correlation (autocorrelation) even within seasonal time series?

This comes from a reviewer wondering if Theil-Sen/Mann-Kendall are appropriate. If there is autocorrelation, these may overestimate confidence. Here, I tested for autocorrelation of residuals from the Theil-Sen slopes. To do this in actual time, however, I had to take an annual aggregate and then do a Theil-Sen slope, becauase autocorrelations really rely on well spaced data in time. With that, however, the seasonal time series seems to remove the strongest autocorrelation signal already, and the time series have mostly weak autocorrelation. However, using a Hamed-Rao Mann-Kendall variant seems to provide the most conservative estimate of the p-value of the slope, since there may be some minor autocorrelation on a 30-40 day timescale. I can include this analysis as part of a "sensitivity analysis".

I also conducted an ARIMA test (which I don't know much about other than it assesses how much serial correlation might matter) on recommendation from the STATS department. Without fully understanding it, it supports the conclusion that the results of Theil-Sen are not inflated by serial correlation in these series.

## Question 3 - Per-cast vs. annual aggregate values for the trend analysis?

This is an interesting question, and one that has a lot of possible discussion. We initially opted against using an annual aggregate because it tended to obscure the inherent sampling frequency differences between older and newer casts. However, this may provide more weight to modern casts than we want when using Theil-Sen slopes.

On the other hand, a reviewer mistakenly thought I was using annual aggregates, and really didn't like that! In either case, I compared the annual median value Theil-Sen slopes vs. my standard per-cast slopes, here. There is little to no difference except for significance changes slightly, and they generally lower for the annual median values. However, they are so darn similar that I believe our earlier rationale for pre-cast values still holds.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/e3c6d0b6-7d56-46f5-8809-fbe531f28503" width="800"/><br>Fig 2. Theil-Sen slopes of DO for each site, season, and depth using annual median vs. per-cast values.</p><br>

## Question 4 - Is the Theil-Sen slope the best estimator?

This has been a big one. I tried a few on recommendation from the STATS department. Ultimately, I looked at residuals as well as just did a sensitivity test between several tests.

For residuals, Theil-Sen does not require normality where a simple linear regression (OLS) does - this inherently means that Theil-Sen is better at outliers. OLS normality is failed by 60% of DO cases and higher for salinity and temperature, and 50% or more than the series have significant outliers. Theil-Sen remains the clear choice here.

I also did sensitivity testing with quantile regressions and weighted quantile regressions (using annual median values). These have higher asymptotic variance (apparently - are less precice) than either OLS or Theil-Sen. Thus, I still think we did the right thing in the first place!

## Question 5 - Should I use linear mixed models (LMM)?

This was recommended by a reviewer and the STATS folks. My understanding is that this shows if there is a basin-wide correlation and/or spatial correlation between sites, while also fitting a linear regression? Apparently it improves statistical power...somehow. Here's some slopes from that analysis for DO:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/424d3383-585f-44eb-b483-eae24ab79d4b" width="800"/><br>Fig 3. Linear Mixed Model (LMM) slopes of DO for each site, season, and depth.</p><br>

The takeaway here is that the slopes per site are not necessarily coherent with the overall trend (we need all the sites described independently). Which I think we knew already. However the gray bars give a "common slope" that follows our findings so far.

One important addition that I think is better emphasized here: there is evidence to suggest that spring DO at the surface is increasing over time... Would this change or Discussion of potential causes of DO loss...? Let's chat more here?

I'm working to incorporate this cohesively into my revisions. Stay tuned!

