# Quals Recovery and Moving Forward

### Goals From Last Meeting:
1. Quals!
2. Cleaning/improving VFC codebase as time allows - work with Parker on improving code efficiency.
3. After quals - slight direction shift to start working with real observational data vs. strict error quantification.

### Completed Goals:
1. Quals!

---

## Quals Reflection

Last week, I took the CEE - Hydrology and Hydrodynamics PhD Qualifying Exam - and passed! It was a challenging, time-consuming, but rewarding experience. It was an opportunity to really drill down on concepts that I've previously learned throughout the coursework so far, from fundamentals to our new estuarine physics class last quarter. The questions served to push me beyond my comfort zone and allowed me to think outside the box. We ensured that I have a good grasp of using our friend the Navier-Stokes, talked about modeling uncertainty, and discussed big picture project goals. Overall, I'm happy I did it and glad it's behind me!

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/235755691-2b6167f4-5d0e-4567-aeb3-44611841ca6c.jpg" width="300"/><br>Fig 1. Unnecessary meme.</p><br>

A few general takeaways to come out of my exam:
* I'm feeling confident about my technical writing; when I get to publications, this confidence will be very helpful!
* I'm gaining confidence at discussing tricky concepts "on the chalkboard," which is helpful for teaching and general public speaking confidence.
* I've accumulated very useful literature and am gaining familiarity with the major players in this field (mainly Parker!).
* We discussed the potential of creating a field work proposal for Penn Cove, given the lack of physical and biogeochemical observational data in this area.

Some specific points of critique:
* I have been frequently using language indicative of a **proven** downward trend in DO concentration in Puget Sound in recent decades and that hypoxia is a common issue in shallow embayments like Penn Cove. I agree that this requires a lot more information before I make suchs claims. Parker's words of wisdom toward skepticism in all things in academia (and life?): "Is it true? How do you know?" As I continue to discuss and write about these concepts, I will certainly revise language to be reflective of what I myself understand enough to claim. Generally: **be wary the hype!**
* My knowledge of biogeochemical processes affecting dissolved oxygen is fairly surface-level. I intend to take (or audit) Mike's Applied Limnology (CEE 462) class in the fall to bolster that knowledge.

Overall, a relief to have that checkpoint done, and in a way that I feel pretty proud of!

---

## VFC Progress and Plan

Given the time spent on preparation and taking quals, I have not made huge progress on research. From our last meeting, we set my directive toward starting to plunge into observational data, instead of spending more time trying to minutely quantify VFC errors using solely LO casts. I want to note for posterity that there are a few kinds of error that I'm discussing:

1. **Sampling Error** - given a fraction of sampled points in the domain, how closely can we approximate the domain?
  * This is what I've been doing with using the VFC method within the LO domain. Since we can only have full domain knowledge about a model, this is the only way to approach this question.
  * Eventually, however, the domain is "real-life," and estimates made using the LO domain will inform the confidence we have in our VFC methods using real observational data.
  * This could be captured taking "n" points out of the domain in LO and varying "n" until the VFC method and LO output converge. However, this simple implementation doesn't represent the spatial biases represented in real-life sampling (i.e., general undersampling of shallow areas).
2. **Modeling Error** - given observational data CTD/bottle casts and model CTD/bottle casts/full domain output, how closely does the model reproduce real-life?

Both are important, but neither have meaning unless I actually start working with observational data. So onwards! The next order of business is what we've termed the "money-plot;" a time-series of hypoxic volume in the Salish Sea over as long as we have record, and compared to the LO output at available times.

Since quals finished Friday, I've been reconnecting to research and figuring out how to use observational data for the VFC method. Stay tuned throughout the week for more.

Next steps are as follows:
1. Start using observational data in VFC method (likely using DFO in specific domains again).
2. Continue to build robust VFC toolbox - ESPECIALLY code efficiency.
3. Continue thought on error evaluation, but on the backburner for now.
4. Working towards Gordon Conference poster plots/figures.

---

## Bookkeeping 
* WWU Lecture - scheduled for Thursday, 5/4/2023
* KC Spring Update - scheduled Friday, 5/26/2023
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods - need lit. review.
2. Figure out comments section on blog!!!
3. Organize literature - Endnote?

### Looking Ahead:
1. Plugging back into research, start using observational data in VFC method!
2. Meet with Parker if available this week for code efficiency review.

### Goals For This Week:
1. 
