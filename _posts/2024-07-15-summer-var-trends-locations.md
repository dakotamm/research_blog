# Summer Season Variation, Trend Locations, and Preliminary Skagit Discharge Correlations

### Goals From Last Meeting:
1. Work on integrating new KC data + Ecology historical into LO - README + Parker review.
2. Look at Ecology historical data.
3. Follow up with Metro Vancouver.
4. Contact Christopher Krembs (Ecology) for data discussion.
5. Keep on Marielle/Dave Clark (HDR) to discuss long-term trends
6. Homeworks!
7. Understand where trends occur with August/September summer analysis.
8. Investigate correlations with Skagit flow.
9. Write write write.
   
### Completed Goals:
1. Cleaned and made Ecology historical data usable with LO.
2. Keeping with Dave Clark (HDR) to discuss long-term trends - still pending meeting time.
3. Investigated trends with August/September analysis.
4. Preliminary look at Skagit flow...


---

## Historical Ecology Dataset

I finally cleaned up and can use the historical Ecology dataset (1973-1998). This dataset is mainly bottles before November 1989, after which time we have CTD profiles available. The new data does not add more resolution to our existing long-term analysis sites but is good to have! Early DO tends to be very shallow and sparse. I haven't spent too much time working with it yet, but it is usable and ready to be implemented within the greater LO ecosystem (in terms of its structure!).

---

## A Note on Summer Season Variation 

From last week, I presented some different data views at Point Jefferson. Of primary interest was the "summer" seasonal definition. For this analysis, I intend for my summer definition to capture the minimum DO at our sites. Canonically, I've continued this investigation using August and September. However, these do not always follow our "summer" definition, as the minimum DO can fall outside of these bounds. First, I'll start with Point Jefferson's three key variables. We note from last time that August and September do not show a significant decrease in DO overtime, where a longer and later summer season does (yeardays 125-325).

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/abc0d4cc-1be2-4a86-909d-a5c2aa5f1f9d" width="800"/><br>Fig 1. Point Jefferson DO, temperature, and salinity annual August-September averages; purple corresponds to deep depth-bins and pink corresponds to surface 5m.</p><br>

Further, I investigated the DO minima timing and related variables to understand if August and September in fact captures all DO minima. Here's a plot similar to last week, but with shading indicating August/September.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/7ce6e813-5ea4-4978-ae9c-c917dfc5a5c0" width="800"/><br>Fig 2. Point Jefferson minimum annual DO in bottom 20% depth-bin, timing of minimum annual DO, and depth of minimum annual DO overtime; August and September are highlighted in the middle plot.</p><br>

We see that while August and September capture some DO minima, it is by know means fully inclusive. I did the same analysis for all long-term and 20-year ecology sites. In general, August-September does not capture all DO minima with most sites having a skew toward later DO minima timing. I can show more plots during the meeting.

I'm not entirely sure yet what this means yet for future summer definition, especially with site-specific variation in DO minima timing...but I proceed with August/September in the rest of this blogpost.

---

## Trend Locations

Given the new summer season definition, I have summarized the varying potential important trends in the following plot, showing the locations of varying significant trends overtime. A reminder that the circular sites are 20-year-ish time histories from Ecology and then the irregular polygons are 60+ year time histories. Color indicates a significant trend during August/September.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5bc11328-0b16-40c5-aff6-72dbccfa199a" width="800"/><br>Fig 3. Locations of August/September deep hypoxia, decreasing deep DO, surface warming, increased stratification, and decreased surface DO saturation; signficant trends using annual averages and 95% confidence.</p><br>

Given this summer definition, we see nearly no stratification increases throughout the system, and that DO surface saturation decrease is nicely correlated with surface warming. I intend to use more variables and understand spatial trends in more depth.

---

## Looking A Bit at Skagit Discharge vs. DO/SA/CT

As intended for Paper 1 discussion, it's important to understand the correlation of observed DO/SA/CT trends and variation with environmental variables like river flow. I've taken a quick first pass at using the Skagit River annual flow at Mt. Vernon (from the USGS site) and comparing that graphically to all sites observed DO/SA/CT. Here's starting with Saratoga Passage North, which is nearby the Skagit River mouth.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/68a40473-180a-4d1a-bd8f-e937e6a8cc9c" width="800"/><br>Fig 4. Skagit River annual mean flow and Saratoga Passage North DO, temperature, and salinity annual August-September averages; purple corresponds to deep depth-bins and pink corresponds to surface 5m.</p><br>

We see what perhaps is a slight increasing trend in annual river flow, but a signficant increase of DO both at the surface (pink) and at depth (purple). NOTE: This increase of DO may also be attributable to a LATER DO minima, since this is only capturing August/September. I'll investigate further.

If I squint, I can also kind of see some interannual variation in salinity accounted for by river flow changes...but a more focused attack is necessary! Also, some variables may respond more to other river flow characteristics like peak flow and timing of that flow.

Some future work on this:
1. Compare to DO surface saturation and stratification (I have these plots separately if we'd like).
2. Trend analysis on Skagit data
3. Use different river indicators like peak flow, freshet timing, or monthly average during data window.
4. Use all rivers in Puget Sound? (Mike has sent me this.)
5. Zooming in on interannual variability.
6. Investigate other seasons' variation.

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
   * Taylor recommended bootstrapping techniques, using Mann-Kendall trends with Thiel-Sen slope (and checking residuals when using linear-regressions...)
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
7. Taylor HW question - compare linear regression trends to Mann-Kendall (broken out by seasons) and bootstrapping/subsampling vs. simple time-averaging, plot residuals for linear regressions!
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
* PECS - 9/23-9/27
  * Registered + booked Airbnb!

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. 

