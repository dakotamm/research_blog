# Time Series Confidence Intervals and Future Planning

### Goals From Last Meeting:
1. Continue to scope future work (discuss general exam this week).
2. Make time series plots with confidence intervals.
   
### Completed Goals:
1. Make time series plots with confidence intervals.

---

## CEWA 565 Project Ammendments

To wrap up my analysis of pre- and post-2010 DO trends that I presented both for King County and as a portion of my final project for CEWA 565 (Data Analysis in Water Sciences), I looked more in-depth into my use of z-tests of hypotheses. As a reminder, this test assumes the data in both distributions (pre- and post-2010) has more than 30 data points, is normally-distributed, and has known population variances. This is unrealistic for this dataset since we do not know the population variance. Thus, I used a Welch's t-test for my final report instead. This test does not assume data distribution nor variances (unlike a Student's t-test, which requires similar distribution variances in two compared distributions).

Here's my old conclusions from the z-test:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e67239de-e1bd-44dc-9925-9237879c3b7b" width="800"/><br>Fig 1. z-test results for a change in mean [DO] below 35m in Puget Sound before and after 2010 (OUTDATED).</p><br>

Here's my new conclusions from the Welch's t-test:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/257838d6-5210-4169-b08b-9498f736dbbb" width="800"/><br>Fig 2. Welch's t-test results for a change in mean [DO] below 35m in Puget Sound before and after 2010 (NEW AND IMPROVED).</p><br>

Conclusions don't change much and find less statistically significant change, as expected. All this to say that further understanding of our dataset is always helpful and questioning what is the appropriate statistical tool is good practice going forward. 

---

## Time Series with Confidence Intervals

From last time, we discussed that a next important step in my data analysis is understanding the uncertainty inherent in our time series measurements. This is imperative for me to be able to say anything about an observed trend, its correlations with other environmental variables, understand potential oscillation, etc. So I've made a couple of steps:
1. Incorporated all of the available CTD/bottle data (collias, dfo1, ecology, and nceiSalish).
2. Calculated confidence intervals for each monthly average.

For the following plots, I am using every month and all data points deeper than 35m to create an average. The confidence interval shown is 95%, which is 1.96x the standard deviation, divided by the squareroot of the number of data points. I removed average with only one sample, since that implies confidence intervals of 0, which is misleading in these plots. (This tended to occur sporadically in older datasets, where confidence intervals tend to be much larger due to smaller sample sizes). These focus on salinity, temperature, and dissolved oxygen.

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/93456af4-951d-4c3d-a350-abebf168df88" width="400"/><br>Fig 3. Main Basin mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/49fab505-48fd-45f9-ae24-cc439ba4b7e9" width="400"/><br>Fig 4. Whidbey Basin mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/986d7763-f278-418e-9fcc-865afa0c975c" width="400"/><br>Fig 5. Hood Canal mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/31c287ae-b0bc-411c-bebf-38ffe328fee2" width="400"/><br>Fig 6. South Sound mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

We noted last week that we should focus on Puget Sound, but I also made plots for Strait of Georgia and Strait of Juan de Fuca.

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f046d397-4787-433f-93c1-3df1688a4a7e" width="400"/><br>Fig 7. Northern Strait of Georgia mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e799b25e-15a9-4580-b171-113d0f3efb38" width="400"/><br>Fig 8. Southern Strait of Georgia mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/67606624-0ad4-467e-8c0a-9ca84f9b9579" width="400"/><br>Fig 9. Strait of Juan de Fuca mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

<p style="text-align:center;"><img src=https://github.com/dakotamm/dakotamm.github.io/assets/55995675/7839a9ce-3c8b-494a-80f9-add886c17986" width="400"/><br>Fig 10. San Juan Islands region mean monthly [DO] below 35m time series with 95% confidence intervals.</p><br>

With all of these plots, it's hard to see a trend at first glance. It's also really challenging to infer anything given years missing data (**does anyone have this?!**) and the large confidence intervals in earlier data. I also want to note that Figure 8 shows that Southern Strait of Georgia has really low DO in recent years. I believe this is due to oversampling at Saanich Inlet (as usual). If I have time before the meeting, I'll break out Saanich Inlet versus the rest of the Southern Strait of Georgia.

I already have put so many plots here, but I do have seasonal time series, time series for a mid-depth bin (15-35m) and shallow bin (<15m), and time series for all measuresed variables (spoiler alert: it's pretty sparse with most of the other ones in earlier years). I can share these outside of the blogpost.

Next steps here:
* I have Skagit discharge data since 1940...explore the correlation between monthly discharge and CT/SA/DO?
* Volume-weighted averages?
* Saanich Inlet breakout (if I can't get to it today)

---

## Planning

Last week, we chatted about Ocean Sciences and the direction for Paper 1. Here's some summary:

* 2/22: Ocean Sciences Poster
  * Focus on Puget Sound observed DO/CT/SA trends and uncertainty
    * Exclude King County data, ORCA buoys, Whidbey mooring data for now (mooring data could provide short-time scale analysis/later hypothesis testing)
    * Analysis of correlation with physical environmental data (like river flow)
    * Potentially use volume-weighted averages?

* Spring/Summer 2023: Paper 1
  * Continuation of Ocean Sciences poster...
    * long term trends in Puget Sound DO (similar to Riche et al. 2014, Moore et al. 2008)
    * Emerging story of changing atmospheric and environmental conditions
      * low river flow leads to less efficient exchange flow and longer residence times may be associated with lower DO
        * less stratified, saltier over time, warmer over time?

* Spring 2023: General Exam (Thesis Proposal)
  * Part 1: Paper 1 content!
  * Part 2: ??? specific regional analyses
  * Since I already have a Masters (albeit in a different group), how many "chapters" are warranted? I've heard two for pre-existing MSCEs...
  * Where does Penn Cove stuff fit? Learning how to run LO?
  * Incorporating reading...
  * **NOTE:** Stefano (PSI) reached out regarding my thesis proposal and potential collaboration... Thoughts?

---

## Bookkeeping 
* Vacation: 12/18-12/22
* Ocean Sciences: 2/18/-2/23 - Airbnb booked!
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
1.
