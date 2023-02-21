# KC Drafts, EFM Presentation, and Transects

### Goals From Last Week:
1. Gordon Conference Abstract - finalize and submit.
2. KC deliverables - slides and document.
4. Continue on volume estimation scheme - quantify errors.

### Completed Goals:
1. Gordon Conference abstract - submitting today, 2/21/2023.
2. KC deliverables drafts sent 2/21/2023, to be reviewed here.
3. EFM meeting presentation MOVED to Thursday, 2/23/2023. To be reviewed here.
4. Continued on volume estimation scheme.

---

## KC Deliverables

KC deliverables for meeting Friday, 2/24/2023:
1. ~15-minute presentation on progress/goals.
2. 1-page document detailing progress/goals.
3. Updated academic year plan.

I sent drafts of all three deliverables this morning, 2/21/2023. For the presentation, I will take ample time to format correctly and add missing figures if necessary. Revisions to wording and grammar on the documents are likely necessary! Overall, I have a few questions:
1. Do I need a timeline in my presentation?
2. If so, should I include a "before" and "after" timeline (as in, one from last quarter and then one that shows that I've changed the schedule)?
3. Is my presentation too detailed?
4. Is there a better word for "volume-from-casts" method???

**Note:** KC fieldwork...

Below is my revised academic year plan draft:

# Academic Year Plan (Winter Revision) DRAFT

**Guiding Science Question:** *What are the long- (several decade) and short-term (within the last decade) trends in dissolved oxygen and affecting factors in Puget Sound and the Salish Sea?*

**Winter 2022**
*Question/Objective:* Using data from a single source, how has hypoxic volume changed over time in the Salish Sea?
•	Selected data source: Canadian Department of Fisheries & Oceans (DFO) CTD & bottle casts due to temporal range (since 1930s), spatial coverage of the Strait of Georgia, relative completeness within these ranges, and existing data framework.
1.	Validate and understand errors/biases associated with the volume-from-cast method.
2.	Use volume-from-casts to understand long term trends in hypoxic volume and associated state variables within DFO dataset.


**Spring 2023**
*Question/Objective:* How do trends in hypoxic volume correlate and vary working with more datasets?
•	Additional data sources:
o	King County Marine Water Quality Monitoring
o	WA Dept. of Ecology
o	Collias
o	USGS (rivers)
o	NCDC (climatology)
o	WOAC cruises
o	NANOOS (ORCA buoys)
o	Port Susan Stillaguamish mooring/casts
1.	Pull existing datasets into framework.
2.	Apply volume-from-casts method to additional datasets.
3.	As part of this process, build validation routines for LO.
4.	Qualifying exams (April).


**Summer 2023**
*Question/Objective:* Synthesize and analyze long-term trends in hypoxic volume and related metrics for the Salish Sea and Puget Sound. 
1.	Compare findings in datasets for region-specific information and cross-validation between sources.
2.	Begin draft of journal paper: methods, literature review (ongoing).
3.	Continue work on LO validation.
4.	Compile intermodel comparison benchmark datasets.
5.	WOAC cruise (July).
6.	Conference preparation.
7.	Target journal paper draft completion by beginning of summer.


**Fall 2023**
*Question/Objective:* Continue to synthesize and analyze long-term trends in hypoxic volume and related metrics for the Salish Sea and Puget Sound.
1.	Paper revisions.
2.	Conference preparation.

---

## EFM Presentation

My presentation to the EFM group has been shifted forward a week to Thursday, 2/23/2023. I figure I will adapt my KC presentation as follows:
1. Remove all planning discussion.
2. Pick up where Aurora left off - offer brief discussion of factors in hypoxia.
3. Detail observational data sources.
4. Discuss "volume-from-casts" method and challenges associated.
5. Expand possible errors discussion.

---

## Volume-From-Casts Method - Transect Troubles

I have spent some time this week trying to create different visualizations, such as transects, to begin to understand errors in the method. I have created transects adapting LO/plotting/roms_plots.py "P_sect" method for LO output data for each time point in the study discussed in more detail last week. However, I am running into a bizarre bug that I can't figure out how to solve - the transect isn't recognizing land. The following figure is taken from LO output data on July 1, 2022.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/220457281-181ae871-e379-4892-8022-e382f4d4943c.png" width="600"/><br>Fig 1. DO transect from LO output data taken July 1, 2022.</p><br>

(Noting that what appears to be East Sound in the transect has bottom hypoxia, as seems to be the trend in shallow embayments.)

Perhaps my transect isn't where it thinks it is? Is something wonky with the land mask and/or wet and dry gridcells? Is this "extra volume" causing errors in my LO output data measurements? Likely my own user error somewhere...

---

## Bookkeeping 
* EFM Talk **rescheduled** for Thursday, February 23, 2023 (20 minute presentation)
* KC Meeting scheduled for Friday, February 24, 2023
* Gordon Conference Abstract - submitting today, 2/23/2023
  * I may have a conflict with Sunday/Monday of conference dates.
* Ocean Visions Summit: April 4-6, 2023 - need to confirm
* Quals: April 17-21, 2023 - need to confirm Friday oral defense time, waiting on CEE formal procedures.
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Transect bug...
2. How to do transect from casts...things to noodle on.

### Looking Ahead:
1. Gordon Conference Abstract - submit today.
2. KC deliverables - polish for secondary review tomorrow, 2/22/2023.
3. EFM presentation - polish for secondary review tomorrow, 2/22/2023.
4. Continue on volume-from-casts method.

### Goals For This Week:
1. 
