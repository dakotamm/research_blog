# Paper 1 Draft Plots

### Goals From Last Meeting:
1. Work on integrating new KC data + Ecology historical into LO - README + Parker review.
2. Follow up with Metro Vancouver.
3. Contact Christopher Krembs (Ecology) for data discussion.
4. Homeworks!
5. Further investigate trends using different statistical methods (e.g., varying summer seasons, trend tests, bootstrapping).
6. Continue to investigate correlations with Skagit flow and other environmental variables (ref. Banas MacCready Long Live the Kings report).
7. Write write write.
8. Start thinking about Parker's website update on trends.
   
### Completed Goals:
1. Feeling confident in our trend analysis technique! See below.
2. Paper draft coming to light! Plots/thoughts below.


---

## Trend Analysis - I'm Starting to Feel Confident

Last week, I presented more analysis on varying summer definitions, causing myself a little bit more confusion. After the Tuesday meeting, we decided on a new direction to use a percentile-based filter within a "low DO" time range to account and account for interannual variation in reoxygenation timing. I created plots for Parker's presentation using the 50th percentile of lowest deep DO casts occurring between August and November for each year for all variables' trend analyses. After meeting with Alex last Friday, we realized that this method should only really be applied to DO measurements (since timing variability for DO is the interannual variability we seek to control in this analysis) and that it doesn't make sense to apply this cast filtering to other variables (CT/SA). So - throughout the blog these will just be all measurements occurring between August and November.

However, 50th percentile cutoff is not the only path. Throughout the blog, I have continued with it since it is the cleanest, but the following two figures show the trends for each of my (5) long term sites using different percentile filtering.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/951e3cf7-f2a9-4ab6-bae5-6b8e560dc734" width="400"/><br>Fig 1. Surface DO trend slopes [mg/L/century] at various sites, under various August-November deep DO percentile filtering.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/4bf77f4b-1bfd-446f-bf25-4b2059e93ee8" width="400"/><br>Fig 2. Deep DO trend slopes [mg/L/century] at various sites, under various August-November deep DO percentile filtering.</p><br>

**Any thoughts on if different percentile filtering makes more sense?**

Here's a graphical example of the process:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/4bf77f4b-1bfd-446f-bf25-4b2059e93ee8" width="400"/><br>Fig 3. Point Jefferson deep DO August-November percentile filtering example.</p><br>

---

## Paper Initial Conclusions

It's really helpful for me to have an idea of the bottom line when writing this paper. I feel confident that I'm close! Here's some plots to show that. Note that in these plots, I've started numbering my long term sites. They are in alphabetical order as follows:

1. Carr Inlet Mid
2. Lynch Cove Mid
3. Near Seattle Offshore
4. Point Jefferson
5. Saratoga Passage Mid

This first plot is the surface and deep DO, CT, and SA trend slopes. Recall I'm using Theil-Sen slope analysis for each, using August-November values. In the case of DO, I only use casts that are at or below the 50th percentile deep DO values for that year, controling for winter storm/oxygenation interannual variability. 

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0cfa103f-5058-45f9-bfbe-89e0af4ecca1" width="800"/><br>Fig 4. Long term sites DO/CT/SA surface and deep trends in summer (August-November).</p><br>

This plot to me feels like a really good representation of what's actually happening in the system. For surface temperature, we see around 1.5 degrees C/century. Lynch Cove is the highest at 5 degrees C/century but has a ton of variability. Main Basin sites have the least warming. Deep temperature is increasing at about 1 degrees C/century. All of these are really similar and also not variable! So these slopes are pretty well defined and well understood. These temperature signals are all increasing (cough cough global warming) and are also essentially the same as what Riche et al. (2014) reports!!!

Surface salinity has pretty much no change at Carr Inlet, huge variability but no change at Lynch Cove, greater than a 1 PSU increase in Main Basin, and a notable 2 PSU decrease Saratoga Passage. This is likely due to this site's unique proximity to the Skagit! Deep salinity ~0.5 increase at Carr Inlet, Near Seattle Offshore, and Saratoga Passage. As with temperature, the bottom values show vary little variability in the confidence intervals. The impact on stratification is bi-directional but it seems like, if there is any system-wide change, it is a very small increase in salinity (as evidenced by bottom values).

Finally, surface DO has huge variability at Lynch Cove, Carr Inlet, Whidbey Basin which negates any statistically significnat trend. There are significant trends of 0.5-1 mg/L/century decrease at the Main Basin sites. Deep DO change is approximately 0 at Lynch Cove and Saratoga Passage, is decreasing by more than 1 mg/L at Carr Inlet and at Near Seattle Offshore, and is just barely decreasing at Point Jefferson. Very importantly, the regions with documented hypoxia (Lynch Cove in this set) show no trend at depth and a surface INCREASE of DO! Similarly, the only sites with statistically signficant decreasing trends have relatively high ambient oxygen (double check at Carr Inlet).

