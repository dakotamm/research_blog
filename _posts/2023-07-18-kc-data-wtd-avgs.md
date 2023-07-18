# KC Data Cleaning, Weighted Averages, and Summer Planning

### Goals From Last Meeting:
1. Different lenses for analyzing trends - seasonal, avg. below 40m DO, T/S analysis, etc.
2. Data cleaning for KC/Whidbey Basin data.

### Completed Goals:
1. Data cleaning for KC/Whidbey Basin data.
2. Weighted average plot below 40m.

* meg stuff??
* greg johnson stuff

---

## KC Data Cleaning

Since last meeting, I have downloaded and have been working to pull in KC data (including Whidbey Basin monitoring). I've started with downloading what's currently available on the KC site, which is a large dataset with all water quality monitoring data (includes Whidbey Basin new monitoring) and Whidbey Basin CTDs. **Note:** Taylor has mooring data from Coupeville and Port Susan, but has not gotten back to me with it.

The data, as assumed, is pretty messy and odd to work with. A few questions and notes:
* KC seems to have combined earlier CTD data into the "water quality/bottle" data spreadsheet. Should we keep this in the "bottle" category or sift this into "ctd" format?
* Does every bottle cast have to have salinity/temperature?? (Example: ecology uses CTDs taken concurrently and puts that into bottle formatted data.)
* Further documentation questions (probably for KC):
  * I'm not sure if the measurements are already "conservative temperature" and "absolute salinity," or if conversion is required (documentation isn't clear).
  * "Silica" = SiO4?
  * "Orthophosphate phosphorus" OR "total phosphate" = PO4?
  * "- field" suffix - does this mean pre-QA/QC?
  * UTC or local time?
  * *(A good argument for super-specific READMEs and documentation!)*

Currently, I'm pretty close to an infrastructure that can get it into a similar format as "ecology," "dfo," and "ncei" data formats. It is using a slightly different mechanism than Parker's scripts but is similarly time efficient. (**Parker** - perhaps we can review this in an offline meeting?)

It's been very useful to be able to look at real data and see what it is we actually have to go off of. Here's a list of other data sources that could be helpful:
* Strait of Georgia Data Centre (https://sogdatacentre.ca/atlas/citscidata/) - other than DFO.
* Collias (when Parker has cleaned it).
* ORCA buoys

---

## Some Work on Trends

I spent some time getting weighted averages for state variables up and running. I am almost ready to have a plot...

As of right before the meeting I do not have this plot yet. 

**Please pretend this plot also has weighted average DO concentration.**

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/a7a93be9-9d82-440e-9cf7-fc6da9a97c10" width="800"/><br>Fig 1. Regional hypoxic volume in the Salish Sea since 1930.</p><br>

---

## Planning

**Guiding Science Questions & Objectives:**
* Using observational data, how has dissolved oxygen changed over time in the Salish Sea?
  * What are the spatial and temporal patterns? Are certain areas exhibiting similar or disparate trends?
* Can we observe trends in hypoxic volume using observational data? How confidant are we in these estimates?
  * What tools do we need to understand uncertainty?
* What are we limited by in areas that are predicted to have high incidence of hypoxia?
  * Do we need more observations? Can we plan this?
  * Do we need more modeling?
* Can we explain any trends using observations and theory?
* Are there specific areas that should be studied in more depth, such as Penn Cove, Lynch Cove, etc.?
* Compile all available observational data for these tasks.
* Build datasets for model evaluation and intermodel comparison.

 
**Some Broad Notes:**
* I'd like to complete my PhD by Spring 2026 (or earlier!). During this time:
  * I want to hone data science skills via the CEE Data Science Option certificate (requires ~2 more classes).
  * I want to improve public speaking and grow overall confidence in my work and ability.
  * I want to become more proficient at coding and graphic design.
  * **I hope to get some experience using LiveOcean and ROMS for future job opportunities.**
  * **I hope to get experience scoping and potentially conducting meaningful fieldwork.**
    * There may be opportunity to do this with WWU faculty in some capacity.
    * Can we broach the idea of tagging along with King County again?
* I'd like to do my General Exam in Spring 2024.
* Concurrently, I'd like to aim for my first publication (Spring 2024).
* Potential conferences:
  * OSM 2024
  * PECS 2024

### This Summer

**Big Picture:** I want to dig into the data and start understanding some trends, or perhaps lack thereof. There has been discussion regarding more advanced statistics to understand uncertainty; this is something that I'd like to let simmer while I begin digging in more. (Also, the UW Stats department doesn't resume consulting until Fall. It seems like an interesting idea to pursue at that point.) By the end of summer, I'd like to come up with a hypothesis that may form a dissertation chapter regarding trends in hypoxic volume in the Salish Sea. This may be something to do with differences in trends observed in various regions. *I will be working remote Monday, August 21, 2023 - Friday, September 15, 2023.*

#### Rest of July
1. Data exploration - what can we see so far in DO data? Other state variables? What is the spatial variation?
   * Plot trends in temperature, salinity, wind, upwelling, climate indicators, WWTP, etc.
3. Pull in KC Penn Cove data. Work with model evaluation in Penn Cove with Aurora (scoped July 24-August 18).
4. Investigate and incorporate all available data (e.g., Colius, etc.).
5. Continue to track uncertainties and think toward further analysis.
6. Literature review - especially Stramma et al. (2008) & (2010) (with Greg Johnson) to understand techniques in using cast data in larger ocean.
7. Reach out to Susan Allen's new post-doc starting some work with observational data.

#### August
1. Continue to work with Aurora on Penn Cove deep dive.
2. Hypothesis formation for Chapter 1/first paper.
3. Continue to pull in all available data.
4. **Learn how to run LO model?**
5. KC update meeting.
6. Remote work on PDT Monday, 8/21 - Friday, 8/25.
7. Remote work from Europe Monday, 8/28 - Friday, September 15.
   * I won't be able to attend our regularly scheduled meetings - could meet at alternative times.
   * Prioritize independent work such as dataset incorporation/model learning?
  
#### September
1. Remote work from Europe Monday, 8/28 - Friday, September 15 (see above).
2. Vet hypothesis for Chapter 1/first paper.
3. ?

### Fall 2023
1. Classes: CEE 464 (Mike's limnology class) + CEWA 565 (Data Analysis in Water Sciences)
2. Hypothesis testing for first paper/Chapter 1.
3. Consulting with UW Stats department.
4. Plan EFM presentation.

### Winter 2024
1. Start work on general exam + confirm three chapters for dissertation.
3. Start on paper draft.
4. **OSM 2024?**

### Spring 2024
1. General Exam.
2. Refine paper for summer publication?

---

## Bookkeeping 
* August 21 - September 15, 2023 remote work...

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. Organize literature - Endnote?

### Looking Ahead:
1. Continue data exploration.
2. Continue data cleaning.
3. Reach out to Greg Johnson!

### Goals For This Week:
1. 
