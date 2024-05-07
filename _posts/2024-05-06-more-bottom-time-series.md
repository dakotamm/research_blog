# More Bottom Time Series for Decadal and Annual Salinity, Temperature, and DO

### Goals From Last Meeting:
1. Work on integrating new KC data into LO - README + Parker review.
2. Decadal and annual time series.
3. Work on General Exam/Paper 1 - literature review for deoxygenation in temperature urban estuaries + set up documents.
4. Formally schedule General Exam with CEE.
5. Track down more data!
   
### Completed Goals:
1. Decadal and annual time series - in progress.
2. Working on General Exam/Paper 1 - literature review for deoxygenation in temperature urban estuaries + set up documents.
3. Tracking down more data!

---

## More Decadal Analysis Cleanup

Last week, I discussed methods for assessing the bottom DO, temperature, and salinity for my decadal sites. After discussing in our meeting, we determined that the best path forward was to use the LO grid to establish the maximum depth in each decadal site, assume isobathymetry of water properties, and take the average of the bottom X% of the water column. For this analysis, I used the bottom 20%.

Additionally, after expressing my own concerns about my "seasons" I've used for analysis, I established a "growing/respiring season" from yearday 200-300 based on histograms at each site, which found the minimum DO occurs during this time period (approximately).

To conduct a decadal analysis, I took an average value of each cast in the bottom 20% of the maximum depth of the site during my "growing/respiring season". Then I averaged across all casts in each year during the growing season to establish yearly 95% confidence intervals.

A few notes to start out: I was able to elucidate which sites do not have enough depth consistency in time to be useful. Also, we discussed adding "decadal average" blobs to the plots. I haven't yet done that since so many decades are so sparsely populated. I've eliminated the following sites based on the fact that they do not have consistent sampling within the 20% of maximum water column depth:

1. Admiralty Sill (modern sites too shallow)
2. Budd Inlet (modern sites too shallow, depth inconsistency over time)
3. Dana Passage (modern sites too shallow)
4. Hazel Point (modern sites too shallow)
5. Near Edmonds (modern sites too shallow)

