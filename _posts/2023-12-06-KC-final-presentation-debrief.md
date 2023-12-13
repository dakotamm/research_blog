# KC and Final Presentations Debrief and Future Planning

### Goals From Last Meeting:
1. KC quarterly meeting 11/30
2. CEWA 565 presentation 12/5
   
### Completed Goals:
1. KC quarterly meeting 11/30
2. CEWA 565 presentation 12/5

---

## KC and CEWA 565 Final Presentation Debrief

Last Thursday, we met for our quarterly review with King County. After some iterations, I presented the results of a preliminary statistical analysis where I discussed a change of means of monthly average DO before and after 2010, analyzing combinations of different depth bins (full depth, shallower than 35m, 35m and deeper), seasons (including analysis of the full year), and different Puget Sounds regions (including all Puget Sound, Main Basin, Whidbey Basin, Hood Canal, and South Sound). I also discussed whether or not there was a decreasing trend in the various data partititions, and set the stage for some preliminary correlative studies with monitored and environmental data.

Largely, the KC content remained the same as in last week's blogpost. I did emphasize a conclusion that for Hood Canal in the fall in particular (where we are most concerned about increasing hypoxia given measured lower DO), there is no statistically significant decrease in DO observed. I got some insightful comments from the crowd:
* Taylor reminded me that King County had used the **Mann-Kendall** test for monotonic trend within their data in lieu of my linear regressions (with very poor fit) for assessing if a time series had significant trend. I did some more reading and did use this for my final presentation, and I'll show that shortly.
* Mike recommended that I use LOESS slope-fitting to identify the seemingly periodic trend in the data.
* The team recommend I investigate correlation with loading trends from Dept. of Ecology, which is definitely a good next step.
* Parker recommended "polygon-ing" Saanich Inlet and looking specifically at trends there. This would be interesting given Tall's interest in increasing their model's performance in this area and also because there is tons of data there.
* Taylor recommended looking into upwelling and regional climate indicators like NPGO (as well as PDO and ENSO) as covariates. I agree!

Yesterday, I morphed the KC presentation and presented it as a final project for my data analysis class (CEWA 565). I made a few changes. First, I only focused on deep DO (>35m depth) so that I could streamline the discussion (and honestly present more meaningful data in lieu of a full-depth average). Second, I did change my time trend analysis to use a Mann-Kendall trend analysis given the poor linear fit of the data on Taylor's suggestion. The results were not markedly different, but I'll show both here so we ca

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/63ada13b-35d1-4a5c-9f28-097197981c1b" width="800"/><br>Fig 1. Least-squares linear regression (left) and Mann-Kendall (right) trend significance for deep DO in Puget Sound from 1999 to 2019.</p><br>

The conclusions I presented were similar (that bad DO areas/times are not getting worse). I got some interesting questions:
* A classmate asked the physical and biological reasons Hood Canal in the fall is expected to have the lowest deep DO. I don't know if I gave her an excellent explanation, but explained my thoughts on high residence time and high productivity. Unfortunately I also reminded myself that I need to review and come up with better explanations for physical intuition here.
* Steven (the lecturer for the class) asked if the poor linear fits I saw were due to large seasonal and how I was worked to mitigate that data effect. I mentioned that yes there is large seasonal variation, and I did analyze by season, and also found poor linear fits. I realize that this implies that the contribution of variation that makes linear fits poor is mainly interannual... And so I'm both pondering this question and wondering what else one can do to analyze time series with significant seasonal and interannual variation... Perhaps understanding which (interannual or seasonal) variation is more significant in a more qualitative way would be a good first step.

I'd love any more thoughts and comments you have on the KC presentation or otherwise!

---

## Next Steps

As the quarter winds down and I get a few big presentations out of the way, now seems a good time for some refocusing. Here's an outline of a few big ticket items and some ideas on approaching them.

* 2/22: Ocean Sciences Poster
  * Option 1: Continuing this statistical trend analysis, extend this to Strait of Georgia + longer timescale with Colias dataset
    * Include King County data, ORCA buoys, Whidbey mooring data
    * Extend to other variables other than DO? Salinity? Temperature? NO3?
    * May be too much to add analysis of all correlated variables -> drivers
  * Option 2: Narrow in on a region, try to ascertain the different drivers...
    * Eg. Hood Canal fall DO
      * Examine streamflow, precipitation, PDO/ENSO/NGSO, nutrient loading from DOE
  * For now - leave "volume-based" measurements on the back-burner?

* Spring/Summer 2023: Paper 1
  * Continue whichever direction we decide for Ocean Sciences poster.
    * "long term change in Salish Sea DO and other variables".
    * Include drivers analysis...
      * Seems like a combo of the two poster options above?
    * Would volume-based measurements be important here? How do I make this decision?

* Spring 2023: General Exam (Thesis Proposal)
  * Part 1: Paper 1 content!
  * Part 2: ??? specific regional analyses
  * Since I already have a Masters (albeit in a different group), how many "chapters" are warranted? I've heard two for pre-existing MSCEs...
  * Where does Penn Cove stuff fit? Learning how to run LO?
  * Incorporating reading...

I realized it's a bit early for a swanky Gantt chart for my General Exam, but I'd love to get there next week after our chat today.

---

## Bookkeeping 
* Working Remote: 12/6-12/8
* Vacation: 12/18-12/22
* Ocean Sciences: 2/18/-2/23
* General Exam Timeline?
  
---

### Looking Ahead:
1. ORCA buoys - incorporate this into trend analysis ASAP.
2. KC data cleaning - ascertain the relative impact to the trends found; complete data incorporation into LO ecosystem.
3. Upwelling data - look into NANOOS NVS (NDBC or the NSF OOI Endurance Array).
4. Are warming events more common in NE Pacific? Paper??? (Ref. [this](https://www.pugetsoundinstitute.org/2023/09/warm-ocean-waters-work-their-way-into-puget-sound/) Puget Sound Institute article Parker pointed toward me...)
5. Penn Cove nitrogen budget with WWU + Penn Cove nested model...
6. Keep on Taylor for me to be involved in KC Whidbey sampling...

### Goals For This Week:
1. Continue to scope future work.
2. Discuss general exam next week.
3. Make time series plots with confidence intervals for next week.
