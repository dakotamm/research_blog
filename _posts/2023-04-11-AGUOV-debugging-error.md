# AGU Ocean Visions Reflections, Debugging VFC, and More Error Quantification

### Goals From Last Meeting:
1. Confirm class schedule.
2. Quals studying - approximately 3-3.5 days per week.
3. Compare segment indices to land mask to check for mismatch (ref. bug discussed in "Follow-Up from Last Meeting" section.
4. Debug indexing issue that occurs when casts fall on masked domain.
5. Expand domain/cast location source.

### Completed Goals:
1. Confirmed class schedule.
2. Quals studying - ongoing.
3. Compare segment indices to land mask to check for mismatch (ref. bug discussed in "Follow-Up from Last Meeting" section from last post).
4. Debug indexing issue that occurs when casts fall on masked domain.
5. Expand domain/cast location source - ongoing.

---

## AGU Ocean Visions

Last week, I attended the AGU Ocean Visions conference in Atlanta, GA alongside great colleagues. It was an eye-opening experience, serving to educate me in a new, crucial field and bridging the gaps between industry, academia, and policy. Personally, I entered without much knowledge of current ocean-based climate solutions. When such solutions were presented (specifically via a VC/startup lens), I was initially skeptical: shouldn't the bottom line be reduce humanity's carbon footprint? To cause less harm instead of turn to technology to allow our lifestyles of carbon excess? As a stubborn idealist, my knee-jerk cold shoulder to geoengineering was strong.

However, in no minced words, Ocean Visions director Brad Ack stated that we've passed the tipping point before which "emitting less" would have been a viable solution. Any sustainable, survivable future requires intervention via removing carbon (CDR), lowering the mean temperature of earth (e.g., via cloud brightening), safeguarding species from extinction - all in addition to the seemingly impossible task of cutting the world's carbon footprint.

Among many other speakers, writer Oliver Morton advised thinking of geoengineering and climate intervention as "medicine," without which the climate will continue to change with disastrous effects. Director of Silver Linings (NGO) Kelly Wanser described geoengineering as a means to deal with near term issues in a way that reducing carbon emissions can't, given the timescales of climate equilibration. The week's refrain seemed to be: "one can't let best be the enemy of good," because the time to act is now and while not every proposed solution is perfect, it is likely that they'll all be necessary to help solve the crisis. And enabling humans to fix the issues they've caused via ocean-based climate solutions is "irresponsible not to consider."

I was inspired too by the women leaders in this field. Among many others, Dr. Anya Waite of the Ocean Frontiers Initiative was an inspiring speaker and leader of this academia/governement/industy partnership committed to equitable data collection and ulitilzation toward carbon removal and climate solutions. I feel confident in these leaders and emboldened to follow in their footsteps.

Parker asked us to consider how we might use our local waters for carbon removal experiments. After an initial not-in-my-backyard reaction (which I then realized was a little silly), I have some questions and thoughts with regards to carbon removal:
* Adding alkalinity seems like the most readily discussed solution in carbon removal, but other sources - how can we understand downstream impacts of all comparatively? What's the role of models in this?
* Are there any ecosystem impact studies/thoughts on marine carbon removal?
* Ethics of preservation local ecosystems vs. global solutions (relevant to our work here)
* Balance between residence time at surface/near carbon removal system vs. timescales of dissipation of additives (if used) to prevent ecosystem harm
* Earth system effects - where are the most useful places to perform CDR, cloud-brightening, etc.
* Policy shifts to enable research and intervention - what are the policies in place preventing this that everyone seemed to discuss? Environmental protection laws?
* Changing well-intentioned public perception against geoengineering - what's the most effective way?

Overall, this was an excellent, eye-opening experience. I am left with many questions, some good connections, and a drive to improve. Specifically, I want to learn more about the technologies for climate intervention, the earth system/ocean chemistry influencing the solutions, and - very importantly - how to bolster my science communication. If nothing else, communication is imperative to my future as a scientist and hopefully as a leader in this field.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/231262662-ec3cdf04-c900-47a1-85be-b6f81dc12c3e.png" width="600"/><br>Fig 1. Whale shark + humans.</p><br>

---

## Segment Indices Check

Given the conference and quals studying, my progress hasn't been momentous. However, given discussion last week, I implemented a comparison of LO segment indices to the landmask used to determine cast areas via the VFC method. This was elucidated as a potential problem since early implementations of calculating LO subthreshold cells showed 0 values on edges near masked cells. This process investigated whether or not these cells were seen as a result of a bug in my early processing code or because of an error in the LO segment indices. As a note: I wasn't able to replicate this early error (the case for better version control...)

Figure 2 shows the difference between binary matrix "mask_rho" extracted from the LO grid (0 indicates land cell) and the i & j segment indices used in calculating LO subthreshold cells. There are no cells that do not agree - this is good!
![Figure 2023-04-11 094324](https://user-images.githubusercontent.com/55995675/231267501-c803e2a7-3752-4608-a95c-e3741f2e73c3.png)

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/231267501-c803e2a7-3752-4608-a95c-e3741f2e73c3.png" width="400"/><br>Fig 2. Difference of binary matrices of "mask_rho" and LO segments. 0 indicates agreement.</p><br>

---

## Volume-From-Casts Progress

From last meeting, my goal was to extend VFC into more segment domains and handle indexing errors discussed last week. I was somewhat successful (so far). As a reminder, LO segments in the Strait of Georgia and Juan de Fuca are shown in Figure 3. Note that these are segments relevant to the DFO bottle and cast data that I'm using as a test case.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228325464-b0bf802a-86a8-4de4-b734-02f9a7daab82.png" width="300"/><br>Fig 3. LO segments in Strait of Georgia and Strait of Juan de Fuca.</p><br>

Figure 4 shows normalized RMSE (where normalization is the range of LO values) for subthreshold volumes calculated in the Strait of Georgia using the VFC method vs. LO calculations. I've specified a subthreshold volume for oxygen as 4.0 mg/L and casts from DFO locations during June 2019. Like previous studies, I've taken casts from LO history files on the first of each month throughout 2022.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/231269507-7f9b8bd4-5994-4d9b-b0e7-f9f2d02a5605.png" width="900"/><br>Fig 4. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. RMSE is shown for each segment in the Strait of Georgia.</p><br>

I have not yet looked at each individual section's cast partitioning - I believe this will elucidate the differences in RMSE. Largely, however, VFC performs well in this region, as discussed in part last meeting.

Since I was able to debug in the Strait of Georgia, I extended my analysis to the Strait of Juan de Fuca...see Figure 5 for the same analysis as Figure 4 but on Juan de Fuca segments.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/231270151-da8e7e9e-7f60-4730-a0fe-5daf7727816e.png" width="600"/><br>Fig 5. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. RMSE is shown for each segment in the Strait of Juan de Fuca.</p><br>

Clearly the method has more to debug...

Next steps are as follows:
1. Expand the VFC methods to all domains.
2. Continue to build robust VFC toolbox.
3. Create plots comparing spatial variability of errors.
4. Incorporate other data sources (including revised DFO, NCEI, DOE, etc.).
5. Onto actual observerational data...

---

## Bookkeeping 
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* Quals: April 24-28, 2023 - oral defense Friday, 4/28/2023 at 10am
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods - need lit. review.
2. Figure out comments section on blog!!!
3. Gordon Conference poster timeline...

### Looking Ahead:
1. Quals studying...
2. Debug/build out VFC code (expand to all domains, at least...sheesh!)
3. 

### Goals For This Week:
1. 
