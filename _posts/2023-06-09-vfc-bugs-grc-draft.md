# VFC Bug Squashing and GRC Poster Draft

### Goals From Last Meeting:
1. Incorporate DO inversion handling + shallow casts usage.
2. Run hypoxic and interannual conditions.
3. GRC poster draft - target by end of this week.
4. CEE PhD Performance Review - draft by end of this week (push to next).

### Completed Goals:
1. Incorporate DO inversion handling + shallow casts usage.
2. Run hypoxic and interannual conditions.
3. GRC poster draft - almost there.

---

## VFC Bugs and Bettering

This last week I have spent copious amounts of time working through my VFC method to improve and build new functionality. Broadly, I have accomplished the following improvements:
1. DO inversion handling - now incorporates true hypsometry in lieu of cutoff depth.
2. Shallow-cast handling - now removes all casts that don't reach 80% of total depth.
3. I've run hypoxic and interannual conditions with available observational and LO data from 2008-2017 (on perigee).

This came via some large hurdles. I ran into a substantial bug while incorporating the first two. Specifically, a great deal of time was spent learning a hard lesson about deep and shallow copying and being utterly confused why running methods defined outside of a script had dependence on one another. Fortunately I figured out that certain datatypes shallow and deep copy differently, and that I should just deep copy everything and avoid that pain.

Finally, my VFC codebase feels pretty iron-clad and I am able to represent subthreshold volumes with more confidence.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6bf57632-2413-4a81-8eb8-6b9f429c778d" width="500"/><br>Fig 1. Strait of Juan de Fuca time September 2017 sub-5mg/L DO thickness after many trials and tribulations (yay!).</p><br>

I am finally also able to represent interannual variability. In this case, I'm showing all available data from 2008-2017 (mainly obs, with some LO history and LO casts). More on this in the poster review.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/6917a7ee-0837-41d6-aa59-974a1d374904" width="800"/><br>Fig 1. Salish Sea 2008-2017 hypoxic volume.</p><br>

*Given the huge coding effort this week, I have not yet had time to fully vet all of these results.*

I'll leave my updated to-do list here.

This is the first step among many steps, but at least is a fun and exciting first look at some observational data. Here are some next steps (some from the KC meeting, but generally):
* ~~Get set up to run on perigee - in lieu of using just one history file to represent a month for personal computer space efficiency, start working with the full suite of model data and perform analyses more quickly.~~
* ~~Incorporate variable inversions + cast depth checking.~~
* ~~Start looking at interannual variability.~~
* Investigate differences in time-binning.
* Investigate Whidbey Basin vs. Strait of Geogia (e.g.) differences in error (Whidbey Basin tends to have less throughout the year).
* Apply uncertainties to measurements of subthreshold volumes estimated with VFC.
* Refine statistical understanding and presentation of errors and biases - what's the best way to do this?
* ~~Conduct analysis of hypoxic volume (<2.0 mg/L).~~
* Conduct analyses of different domains, time periods, and state variables of interest.
* Continue refinenement of codebase and work towards making it more time efficient.
* Clean and incorporate more data (especially KC Whidbey Basin data).
* ~~Define GRC poster scope.~~
* Synthesize trends -> paper draft toward end of 2023???
* Work with Ben/Aurora on what I can build to be helpful!

---

## GRC Poster Thoughts

I am definitely behind on my draft. I sent via email on Friday, 6/9/2023 a template with few non-vetted plots. 

After the KC meeting push, I'm looking towards drafting by GRC poster by the end of next week. A rough outline is as follows:

* Title: Spatiotemporal Trends of Dissolved Oxygen in the Salish Sea
  * Caveat preliminary analysis...
  * Motivation of DO in Salish Sea - why it's important to understand trends, factors that might influence
  * Describe VFC method in depth, discuss sampling error, emphasize obs data analysis technique
  * Interannual variability - start proposing drivers?? Covariation of DO with other state variables?
  * Trends in DO over one year (discuss natural variability?) ???
  * Tie in with model - modeling error?

My draft is lagging but will be ready to be printed as soon as I start to piece together my plots.

---

## Bookkeeping 
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* CEE PhD Performance Reviews: due 6/30/2023
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. Organize literature - Endnote?

### Looking Ahead:
1. GRC poster draft - finish ASAP.
2. CEE PhD Performance Review - finish ASAP.

### Goals For This Week:
1. GRC poster draft.
2. CEE PhD performance review draft.
