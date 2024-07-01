# DO Solubility and Stratification Investigation and ...

### Goals From Last Meeting:
1. Work on integrating new KC data into LO - README + Parker review.
2. Follow up with Ecology and Metro Vancouver.
3. Contact Christopher Krembs (Ecology) for data discussion.
4. Keep on Marielle/Dave Clark (HDR) to discuss long-term trends
5. Homeworks!
6. Investigate changes in DO solubility due to temperature and salinity at Point Jefferson (long time series).
7. Set meeting with Taylor regarding Penn Cove instrumentation.
8. Identify target journal.
   
### Completed Goals:
1. Followed up with Ecology (the provided link doesn't give any data?) - still need to touch base with Metro Vancouver/
2. Contacted Marielle for introduction with Dave Clark (HDR) to discuss long-term trends - still pending.
3. Investigated changes in DO solubility due to temperature and salinity at Point Jefferson (long time series).
4. Set meeting with Taylor regarding Penn Cove instrumentation - Wednesday, 7/3.
5. Identified target journal - Estuaries & Coasts.


---

## DO Solubility and Stratification Changes at Point Jefferson

From the General Exam, we discussed investigating the change in DO solubility at the surface as a result of changing temperature and salinity separately. Based on my reading so far, I know that salinity and temperature both play a role in impacting DO solubility with the atmosphere at the ocean surface, and that temperature has stronger influence over solubility. As a corallary to this work, we also know that density (and thus stratification) is influenced by both temperature and salinity to varying extents. Though I didn't know exactly during the General Exam, I've found that a good rule of thumb is that density changes by 0.001 kg/m^3 when there is a 5 degree change in temperature, a 1 PSU change in salinity, or 200m change in depth (I got this succinct addage from [here](https://science.widener.edu/~svanbram/seawater.html)). Both density and DO solubility are non-linear and more sensitive in different temperature/salinity ranges.

To understand the relative effect of temperature and salinity on solubility and density at our Point Jefferson site, I used the [Gibbs Seawater package](https://www.teos-10.org/software.htm) for the equation of state and then [Garcia and Gordon (1992)](https://aslopubs.onlinelibrary.wiley.com/doi/abs/10.4319/lo.1992.37.6.1307) to empirically derive the DO solubility changes.

First, here's the oft-viewed century time series for DO, temperature, and salinity given both the annual surface 5m average and the bottom 20% average at Point Jefferson during the summer season.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/799f7b8c-fd68-4f6d-b22c-d1a23b3bbc04" width="350"/><br>Fig 1. Point Jefferson DO, temperature, and salinity annual summer averages; light color is surface and dark color is bottom.</p><br>

We see a decrease in DO of about 0.5 mg/L at the bottom over the last century. Using very rough estimates, we arrived at the conclusion that surface salinity and temperature change accounted for a solubility change of 0.2 mg/L DO. The following plot investigates both stratification changes and solubility changes considering just observations, and then holding a constant temperature or constant salinity. We calculate this stratification proxy as a difference between the surface and bottom measurements (deep less surface). The solubility uses Garcia and Gordon (1992) best fit method and then I convert the units using the calculated surface density using either natural or constant temperature or salinity conditions.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d8f3cacc-75d3-42dc-99bb-a554b7dfed27" width="800"/><br>Fig 2. Point Jefferson stratification and solubility annual summer averages, observed and holding salinity or temperature constant.</p><br>

---

## General Exam Debrief

It's done! I'm excited to have a milestone accomplished and even more so to get all of the awesome feedback that our discusssion brought forth! Overall, it was a good opportunity to go back to some fundamentals, do some good literature review, and make sure I can explain some of the theory in a digestible way. I was proud of my presentation! In terms of my research progress, I'm glad I did this earlier than usual in my PhD. It seems like there's a ton more to do, but I'm really excited to look back too at how much I've done.

Some good notes from the discussions:
1. Lots of great audience comments - Melissa Moulton mentioned using idealized terminal inlets for hypothesis testing using LO.
2. Mike notes that using "sensitivity" or lack thereof when it comes to Puget Sound nitrogen is sticky, given that the balance of nutrients in the system is equally importance (ref. Mackas & Harrison 1997 figure).
3. Mike recommends using quantitative model assessment, like "model skill score" or RMSE.
4. Mike indicated interest in decadal analysis of river nutrient variability with CT/SA/DO - sent me a nice spreadsheet that he and Ben have workedo on with USGS data from 1948.
5. Mike also indicated interest in other long-term correlations with largescale climate like PDO - e.g., using Race Rocks to correlate both with interdecadal variability in Puget Sound obs + climate oscillation.
7. Comments on "avoiding inadvertant p-hacking" - basically, layout all my data analysis steps.
   * Taylor recommended bootstrapping techniques, using Mann-Kendall trends with Thiel-Sen slope (and checking residuals when using linear-regressions...)
   * Taylor/Alex recommended instead of "no slope detected" - explain the minimum detectable slope given data, say that slope does not exceed that.
   * Group discussed propagating errors through to final results - e.g. what is the uncertainty on my solubility calculations given CT/SA etc.
   * Also - listing out all the slopes and uncertainties, comparing slopes across sites, keeping 95% confidence interval on slopes...
   * Investigate "step trends" as well as full time series
   * Consider % change vs. absolute changes, like with stratification!
8. Mike pointed out the importance of winter properties on DO minima...consider this in more expanded analyses.
9. Penn Cove - pull in Ecology data as well + Coupeville wharf
10. Emily Herrington - reach out to for Penn Cove data, especially on mussel growing stuff?

Further reading:
1. [Elmstrom et al. (2024)](https://www.nature.com/articles/s43247-024-01235-8) - nutrient trends
2. Provisional WA water quality standards - Taylor emailed
3. [Brandenburger et al. (2011)](https://link.springer.com/article/10.1007/s10498-011-9129-0) - sediment trends

Homework
1. Check into stratification plot labelling issue - confirmed that I just mislabeled. The stratification is DEEP density less SURFACE density in sigma [kg/m^3]. All indicated trends and interpretations are accurate with regards to my calculations, and that was just a typo. Oops, but at least I didn't totally mess up some simple math!
2. Better solubility calcs using CT/SA - ref. [Garcia and Gordon (1992)](https://aslopubs.onlinelibrary.wiley.com/doi/abs/10.4319/lo.1992.37.6.1307) per Mike.
   * Parker recommended calculating relative contributions of both overtime.
4. Make sure I know equation of state specifics better - unit change in temperature vs. salinity impact on density.
5. Parker HW question - can we do a box model to estimate a respiration rate from observations, say in Penn Cove? Basically, what can change our simple DO decay that I scraped together on the board (~ DO(t) = DO_i*e^(t/T)) where T is the time after which DO(T) = DO_i/e (or the e-folding timescale)?
6. Mike HW question - using LO & SSM rates for settling and POC degradation and mean PS depth/Penn Cove depth/etc., how much organic matter reaches the sediment intact? Does water column or sediment respiration seem to dominate?
7. Taylor HW question - compare linear regression trends to Mann-Kendall (broken out by seasons) and bootstrapping/subsampling vs. simple time-averaging
8. Taylor fieldwork question - looks like some ADCPs in Penn Cove are possible! Where and how long? What other field data would be helpful in Penn Cove?

Also as a note - I think I messed up recording the talk. I thought I pressed record but I don't have any cloud or local recordings. Darn it! Food for thought next time...

---

## Next Steps

Next on the docket is getting a real Paper 1 out the door. I'd love to do some scoping over the next week so and refresh my outline.

I'd also like to select a target journal - any thoughts?


---


## Miscellaneous

Thoughts for posterity:
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)
* Am I going to do anything in Strait of Georgia?!


---

## Bookkeeping
* OOO - 7/5
* PECS - 9/23-9/27
  * Need to register!

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. General Exam homework!
2. 

