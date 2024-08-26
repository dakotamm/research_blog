# Annual and Modern Trends at Long Term Sites

### Goals From Last Meeting:
1. Work on integrating new KC data + Ecology historical into LO - README + Parker review.
2. Follow up with Metro Vancouver.
3. Contact Christopher Krembs (Ecology) for data discussion.
4. Homeworks!
5. Further investigate trends using different statistical methods (e.g., bootstrapping).
6. Continue to investigate correlations with Skagit flow and other environmental variables (ref. Banas MacCready Long Live the Kings report).
7. Start thinking about Parker's website update on trends.
8. List of Paper 1 potential discussion topics.
9. Paper 1 draft plot updates.
   
### Completed Goals:
1. Paper draft plot updates - annual trends and modern trends and long term sites.


---

## Full-Year Trends

I was on vacation last week, so in the last working day I haven't been able to get too much done! However, I did update some of my Paper 1 draft plots according to our discussion the day before I left!

The first update was to add "full-year trends" to all of my slope plots. This allows us to compare the "low DO season/summer" trends to the slopes using all of the data. All analysis methods are the same as last blogpost. NOTE: This still includes filtering to the bottom 50% of all the DO measurements... *I can/will change this ASAP.*

NOTE AGAIN: As I'm writing the blog, I am seeing some dupliate cast IDs when I do percentile filtering. I've yet to fix this problem. It's a small number but I still need to consider how my cast ID non-uniqueness might be affecting this analysis. *I'll figure this out ASAP.*

All that said, the below figure shows the century trends for all three variables (DO/CT/SA) both during summer and using all-years' worth of data.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a448f976-6db3-497d-92b1-5aa880fcde4c" width="400"/><br>Fig 1. Surface and deep DO/CT/SA trend slopes at long-term sites using median and lower for deep DO as filter for casts; grey uses all seasons and color filters to just the "low DO season/summer" August-November.</p><br>

Mostly, we do not see big differences between annual trends and low DO season trends...


---

## Modern Trends at Long Term Sites

Also from last week, we discussed doing an analysis at all long time history sites for the last 20 years. We have a lot of Ecology monitoring in that time period, but this allows direct comparison between long-term trends and trends within the last 25 years at these specific sites. Here's figures comparing long-term and modern trends DO/CT/SA trends at the five sites (Carr Inlet Mid, Lycnh Cove Mid, Near Seattle Offshore, Point Jefferson, and Saratoga Passage Mid; respectively).

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/64d72a44-50ae-4e04-935b-5f3d13dd3fc6" width="400"/><br>Fig 2. Surface DO trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using full and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/1aec65bf-c63e-43f0-b3d6-ead2863bab11" width="400"/><br>Fig 3. Deep DO trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using full and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/4a774efc-2b54-475c-ad45-d174471ede78" width="400"/><br>Fig 4. Surface CT trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using full and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/7e4c4b6b-d3a3-4f9f-9015-9f5bd5e9d8a5" width="400"/><br>Fig 5. Deep CT trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using full and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/64d72a44-50ae-4e04-935b-5f3d13dd3fc6" width="400"/><br>Fig 6. Surface SA trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using full and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0d909f90-6770-437d-8114-98c3e5036364" width="400"/><br>Fig 7. Deep SA trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using full and modern time series.</p><br>

For the most part, the trends are not statistically significantly different than the long-term trends...

---

## Discussion Possible Topics/Outline

Since last time, I was tasked to put together a list for potential topics to go in the "discussion" portion of my paper. While I haven't had a ton of time to think about this in depth, I've started a brief outline:

* When/where are things changing
  * CT increasing everywhere
  * SA changes are regional (especially Skagit) but usually small
  * DO is not decreasing where we have hypoxia measured, but DO IS decreasing at "background" sites in central Puget Sound.
    * However: 1/10th of EPA plot prediction
* Explaining long-term trends
  * CT: Do temperature changes correlate with atmospheric temperature change? Precipitation changes? Offshore changes?
  * SA: Do changes in salinity correlate with changes in river flow and timing? Precipitation? Offshire change?
  * DO: How much deep DO change does surface DO saturation change explain? What about anthropogenic eutrophication?
    * Changes in population vs. changes in WWTP nutrients (if data exists) - does this correlate with DO decline (not really...)
      * Can I leverage monthly EPA data for this correlation using modern WWTP time series? As in - see if correlation anywhere in modern data? If not, likely no correlation in long-term data.
         * Event-based correlation?
    * River nutrient changes over time? Review Elmstrom et al. (2024) further
* Time lagged/seasonal correlations? E.g., dry winter predicting low DO or something?




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
3. ~~[Brandenburger et al. (2011)](https://link.springer.com/article/10.1007/s10498-011-9129-0) - sediment trends~~

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
* CEE Performance Evaluation - ? oops!
* Vacation - 8/19-8/23
* PECS - 9/23-9/27
  * Figuring out reimbursements...
 

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1.

