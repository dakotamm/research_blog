# Exploring Penn Cove Observations

### Goals From Last Meeting:
1. Submit Paper 1!
   
### Completed Goals:
1. Submitted Paper 1!


---

## Ocean Visions Reflection


---

## Paper 1 Reflection


---

## KC Penn Cove Observational Data Exploration

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6a134e5b-defe-4655-b20d-715dd1f2a477" width="800"/><br>Fig 1. King County's Whidbey Basin sites sampled from 2022-2024.</p><br>








PECS was a great experience to feel confident discussing my research publically. It was really well received and I want to ride that momentum towards a paper! An important item that came up is an explanation for the salinity increase at our 5 long-term sites. So far we've only lightly touched on an analysis that I conducted before heading off to PECS. I want to rehash here.

For Skagit flow, I'm taking monthly mean flow and dividing that into three different seasons, namely:
* Winter = December-March
* Grow = April-July
* Low-DO = August-November

Then I conducted trend analyses using Theil-Sen slopes and Mann-Kendall tests of monotonicity to find where in the data there are statistically significant slopes. I did this for each season and also for the full time history. I also created decadal average hydrographs.


<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/84c55508-b087-42d2-9eba-fbe5a1ba3f51" width="800"/><br>Fig 1. Top row: full time series and seasonal trends (significant if indicated); bottom row: decadal average hydrographs.</p><br>


Overall, flow in the Skagit is not changing (does not have a slope significantly different than 0) but Skagit winter flow is INCREASING over time and Skagit spring flow is DECREASING over time, which indicates a shifting hydrograph to earlier in the year. This corroborates what Parker showed on his website.

However, the overall flow is not decreasing nor is fall flow decreasing - so the case of explaining increasing fall salinity is not definitively closed...

Given that the Skagit is not the only river in Puget Sound, I think looking at rivers in different regions will be important here, as well as the differential timing between river flows throughout the regions of the Sound. This also leads me to another related point, below.


---

## Lateral Salinity Trends

Another thought that came out of PECS was the idea of changing lateral salinity gradients over time. This may also elucidate some possible explanations for the changing salinity trend overtime, or at least allow further discussion of those mechanisms of change. To do this, I took annual averages of all August-November sampling at each site. Then I selected Point Jefferson as my "seaward" salinity measurement and calculated the difference between the salinity here and the other four sites. *I have not yet included a distance calculation to create a true "ds/dx" measurement, but since the distances would be constant in time, this is a rough pass at lateral salinity gradient change over time.*

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/89a9382c-9b08-4b85-9abb-83c68ed3e85e" width="800"/><br>Fig 2. Lateral change in salinity time series and trends over time (taking the difference between Point Jefferson (seaward asssumption) and other long-term sites, using annual averages for the August-November low-DO season).</p><br>

The only statistically significant trend is at the surface 5m at Saratoga Passage. This means that the salinity gradient between Point Jefferson and Saratoga Passage is increasing at about 2 PSU/century...which is interesting. This speaks to some long-term change in river flow especially at the Skagit, but we're only again really seeing a change in timing of river flow.

Other than this trend, the results elsewhere show no statistically significant trends in the salinity differences over time.

Where does this get me exactly? Not sure...


---

## Paper 1 Discussion Possible Topics/Outline

I've put some more thought into my outline...

* When/where are things changing
  * CT increasing everywhere
  * SA is generally increasing (if signal detected)
  * DO is not decreasing where we have hypoxia measured, but DO IS decreasing at "background" sites in central Puget Sound
    * However: 1/10th of EPA plot prediction
* Explaining long-term trends
  * CT: Do temperature changes correlate with atmospheric temperature change? Precipitation changes? Offshore changes?
  * SA: Do changes in salinity correlate with changes in river flow and timing? Precipitation? Offshire change?
    * Stratification change? Lateral salinity gradient change? Implications for exchange flow.
  * DO: How much deep DO change does surface DO saturation change explain? What about anthropogenic eutrophication?
    * Expected DO saturation change ~ half of measured DO change (or more); sometimes less DO change than anticipated via saturation change
      * Marine heat wave exploration with 20-year data
    * Changes in population vs. changes in WWTP nutrients (if data exists) - does this correlate with DO decline (not really...)
      * Can I leverage monthly EPA data for this correlation using modern WWTP time series? As in - see if correlation anywhere in modern data? If not, likely no correlation in long-term data.
         * Event-based correlation?
    * River nutrient changes over time? Review Elmstrom et al. (2024) further
  * **Out of scope:** offshore processes contribution?! Other than heat waves?
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
* PECS - reimbursements submitted...
* KC Quarterly Report - 10/11
* WWU Seminar - 11/8
 

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. KC Quarterly Report due 10/11
2. Start writing the results I know for sure will go in Paper 1...

