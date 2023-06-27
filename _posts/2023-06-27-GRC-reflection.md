# GRC Reflection and Summer Planning

### Goals From Last Meeting:
1. GRC poster completion.
2. CEE PhD performance review.

### Completed Goals:
1. GRC poster completion.

---

## GRC Reflection

Last week was a super exciting and valuable experience and I was glad to participate! After awesome and totally novel talks about hurricane resilience, internal waves caused by glacial calving, and subterranean estuaries suffice to say my mind is sufficiently blown and I'm really excited to be a part of this awesome community. I really appreaicated the speakers' ability to engage the audience and certainly hope to use that as inpiration for future work. In particular, I found Susan Allen's teaching style to be super effective! I was able to make some good connections with Susan, John Wilkin, Jody Klymak (UVic), and Erica McPhee-Shaw (WWU), among many other students and faculty.

At the poster session, any anticipation was quickly rewolved and folks were generally supportive and enthusiastic. It was also very valuable to see some later-in-grad-school work that was extremely compelling - goals! The following is a list of some comments and suggestions folks had:
1. John Wilkin and Rob Hetland were intrigued in ways to make the domain partitioning and error estimation more robust. They mentioned creating a transfer function based on flow properties from LiveOcean instead of a nearest-neighbor algorithm for assigning properties of casts to each gridcell. They also recommended using LiveOcean to understand covariance to better estimate error. They also recommended using something like orthogonal analysis to inform the “best” sampling locations, which is potentially useful for future field work. Admittedly a lot of the stats are above my head at this point but John Wilkin was excited about me potentially “creating my own AI” to take observational cast data and extend it to a 3D domain.
2. Folks were interested in the method application to their respective estuaries, in particular Geno Palwak and his student Addie Adelson. Additionally, students from the University of Maine were interested in applying it to Patagonian estuaries. Since my error estimation is so closely tied to having a well-performing mechanicsting model like LiveOcean, it may be of limited use, but I made the connections anyway!
3. Mercedes Pozo Buil (UCLA) recommended some further data sources like World Atlas, Argo, and Esper(?), noting that they may not be high enough resolution for the Salish Sea domain.
4. Jim Thomson was interested in bias due to tidal aliasing. He recommended that in areas with high tidal energy I should look at the corresponding tide and evaluate if that changes estimates I get. In particular, I mentioned that I’m using monthly bins, but the errors are estimated using a single time history in LO (which almost certainly is at a different tidal phase than all the observational data). If nothing else, it’s uncertainty to keep in mind! Jim also recommended I look at Ecology’s mooring data for higher time resolution to inform the uncertainty due to tides in this estimation method.
5. Sam Kastner seemed excited about the work and recommended I check into UW’s Stats department’s “consulting” program for some of the advanced stats I might need to do for error estimation - which sounds great.
6. Jody Klymak gave me context on some of the sampling in Strait of Georgia and also recommended I check out Soetaert et al. (2022) for Saanich Inlet information.
7. People were generally really interested to talk about the correlation of trends with other forcing…and I was unfortunately unable to give them that analysis. I’m excited about that next step!
8. Finally, the WWU faculty (Sam and Erica) were excited to chat more about potential Penn Cove fieldwork collaborations. So that’s exciting!

I have so many more questions and thoughts from the conference, but a few that stand out are:
1. How do the upwelling processes in Strait of Georgia affect what I'm seeing? Is this an seen in Puget Sound? (From Susan's talk.)
2. What novel remote sensing techniques could be useful? (From Jessica Garwood's talk - I'm not necessarily jazzed about using animals but cormorants do hang out in the domain...)
3. Effects of internal waves on Salish Sea physics? (Generally something I know is a factor but don't fully understand.)



data from 2008-2017 (mainly obs, with some LO history and LO casts). More on this in the poster review.

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
