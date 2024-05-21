# Mann-Kendall Trends for Decadal and Annual Time Series

### Goals From Last Meeting:
1. Work on integrating new KC data into LO - README + Parker review.
2. Decadal and annual time series.
3. Work on General Exam/Paper 1 - write write write.
4. Formally schedule General Exam with CEE.
5. Process all new data.
6. Follow up with Ecology and Metro Vancouver.
   
### Completed Goals:
1. Decadal and annual time series - in progress.
2. Working on General Exam/Paper 1 - literature review nearly there. Scope feeling more dialed for Paper 1.
3. All new data processed (mainly Point Jefferson KC).

---

## Decadal Trend Analysis

Alongside all the writing, here's some new rough data analysis for Paper 1 scope. I have taken all 8 decadal sites and partitioned the data in two ways:
1. Seasonally (summer/non-summer, defined as inside and outside of yeardays 125-325)
2. By depth (surface: 5m and shallower like MacCready & Banas 2016 report; depth: bottom 20% of site water column)

I've created yearly averages to explore these decadal trends, then I applied a Mann-Kendall test of monotonic trend (since we can't assume normal distribution of residuals around a linear trend nor do we have sufficiently large sets in all cases). NOTE that this test does not necessarily imply direction! I'll have all the time series ready to go to dig into trends during the meeting if need be.

(Also there are sites which have discontinuous data for different seasons (e.g., Near Seattle Offshore during non-summer). This is also impacting the trend results. I think the best way to review this is to pull up time series individually, which doesn't read well and is too much for the blog, but I can do during our meeting. I digress.)

Here's an example of time series in Main Basin...


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/120facff-a9f8-4d62-8d10-78dc22205158" width="600"/><br>Fig 1. Main Basin decadal sites with DO MK trend test information; light color is surface and dark color is bottom.</p><br>

A magenta text with "True" indicates that we reject the null hypothesis and there is evidence for a statistically significant trend. I've summarized the results of this test throughout Puget Sound for all three variables as follows:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/0e642b99-16e5-4840-91c8-0294f2b57cc3" width="600"/><br>Fig 2. Puget Sound signficant decadal MK trends for SA.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c626ca30-45c1-4477-bd0c-e24c3bc95a67" width="600"/><br>Fig 3. Puget Sound signficant decadal MK trends for CT.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/5783a2c2-d4bf-4b6b-a0b2-ef5e988df701" width="600"/><br>Fig 4. Puget Sound signficant decadal MK trends for DO.</p><br>

**NOTE:** I am concerned that Hat Island actually has too few data points to ascribe trends to. I may remove this from the analysis.

I finally feel like I believe in this data analysis! Next step in this scope is understanding potential oscillation and variability. However, given the spotiness of the data, classic time series analysis (like FFT) are not really appropriate.

*Any thoughts on how to tackle frequency of variation on decadal/annual scales using this set?*

When I write up this analysis, my thoughts are to break out the discussion regionally, seasonally, and by depth. I will mention concurrent trends of state variables, but so far I'm not to the stage of assigning mechanisms - which is not in my Chapter 1 scope, so I feel like this analysis is on track for the appropriate scope.

---



## Annual Trend Analysis

I performed a similar analysis with Ecology sampling stations! Without showing gazillions of plots, I removed data sites that weren't consistently sampled over the 20-year available period, as I've found plots with few points can have erroneous trend output using Mann-Kendall tests (I can show you all the raw data here, but it's omitted for brevity).

Here's plots showing where "True" trends are from the MK trend tests:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6e54d5a1-e155-44a4-8b8a-4f43f6a5e03c" width="600"/><br>Fig 2. Puget Sound (Ecology) signficant annual MK trends for SA.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f4ce0b42-3d9a-4a9f-8778-4c24e50c9d8b" width="600"/><br>Fig 3. Puget Sound (Ecology) signficant annual MK trends for CT.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/453a0869-35f1-4706-a9f0-11c7b2d3efb" width="600"/><br>Fig 4. Puget Sound (Ecology) signficant annual MK trends for DO.</p><br>

Similarly, I haven't tried a frequency analysis. I'm open to suggestions on how to tackle that as I read.

---

## Writing

Eek. I'm overwhelmed. But I have made some progress in terms of literature review and what I'm calling a conceptual model of DO in Puget Sound, and I feel like I'm starting to believe my own data analysis. I would like to get drafts out for my literature review and methods sections for my Paper 1 within the coming days...

HOWEVER - I realized my time-till-General-Exam is dwindling. I'd love your input on scoping paper writing vs. general exam focus writing for this week.

---

## KC Quarterly Update

Double eek. I will put together some drafts, but I have admittedly not been prioritizing this as high as I do most months.


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

**I need to formally schedule this with the department at least a week before.**

---


## Miscellaneous

Thoughts for posterity:
* Review Collias publications for early data context.
* Gappy temperature data in SOG - investigate this.
* 1970-2000 data - does it exist? Ask around...(DOE, Mesa Program)


---

## Bookkeeping
* Ocean Sciences - no reimbursements yet for recent expenses.
* KC Meeting - 5/23
* General Exam - scheduled 6/18
* PECS - ORAL presentation accepted! 9/23-9/27

---

### Looking Ahead:
1. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
2. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/))
3. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. KC meeting!
2. Write!!!

