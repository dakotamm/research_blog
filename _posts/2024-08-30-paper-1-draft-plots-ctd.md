# Paper 1 Draft Plots (Continued)

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
10. CID uniqueness bug fix.
   
### Completed Goals:
1. Paper draft plot updates - time series averages, modern trends vs. historic trends, surface DO saturation vs. deep DO, and seasonal skagit flow vs. DO/SA/CT.
2. CID uniqueness bug fixed (not actually a bug - yay!).


---

## Full-Year Trends and Time Series Averages

From two meetings ago, we'd discussed a plot of all trends and also average time series values for each variable of each of DO/CT/SA. These also include "full-year" vs. just "low DO season" values. Here's an attempt at that! *This needs some graphical work.*

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a37cb195-9c98-40d7-a112-0575ae0e7247" width="800"/><br>Fig 1. Top row: time series averages for "low DO season/summer" at surface (pink) and depth (purple) with full-year averages at surface (grey-pink) and depth (grey-purple); bottom two rows: August-November surface and deep DO/CT/SA trend slopes at long-term sites using median and lower for deep DO as filter for casts; grey uses all seasons and color filters to just the "low DO season/summer" August-November.</p><br>

This corroborates some of our initial thoughts: the places where DO is bad (like the bottom of Lynch Cove) are not the places seeing a trend of decreasing DO. Instead regions with minimal oxygen variation throughout the water column (in central Main Basin) are seeing a "background" decrease in DO.


---

## Historic vs. Modern Trends at Long Term Sites

From last week, we suggested modifying the comparison of "modern" vs. "historic" trends would be best represented by comparing trends before and after 1999, when modern sampling took over. The following plots show DO/CT/SA trends before and after 1999, as well as the full time series trend.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/9b5433b2-760e-4ed6-8c4a-82a8a0219677" width="400"/><br>Fig 2. Surface DO trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using historic and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5f443019-fddf-44b1-923d-5d4eedde2eb7" width="400"/><br>Fig 3. Deep DO trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using historic and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0a4e3838-893d-49bf-b7a7-1c07ffd689fa" width="400"/><br>Fig 4. Surface CT trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using historic and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/22ede014-91ce-4a2a-9d76-1eadac892155" width="400"/><br>Fig 5. Deep CT trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using historic and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0625c4a3-b9e5-4814-97bd-ee3396ed8dfb" width="400"/><br>Fig 6. Surface SA trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using historic and modern time series.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6a9b7076-9898-4d59-a538-1a9a060e2ea9" width="400"/><br>Fig 7. Deep SA trend slopes at long-term sites using median and lower for deep DO as filter for casts occurring August-November using historic and modern time series.</p><br>

In general we mantain there is minimal statistically significant difference between the trends before and after 1999. However, the reduced number of data points in either case can lead to expanded confidence intervals, and thus change conclusions regarding trend significance.

---

## Deep DO vs. Surface DO Saturation

From two meetings ago, we discussed an improved graphical representation of the deep DO concentration at each site vs. the surface saturation (calculated using temperature and salinity measured at the surface) to understand how much these physical changes account for DO change over time. Here's an attempt at improving the presentation.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/e82e5093-2605-4ef0-8ea2-5e2d035ba53c" width="400"/><br>Fig 8. Deep DO trend slopes and surface DO saturation at long-term sites using median and lower for deep DO as filter for casts occurring August-November.</p><br>


---

## Seasonal Skagit Flow vs. DO/CT/SA

Last meeting, we discussed different ways to look at freshwater and DO/CT/SA. This analysis uses only Skagit River monthly average flow data and correlates it with DO/CT/SA. To understand potential seasonal effects, I found the mean flow for each of three segments of the year at the Skagit. These are defined as:
* Winter = December-March
* Grow = April-June
* Low DO = August-November

Each seasonal average flow is then correlated to the low DO season DO/CT/SA at each site!

*There's lots more to do here potentially. I can also correlate with differencing between the seasonal flows. I should use more than just Skagit. Also I've plotted short-term sites but just long sites shown.*

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b9a4015e-4b60-4b2e-bc66-ed0011335633" width="800"/><br>Fig 9. Annual Carr Inlet low DO season DO/CT/SA vs. annual Skagit low DO season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/74d74c7b-7a2b-4599-a76f-5d236ddaab4a" width="800"/><br>Fig 10. Annual Lynch Cove low DO season DO/CT/SA vs. annual Skagit low DO season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f3231a79-b805-420f-89e8-fa5c0399070e" width="800"/><br>Fig 11. Annual Near Seattle low DO season DO/CT/SA vs. annual Skagit low DO season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/8e33e9fe-7687-4705-b3cb-a0fa3caeb0eb" width="800"/><br>Fig 12. Annual Point Jefferson low DO season DO/CT/SA vs. annual Skagit low DO season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/04c329b1-17e2-43bd-8aec-2931802a0338" width="800"/><br>Fig 13. Annual Saratoga Passage low DO season DO/CT/SA vs. annual Skagit low DO season average flow.</p><br>


<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5ec582dc-e6ad-40b0-b2e5-6ca2d4d3b412" width="800"/><br>Fig 14. Annual Carr Inlet low DO season DO/CT/SA vs. annual Skagit grow season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5acefe5c-2e6c-42c6-a83b-7c9dd24c41d9" width="800"/><br>Fig 15. Annual Lynch Cove low DO season DO/CT/SA vs. annual Skagit grow season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/d79601f7-94c6-428d-bb49-89d52374e790" width="800"/><br>Fig 16. Annual Near Seattle low DO season DO/CT/SA vs. annual Skagit grow season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/ec24168c-8a94-4665-b3fc-92fe8ff293f5" width="800"/><br>Fig 17. Annual Point Jefferson low DO season DO/CT/SA vs. annual Skagit grow season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5e4c2695-4816-4686-b7c5-73341cf95ce0" width="800"/><br>Fig 18. Annual Saratoga Passage low DO season DO/CT/SA vs. annual Skagit grow season average flow.</p><br>


<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/e2da2e69-f013-4760-a3f9-cfde81120dfd" width="800"/><br>Fig 19. Annual Carr Inlet low DO season DO/CT/SA vs. annual Skagit winter season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/cd5be85b-469f-4237-a09b-fcd989007310" width="800"/><br>Fig 20. Annual Lynch Cove low DO season DO/CT/SA vs. annual Skagit winter season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/24e66203-2b22-49b5-a93e-881e7ff53401" width="800"/><br>Fig 21. Annual Near Seattle low DO season DO/CT/SA vs. annual Skagit winter season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/799de3f6-7abb-42cc-85e8-334c35a31a42" width="800"/><br>Fig 22. Annual Point Jefferson low DO season DO/CT/SA vs. annual Skagit winter season average flow.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/1a7cfd8d-fde6-4135-8c75-91e1a7e31c0f" width="800"/><br>Fig 23. Annual Saratoga Passage low DO season DO/CT/SA vs. annual Skagit winter season average flow.</p><br>

At first glance, it appears that the "grow" season Skagit flow is the best predictor of low-DO season salinity in most cases. However, I need to look at this in more depth!


---

## Discussion Possible Topics/Outline

*No updates since last meeting, will work through.*

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
* Travel/Days Off - 9/16-9/20
* PECS - 9/23-9/27
  * Figuring out reimbursements...
 

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1.

