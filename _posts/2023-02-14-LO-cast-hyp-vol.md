# Finding Hypoxic Volume from LO Casts + KC Planning

### Goals From Last Week:
1. Gordon Conference abstract.
2. Fully implement test hypoxic volume scheme.
3. KC deliverable overview starting next week.
4. Set quals date with Mike/Parker/Alex.

### Completed Goals:
1. Gordon Conference abstract - sent 2/14/2023.
2. Fully implement test hypoxic volume scheme!
3. KC deliverable review - preliminary included here.
4. Set quals date with Mike/Parker/Alex - 4/17-21/2023.

---

## Hypoxic Volume from LO Casts

Finally! Hypoxic volume from LO Casts!

I was able to fully implement a method that takes given cast locations, creates LO casts, then estimates volume under a certain threshold of DO for the area applicable to the cast. I conducted this study using 9 locations (sampled from DFO sites June-August 2019) and then I applied these casts locations to LO history files on the 1st of each month during 2022. The figures below shows DO profiles from January, April, July, and September:

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218854992-590d1fb7-3841-4997-ba8a-14047bc09f1e.png" width="600"/><br>Fig 1. DO profiles from LO casts taken January 1, 2022.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218855189-6157926d-e390-4a18-8474-f4b4006159c7.png" width="600"/><br>Fig 2. DO profiles from LO casts taken April 1, 2022.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218855270-41d23267-df11-4c65-ae04-da145df0308f.png" width="600"/><br>Fig 3. DO profiles from LO casts taken July 1, 2022.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218855357-d5999d86-358d-44b4-a1fb-c0d76fae238c.png" width="600"/><br>Fig 4. DO profiles from LO casts taken July 1, 2022.</p><br>

We can see seasonal variation throughout the selected months; July and September have comparatively lower DO than winter and spring.

After assigning areas to each cast, I can then find which areas have DO under a certain threshold anywhere in the represented water column. In this case, I've shown 5.0 mg/L (since this region doesn't reach 2.0 mg/L or less during this study, and I needed to make plots...). An example from July is shown below.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218857272-a61a635a-50be-44ff-916b-af01d7834605.png" width="600"/><br>Fig 5. LO cast areas with DO concentration under the 5.0 mg/L threshold somewhere in the water column, from LO casts taken July 1, 2022.</p><br>

Now, I can compare this to LO grid data by finding the bottom area under the DO threshold, shown below for all four months:

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218858098-e1a44d66-f0fc-4603-88d9-43c5510b54e8.png" width="1200"/><br>Fig 6. LO cast areas with DO concentration under the 5.0 mg/L threshold vs. LO bottom grid data, from LO casts taken January 1, 2022.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218858171-a1a9f0d7-e8a2-48f4-b5b2-0cbffaf88a60.png" width="1200"/><br>Fig 7. LO cast areas with DO concentration under the 5.0 mg/L threshold vs. LO bottom grid data, from LO casts taken April 1, 2022.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218858210-3cda483c-8af7-4e4e-9c17-2c092f5b41fa.png" width="1200"/><br>Fig 8. LO cast areas with DO concentration under the 5.0 mg/L threshold vs. LO bottom grid data, from LO casts taken July 1, 2022.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218858567-8cb1f74c-4ce6-4855-890e-64edbfec8482.png" width="1200"/><br>Fig 9. LO cast areas with DO concentration under the 5.0 mg/L threshold vs. LO bottom grid data, from LO casts taken September 1, 2022.</p><br>

We can see that there are certainly some bottom DO differences between LO cast estimation and LO grid data. To understand the three-dimensional comparison, we can plot trends in total volume below the DO threshold throughout the year for both LO casts and LO grid data.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/218859406-a1fda2ce-0dd8-46ed-b842-fb576db673ba.png" width="1200"/><br>Fig 10. LO cast volume estimation under DO threshold vs LO grid data throughout 2022.</p><br>

Overall, I'm just excited I got this to work. Next is assessing errors with this method and digging into observational data.

Some thoughts: 
1. Error estimate methods...
2. Interpolation within gridcells (volume partitioning).
3. Averaging - currently only looking at one history file at a time.

