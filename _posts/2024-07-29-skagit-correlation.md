# Skagit Annual Flow Correlations

### Goals From Last Meeting:
1. Work on integrating new KC data + Ecology historical into LO - README + Parker review.
2. Follow up with Metro Vancouver.
3. Contact Christopher Krembs (Ecology) for data discussion.
4. Homeworks!
5. Meet with Dave Clark (HDR) and PSI.
6. Further investigate trends using different statistical methods (e.g., varying summer seasons, trend tests, bootstrapping).
7. Continue to investigate correlations with Skagit flow and other environmental variables (ref. Banas MacCready Long Live the Kings report).
8. Write write write.
9. Start thinking about Parker's website update on trends.
   
### Completed Goals:
1. Investigated the effect on long-term analysis results for varying summer seasons and varying trend tests - decided Mann-Kendall with all casts; still deciding summer season handling.
2. Met with Dave Clark (HDR) to discuss some nutrient trends + my findings 7/26.
3. Investigated some correlations with Skagit Flow.
4. Starting to write methods section.


---

## HDR Debrief

It was a really unique opportunity to be able to meet with Dave Clark from HDR in-person, as well as connect with PSI folks. As per usual, having a presentation checkpoint is really helpful for me to make my work cohesive. While I thought my presentation had a lot of valuable data and analysis, it didn't really seem to align with the short-term goals of dischargers. The questions of event-based impacts on water quality are not really answerable with my current analysis, but I believe that long-term trends are really important to understand to contextualize the work of all folks in this multi-disclinary world of Puget Sound DO.

Some takeaways:
* Timeline of capital improvement projects vs. time series (does discharge change have any impact on what we observe?)
* Summer seasonal breakouts are still something to figure out! (From last week's blogposts and email discussions as well!)
* What's the best way to explain the statistical significance of a "can't reject the 0-slope null hypothesis"?
* Dave mentioned qualifying trends based on existing water quality, like at Point Jefferson with naturally high DO
* Need to look further into Christopher Krembs water quality index...

---

## Skagit Annual Discharge vs. Summer DO/SA/CT Values at Long Time History Sites

Given I focused a lot on the presentation last week, I spent some time getting back into my paper 1 discussion section topics. One that I have not yet tackled is correlations with the Skagit river flow and my observed variables. Last time I presented this weeks ago, we thought property-property plots would be a helpful way to visualize this. So here are the long time history sites, using annual averages during the summer season defined August-November and annual mean discharge values in cubic feet per second. NOTE: These are for water years starting the previous October 1!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/ea8dcc18-666d-4732-b519-01ef8cb93c19" width="800"/><br>Fig 1. Annual Skagit river mean flow vs. Saratoga Passage Mid surface and deep DO, surface and deep temperature, surface and deep salinity, stratification, and DO surface saturation annual November averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/7f5a3f03-945e-450c-985d-46e24db4273f" width="800"/><br>Fig 2. Annual Skagit river mean flow vs. Point Jefferson surface and deep DO, surface and deep temperature, surface and deep salinity, stratification, and DO surface saturation annual November averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/7d12202d-d486-47fd-aeb8-b314755b46b7" width="800"/><br>Fig 3. Annual Skagit river mean flow vs. Near Seattle Offshore surface and deep DO, surface and deep temperature, surface and deep salinity, stratification, and DO surface saturation annual November averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/cf7ead8d-8a26-4eac-a171-0be2a531fdf6" width="800"/><br>Fig 4. Annual Skagit river mean flow vs. Lynch Cove Mid surface and deep DO, surface and deep temperature, surface and deep salinity, stratification, and DO surface saturation annual November averages.</p><br>


<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/eed36775-d018-4a6b-b763-4ed58f171642" width="800"/><br>Fig 5. Annual Skagit river mean flow vs. Carr Inlet Mid surface and deep DO, surface and deep temperature, surface and deep salinity, stratification, and DO surface saturation annual November averages.</p><br>

I need to review the Long Live the King's report in more depth. Also some important variables like freshet timing have yet to be considered or different seasonal responses. From these plots, however, quick interpretation shows that weirdly, Saratoga Passage doesn't show signficant correlation. The largest r^2 values are for Point Jefferson surface and deep salinity at 0.37 (pretty weak). More to dig into here!

**Dakota still updating.**


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
