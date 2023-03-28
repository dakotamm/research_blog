# Some Progress on Volume-From-Casts Errors

### Goals From Last Week:
1. Reach out to KC for Whidbey Basin monitoring data status.
2. Start error-estimations for volume-from-casts method.
3. Gordon Conference registration.
4. Book AGU Ocean Visions.
5. Finish out quarter.

### Completed Goals:
1. Spoke to Greg (KC) for 2022 Whidbey Basin monitoring - not QA/QC-ed, but Greg will send link to where it lives and keep me posted on progress.
2. Registered for Gordon Conference.
3. Booked AGU Ocean Visions.
4. Minor progress on error-estimates for volume-from-casts method.
5. Wrapping up classes and deliverables.

---

## Volume-From-Casts Error Estimation

This have been a very busy couple of weeks in terms of classes and deliverables, so my progress isn't massive this week :(. But I conducted a test on a variety of different threshold values for the same study region (segment G1, 1st of each month during 2022 using LO output for casts and comparisons), trying to shed light on the regions of error between the volume-from-casts method using LO output and LO output itself.

Figure 1 shows the subthreshold volume using 5.0 mg/L DO concentration calculated using the volume-from-casts method and LO output (I've shown this plot a few times before).

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/223526106-c61736be-c733-4c99-8b93-3acd864fc683.png" width="600"/><br>Fig 1. DO subthreshold (5.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022.</p><br>

We've discussed this constant offset value at earlier months in the year, and identified that it likely pertains to shallow cells which are not captured by casts. Figure 2 shows the difference in subthreshold thickness for each month of the year (volume-from-casts less LO output). Figure 2 shows areas of both under- and overprediction throughout the domain, but some agreement in deeper basins.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/223527024-9e0ed9ec-4a99-43a3-9177-b942fd4b3024.png" width="1200"/><br>Fig 2. DO subthreshold (5.0 mg/L) thickness for volume-from-casts method less LO output (noting that this plot is a lot, but here for reference).</p><br>

Figure 3 shows a closer view of April LO vs. volume-from-casts subthreshold thickness. We can see there are cells in shallow areas and/or areas near the land that are not captured by the volume-from-casts method. Note that some of these cells show depths in excess of 150m, so not all the cells are shallow.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/223527432-66694d73-c179-41ae-8302-5e77f1d84b53.png" width="600"/><br>Fig 3. DO subthreshold (5.0 mg/L) thickness for volume-from-casts method and LO model output, all from April 1, 2022.</p><br>

We've seen this already for 5.0 mg/L threshold DO concentration, but I extend the analysis to include a wider range of thresholds. Contrary to expectations, I found that the offset seen using a 5.0 mg/L of approximately 4e9 m^3 underprediction by the volume-from-casts method is present at all lower values, including at anoxic conditions (0.0 mg/L). Figure 4 shows the subthreshold volume as calculated from volume-from-casts and LO output using 0.0 mg/L as a threshold. This is an extreme value, but the plot is representative of this offset in all values lower than 5.0 mg/L.


<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/223529239-c22295f2-9dea-4160-afbf-0c89ae9661ab.png" width="600"/><br>Fig 4. DO anoxic (0.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022.</p><br>

This offset is nearly the same as the underprediction for 5.0 mg/L, which implies that LO has anoxic cells in the domain (if my code is correct). Figure 5 shows the anoxic thicknesses for both methods for April 1, 2022.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/223530482-6fdc5d14-29f5-49b4-a4fa-9d5c1474aa9a.png" width="600"/><br>Fig 5. DO anoxic (0.0 mg/L) thickness for volume-from-casts method and LO model output, all from April 1, 2022.</p><br>

This plot looks very similar to Figure 3 despite vastly different threshold values, implying that LO output shows these cells as anoxic. A few thoughts:
1. These cells seem physically unrealistic...?
2. Very possible that the way I'm calculating these values from LO output directly is somehow flawed or bugged, though I haven't been able to find that.
3. This offset appears consistent when volume-from-casts predicts no subthreshold volume.

---

## Bookkeeping 
* OOO - Wednesday, 3/8/2023 - Friday, 3/10/2023 (back Sunday night)
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023 - REIMBURSED (airfare/lodging/registration)
* Ocean Visions Summit:  flyng Monday, 4/3/2023 - Thursday, 4/6/2023 - REIMBURSED (airfare/lodging/registration)
* Quals: April 24-28, 2023 - oral defense Friday, 4/28/2023 at 10am
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. How to do transect from casts...things to noodle on.
2. Common error estimation methods - need lit. review.
3. Figure out comments section on blog!!!

### Looking Ahead:
1. Continue error-estimations in volume-from-casts method.
2. Expand volume-from-casts method domains.
3. Continue discussion with KC for Whidbey Basin monitoring data.
4. Finish out quarter!!!
5. Start studying for quals.

### Goals For This Week:
1. Fix bug causing erroneous "zero-ing" at domain edges.
2. Expand volume-from-casts method domains.
3. Continue error-estimations.
4. Continue discussion with KC for Whidbey Basin monitoring data.
5. Finish out quarter!!!
6. Start studying for quals.