---

## KC Meeting Planning

Here are some outlines for the KC slides and document that we'll present next Friday, 2/24/2023.

*Guiding Science Question (maintained from last document):* What are the long- (several decade) and short-term (within the last decade) trends in dissolved oxygen and affecting factors in Puget Sound and the Salish Sea?

*Progress Since Last Meeting:*
During Autumn 2022, I began by using data from a single source to understand how hypoxic volume has changed over time in the Salish Sea. As I delved into this task, I came to require a framework with which to understand spatial data. I created a "testing environment": I was able to conduct "model" CTD/bottle casts using the LiveOcean framework. I used locations from DFO CTD/bottle casts and constrained a test domain to create volume estimation methodology. Given the high resolution inherent within LiveOcean's structured grid, I have used volumes defined by the LO grid domain.

At this point, I have successfully used "model" CTD/bottle casts and have create schemes that estimate hypoxic volume given cast information. Comparing to LO grid data (i.e., using the whole LO domain versus just information given in a "model" cast), I find good agreement between the model cast method. A wide range of conditions can be applied to estimate errors introduced by this method, given specific spatial and temporal distribution of observational casts.

Since using a LiveOcean testing environment proved the most efficient way to create with volume estimation schemes, the next step is to apply this methodology to a single data source - DFO data. After understanding trends in hypoxic volume within this dataset, I will extend analysis to other data sources and extend this throughout the quarter.

Note: This means I'll update my Winter Quarter 2023 plan (below) to include starting with DFO dataset now that estimation scheme works...

Note Note: KC fieldwork...


FOR REFERENCE (last quarter's plan):

Autumn 2022
Question/Objective: Using data from a single source, how has hypoxic volume changed over time in the Salish Sea?
• Selected data source: Canadian Department of Fisheries & Oceans (DFO) CTD & bottle casts due to temporal range (since 1930s), spatial coverage of the Strait of Georgia, relative completeness within these ranges, and existing data framework.
1. Within existing framework, create method to understand volume-based (hypsographic) estimates for state variables (e.g., temperature, dissolved oxygen).
2. Understand long term trends in hypoxic volume within DFO dataset.

Winter 2023
Question/Objective: How do trends in hypoxic volume correlate and vary working with more datasets?
• Additional data sources:
o King County Marine Water Quality Monitoring o WA Dept. of Ecology
o Collias
o USGS (rivers)
o NCDC (climatology)
o WOAC cruises
o NANOOS (ORCA buoys)
o Port Susan Stillaguamish mooring/casts
1. Pull existing datasets into framework.
2. Apply method derived during Autumn quarter for volume-based estimates of state variables to
additional datasets.
3. As part of this process, build validation routines for LO.

Spring 2023
Synthesize and analyze long-term trends in hypoxic volume and related metrics for the Salish Sea and Puget Sound.
1. Compare findings in datasets for region-specific information and cross-validation between sources.
2. Begin draft of journal paper: methods, literature review (ongoing).
3. Continue work on LO validation.
4. Compile intermodel comparison benchmark datasets.
5. Potential WOAC cruise (April).
6. Qualifying exams.

Summer 2023
Question/Objective: Continue to synthesize and analyze long-term trends in hypoxic volume and related metrics for the Salish Sea and Puget Sound.
1. Target journal paper draft completion by end of summer.
2. Consider conference preparation.

---

## Bookkeeping 
* KC Meeting scheduled for Friday, February 24, 2023
* EFM Talk scheduled for Thursday, March 2, 2023 (20 minute presentation).
* Gordon Conference Abstract - draft sent.
  * I may have a conflict with Sunday/Monday of conference dates.
* Quals: April 17-21, 2023 (yikes)
* WOAC Cruise: July 10-14, 2023???

---

### Issues/Questions:
1. How to do transects in LO?

### Looking Ahead:
1. Gordon Conference Abstract - finalize and submit.
2. KC deliverables - slides and document.
3. Continue on volume estimation scheme.

### Goals For This Week:
1. 