I started this whole investigation with the EPA's Marine Water Quality Report in the Salish Sea. We show ~1 mg/L/century decrease in DO at any point in Puget Sound, whereas they show ~1 mg/L/DECADE!!! Our results are an ignore of magnitude less extreme for slope over time!

Continuing to some calculated values (that may or may not be "conclusion" plots?) with stratification (density difference between the deep and surface at each site) and DO surface saturation.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/332d96f2-2531-4a02-8a33-2f63717d4103" width="600"/><br>Fig 5. Long term sites stratification and DO surface saturation trends in summer (August-November).</p><br>

We see an increase in stratification at Saratoga Passage North overtime. This is approximately equivalent to the change in surface salinity! Otherwise we observe very little change in stratification.

DO surface saturation is decreasing everywhere or has no trend. This is expected given the region-wide increase in temperature. The next question is - does this explain the changes in DO we see?

For this next plot, I've only taken the difference of the DO slope less the DO saturation slope to get the DO trend NOT accounted for by saturation change (mainly attributable to temperature change). There are probably different ways to do this (**let's discuss!**) but this is a first pass.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/fbe81853-345a-4a99-8746-27472b8e1980" width="400"/><br>Fig 6. Long term sites DO trends not accounted for by saturation change in summer (August-November).</p><br>

This plot is a little rough, but the important takeaway is that the saturation change accounts for almost all of the bottom DO change at Carr Inlet and Point Jefferson. Negative values (like at Near Seattle Offshore) indicate that the DO decrease is MORE than can be accounted for by saturation. Alternatively, the positive values indicate that the DO change is actually INCREASING despite the decrease in DO surface saturation.

Which all means...saturation is some of the story, but not the whole story! Onto some rougher plots and discussion ideas.

---

## Paper Discussion Thoughts and Auxilliary Plots

I have a lot of thougths swirling around so I'll do my best to just get through what I can :).

# Winter System Changes and Correlations with Summer Changes?

I haven't spent a ton of time interpreting these plots yet - but here's the same series of plots and analyses for NON-SUMMER (or December-September). The intent is to understand if there are trends in other seasons and if they maybe explain what we see in our low-DO summer? Perhaps winter high temperatures might correlate with low DO? I haven't compared annual average propreties for correlation yet. I'm also noting there are better ways to define this season and that this large swath of the year is likely introducing confounds... **Any thoughts?**

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/94ea4db4-bb65-431c-86ae-ab8405be4a0a" width="800"/><br>Fig 7. Long term sites DO/CT/SA surface and deep trends in non-summer (December-November).</p><br>


# Modern Trends and Correlation Analysis Using Modern/Monthly Data?

I have identified 21 Ecology monitoring sites with 20+ years of data. I've so far not used these too much, but Alex suggested that I take a look at whether or not the trends that I see at the long-term history sites are statistically different than the modern sites. So I've done that for all variables, but I've shown deep DO here.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a84bbaa1-7fef-4520-8e02-9effe8d6ad92" width="800"/><br>Fig 8. Short and long term sites deep DO trends in summer (August-November).</p><br>

The only value with statistically signifcant slope is at HCB004 (which is about halfway down Hood Canal, south of Seabeck). This is showing an epic INCREASE in deep DO. GOR001 also shows a decrease but not significantly different than the nearest long term site at Carr Inlet. That being said, I'm having a hard time making this a cohesive thought (**some help would be appreciated!**).

Finally, if this makes sense in the paper scope, we could use these sites to do a higher resolution correlation with environmental variables and relate that to nearby long-term sites as a potential explanation of further DO trends?


# Freshwater and Salinity Changes

Last week I spent a little time on this but essentially indicated that the Skagit mean flow does not predict low DO anywhere in the region, nor does it really correlate with stratification. However, surface and deep salinity are somewhat correlated. My discussion definitely at least needs a trend analysis of freshwater flow. Note that some salinity changes at Saratoga Passage may be due to plume effects from the Skagit.


# River and Nutrient Changes

We could evaluate changes in nutrients (given a lack of monitoring DIN data) by at least looking at river trends and changes in nutrients and WWTPs!

Alex and I discussed Elmstrom et al. (2024). I need to do a closer read, but this paper seems to not inform long-term change in watershed nutrients... So this may be a deadend.

For WWTP - I intend to take a look at Aurora's adapted WWTP time series and...see if there's a trend? Could also correlate this to higher resolution ecology data in the same time period.

Finally, I will take a look at population change to see if it has any correlation with nutrients, especially from WWTPs...


# Atmospheric Changes

I now have Parker's temperature and precipitation data from the LO webpage! I'll do some trend analyses here to explain change in temperature and potentially some changes in surface salinity?


# Writing

I'll share a draft! All of the introduction/motivation is currently too long, so I need significant cuts. I've drafted a Methods section and have started to work on results. I think I still need a lot more outlining in the Discussion section. In either case, writing is happening and informing the plots I make!


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
  * Registered + booked Airbnb!
 

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. 

