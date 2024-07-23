# Varying Trend Statistics

### Goals From Last Meeting:
1. Work on integrating new KC data + Ecology historical into LO - README + Parker review.
2. Look at Ecology historical data.
3. Follow up with Metro Vancouver.
4. Contact Christopher Krembs (Ecology) for data discussion.
5. Keep on Marielle/Dave Clark (HDR) to discuss long-term trends
6. Homeworks!
7. Further investigate trends using different statistical methods (e.g., varying summer seasons, trend tests, bootstrapping).
8. Continue to investigate correlations with Skagit flow and other environmental variables (ref. Banas MacCready Long Live the Kings report).
9. Write write write.
   
### Completed Goals:
1. Investigated the effect on long-term analysis results for varying summer seasons and varying trend tests.



---

## Trends Many Ways

Last week, I presented some preliminary analysis of summer variation. We discussed doing a more significant investigation of what occurs with our trends when looking at the data in different ways. This last week, I analyzed varying **summer season definitions**, **annual time-averaging**, and **statistical tests**.

I used the following summer definitions:
* ~85% hypoxic days (yearday 125-325)
* August - September
* August - Mid-October
* August - October
* August - Mid-November
* August - November

Then, I both continued our meetings and also discussion from my General Exam by investigating different statistical methods:
* Linear regression with 95% confidence
* Mann-Kendall monotonicity test and Theil-Sen slopes with 95% confidence

Finally, I considered both annually-averaged data and data without averaging (per cast data).

While I'm still trying to fully understand the unique differences between the tests, I've learned that Mann-Kendall tests do not assume a distribution of the data (and thus are more robust to non-normal residuals) and Theil-Sen slopes are less sensitive to outliers. In theory, then, these two "non-parametric" tests may be better fit for purpose in our applications. This took awhile to figure out how to pull together, but I'll start with some new plots considering variables we've looked at so far at Point Jefferson. Here, I am looking at per-cast Point Jefferson data using both types of tests and using August-November as our summer definition.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/91a94d01-18b7-4409-a983-a64b537939b1" width="800"/><br>Fig 1. Point Jefferson DO, temperature, salinity, stratification, and DO surface saturation annual August-September averages; purple corresponds to deep depth-bins and pink corresponds to surface 5m for the first three variables.</p><br>

We see that despite the data similarity, there is variation between the Theil-Sen slopes and Mann-Kendall slopes. *I'll add more interpretation here if time allows.*

To look at all these axes of variation, I've created a table view for all the long time history sites using all these different metrics! It reminds me of a big game of Sudoku... *I'll add more interpretation here if time allows.*

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/58b1b162-68b6-47df-ab96-1b174833d865" width="800"/><br>Fig 2. All long time history sites with all variables mentioned so far and all analysis methods.</p><br>

Here red indicates increase (positive slope) and blue indicates decrease (negative slope) normalized to each variable's range. The grey indicates non-significant slopes. I want to find patterns in this chart! *I'll add more interpretation here if time allows.*

---

## General Exam Notes

Leaving my General Exam notes here for future reference...

Some good notes from the discussions:
1. Lots of great audience comments - Melissa Moulton mentioned using idealized terminal inlets for hypothesis testing using LO.
2. Mike notes that using "sensitivity" or lack thereof when it comes to Puget Sound nitrogen is sticky, given that the balance of nutrients in the system is equally importance (ref. Mackas & Harrison 1997 figure).
3. Mike recommends using quantitative model assessment, like "model skill score" or RMSE.
4. Mike indicated interest in decadal analysis of river nutrient variability with CT/SA/DO - sent me a nice spreadsheet that he and Ben have workedo on with USGS data from 1948.
5. Mike also indicated interest in other long-term correlations with largescale climate like PDO - e.g., using Race Rocks to correlate both with interdecadal variability in Puget Sound obs + climate oscillation.
7. Comments on "avoiding inadvertant p-hacking" - basically, layout all my data analysis steps.
   * Taylor recommended bootstrapping techniques, using Mann-Kendall trends with Thiel-Sen slope (and checking residuals when using linear-regressions...) - 7/22/2024: doing this now
   * Taylor/Alex recommended instead of "no slope detected" - explain the minimum detectable slope given data, say that slope does not exceed that.
   * Group discussed propagating errors through to final results - e.g. what is the uncertainty on my solubility calculations given CT/SA etc. - 7/1/2024: just doing calculations with measured values then assigning 95% confidence intervals for now
   * Also - listing out all the slopes and uncertainties, comparing slopes across sites, keeping 95% confidence interval on slopes... - 7/7/2024: doing this last point now
   * Investigate "step trends" as well as full time series
   * Consider % change vs. absolute changes, like with stratification!
8. Mike pointed out the importance of winter properties on DO minima...consider this in more expanded analyses.
9. Penn Cove - pull in Ecology data as well + Coupeville wharf
10. Emily Herrington - reach out to for Penn Cove data, especially on mussel growing stuff? - Michelle to connect us

Further reading:
1. [Elmstrom et al. (2024)](https://www.nature.com/articles/s43247-024-01235-8) - nutrient trends
2. Provisional WA water quality standards - Taylor emailed
3. [Brandenburger et al. (2011)](https://link.springer.com/article/10.1007/s10498-011-9129-0) - sediment trends

Homework
1. ~~Check into stratification plot labelling issue - confirmed that I just mislabeled. The stratification is DEEP density less SURFACE density in sigma [kg/m^3]. All indicated trends and interpretations are accurate with regards to my calculations, and that was just a typo. Oops, but at least I didn't totally mess up some simple math!~~ - ylabel typo fixed
2. ~~Better solubility calcs using CT/SA - ref. [Garcia and Gordon (1992)](https://aslopubs.onlinelibrary.wiley.com/doi/abs/10.4319/lo.1992.37.6.1307) per Mike.~~
   * ~~Parker recommended calculating relative contributions of both overtime.~~ - see 7/1/2024 blogpost
4. ~~Make sure I know equation of state specifics better - unit change in temperature vs. salinity impact on density.~~ - same as above
5. Parker HW question - can we do a box model to estimate a respiration rate from observations, say in Penn Cove? Basically, what can change our simple DO decay that I scraped together on the board (~ DO(t) = DO_i*e^(t/T)) where T is the time after which DO(T) = DO_i/e (or the e-folding timescale)?
6. Mike HW question - using LO & SSM rates for settling and POC degradation and mean PS depth/Penn Cove depth/etc., how much organic matter reaches the sediment intact? Does water column or sediment respiration seem to dominate?
7. Taylor HW question - ~~compare linear regression trends to Mann-Kendall~~ (broken out by seasons) and bootstrapping/subsampling vs. simple time-averaging, plot residuals for linear regressions!
8. ~~Taylor fieldwork question - looks like some ADCPs in Penn Cove are possible! Where and how long? What other field data would be helpful in Penn Cove?~~ - meeting with Taylor 7/3/2024



---


## Miscellaneous

Thoughts for posterity:
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)
* Am I going to do anything in Strait of Georgia?!


---

## Bookkeeping
* Meeting with Dave Clark - 7/26
* CEE Performance Evaluation - ? oops!
* Vacation - 8/19-8/23
* PECS - 9/23-9/27
  * Registered + booked Airbnb!
 

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. 