I've plotted the remaining sites, but there is a ton of temporal inconsistency among them. I'd love feedback on how to make this feel a little more useful! Also please note that I'm using the FULL water column at the Lynch Cove site. There is no sampling within 20% of my site's maximum depth, but there is extremely consistent sampling at 20 meters so I think it's important to include. For now I've just averaged over the whole water column. (*Parker - I forgot to place the x-axis labels on all the plots. Sorry about that! I'll fix in future iterations if necessary.*)

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/76169a7d-fbff-425e-bc2d-ffbbdefd4847" width="600"/><br>Fig 1. "Growing season" Carr Inlet bottom SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6a74eaab-2937-4b16-b7ea-c21c798c459f" width="600"/><br>Fig 2. "Growing season" Hat Island bottom SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/121635cc-262c-4b59-a3ab-b554729c9900" width="600"/><br>Fig 3. "Growing season" Hood Canal Mouth bottom SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/ebf5a6b5-ee5c-4e42-8fab-39dd827d108a" width="600"/><br>Fig 4. "Growing season" Lynch Cove Mid FULL COLUMN SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d38ecffe-248d-4811-9480-3297f8460c0d" width="600"/><br>Fig 5. "Growing season" Near Seattle Offshore bottom SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/51f0a836-ff00-4e41-9ab3-cb1dec83e29b" width="600"/><br>Fig 6. "Growing season" Port Susan Mid bottom SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/7330b302-290b-4f53-8fd9-57f918b917d9" width="600"/><br>Fig 7. "Growing season" Saratoga Passage Mid bottom SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f4a37190-a419-46f7-b44a-3f2f737bfca1" width="600"/><br>Fig 8. "Growing season" Saratoga Passage North bottom SA/CT/DO.</p><br>

Data is a little spotty. I'd love some help with direction here.

### Side Quest

I plotted all sites that record DO for every decade... Here's a video to succinctness.

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c8adcb9e-9ec8-4d02-afb1-e497ff826bad" controls="controls" style="max-width: 600px;"></video><br>Fig 9. Decadal hypoxic sites "growing season".</p><br>


---

## Annual Analysis

Last week, I presented bottom SA/CT/DO trends for all of Puget Sound's basins. We redirected and discussed that it would make sense for me to take a look back at EPA's plots on [this site](https://www.epa.gov/salish-sea/marine-water-quality). I've created similarly plots to these before, but here I took a literal approach and did what I could do reconstruct them. The article does not mention exactly what filtering they use, so for mine I've calculated a cast average within each depth bin and for each time period, using the whole year's worth of casts. Here are two replicated time series for Puget Sound:


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/65c51504-f423-4cc3-889b-b06a081e6f7f" width="800"/><br>Fig 10. 2010-2018 DOE 0-35m DO (averaged per cast) with linear best-fit line.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/addea13b-d028-47c5-8c1f-088230e6e9a2" width="800"/><br>Fig 11. 2010-2018 DOE 35-105m DO (averaged per cast) with linear best-fit line.</p><br>

(*Oops - I realize they are using mL/L and I'm using mg/L. They are within the same order of magnitude and slopes look similar. I'll try to fix this before our meeting tomorrow.*)

Both have slopes and shapes similar to those shown on the EPA webpage, though it's difficult to compare apples to oranges without understanding their precise data analysis. We note the poor r^2 values (due to seasonal variation, likely). We also note that there is subtle downward slopes to both regression lines, which leads to a conclusion of "declining" water quality on the EPA site. Now, I'll create plots like this using all years available right now:


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/5285f59b-36db-4fdb-97dc-f4778f6852bc" width="800"/><br>Fig 12. DOE 0-35m DO (averaged per cast) with linear best-fit line.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e839ffe5-efeb-4d10-8676-6db87ad74de3" width="800"/><br>Fig 13. DOE 35-105m DO (averaged per cast) with linear best-fit line.</p><br>

We see these slopes are much less apparent than their smaller timerange counterparts. We see what appears to be multi-annual/decadal variation in this time series as well. Once again, we motivate our work trying to understand this data on multiple timescales.

We also discussed analyzing individual DOE sites, given their spatial consistency for the last two decades. There are 22 total sites. For each of these sites, I've ploted its location and its bottom SA/CT/DO based on the bottom 20% of the cast's water column based on the LO grid, averaged per cast during my "growing/respiring season" (see previous section). Here's a video for space efficiency! (*I have not had a ton of time to synthesize these findings yet, but will try to do so before the meeting.*)

<p style="text-align:center;"><video src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/2e66cd4f-99f7-4c92-86a0-e1c695b328d0" controls="controls" style="max-width: 800px;"></video><br>Fig 14. DOE sites and bottom 20% "growing season" average per cast for SA/CT/DO.</p><br>


---

## Other Action Items

Here's some more to-dos for my tracking/your knowledge:

* Keep an eye on requested Ecology data from 1973-1998.
* Set up chat with Christopher Krembs regarding data usage.
* Taylor sent Point Jefferson KC data (1975-present) - incorporate into analysis, could be helpful as decadal source.
* Reach out to Dave Clark regarding analysis and collaboration for PNCWA conference.
* Keep an eye on requested Metro Vancouver data from Alysia Herr.

---

## General Exam Status Update

Last week, we shuffled around my chapters a bit... (I need to update my outline.)

* **Chapter 1:** *Also Paper 1...* Analyzing Decadal, Annual, and Spatial Variation of Salinity/Temperature/DO in Puget Sound
* **Chapter 2:** Analysis of shallow cove/embayment hypoxia development and mechanisms using observations (KC Whidbey Basin data) and a high-resolution nested model! Given that most of the hypoxia we observe both from field measurements and via models is showing up in shallow regions and we now have nice data for Penn Cove, this is an important piece of the puzzle!
* **Chapter 3:** dentifying mechanisms for DO change from observations. Expand to include BGC variables. Expand to include Strait of Georgia/Strait of Juan de Fuca? Episodic timescales? (Still not so fine-tuned here.)

Gotta read!

Finally - I need to formally schedule this with the department.

---


## Miscellaneous

Thoughts for posterity:
* New paper: Alin et al. (2024) - WOAC OA/DO trends 2014-2018
* Review Collias publications for early data context.
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)
* Taylor to provide 1970-2000 Point Jefferson data.


---

## Bookkeeping
* Ocean Sciences - no reimbursements yet for recent expenses.
* General Exam - scheduled 6/18
* PECS - ORAL presentation accepted! 9/23-9/27


---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. ...

