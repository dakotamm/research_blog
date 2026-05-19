# Okubo-Weiss and Vorticity Changes Around Hypoxic Events in Penn Cove.

I took some time to use my Okubo-Weiss eddy detection methods to see what's happening around hypoxic events modeled in Fall 2017 in wb1_r0_x11b model.

<img width="1621" height="1510" alt="_timeseries_combined" src="https://github.com/user-attachments/assets/dfc08a1d-f3f9-4214-86b5-b8bedddc7e7c" />
<img width="1444" height="1282" alt="_analysis_stacked_DO_vort_layers" src="https://github.com/user-attachments/assets/1977685a-6f68-43bd-8a21-8b7480345460" />



https://github.com/user-attachments/assets/bfb04edf-cd3e-4d7d-9392-5a9dcadb76a9


We have formed some hypotheses over the last few months that in Penn Cove, hypoxia may be driven by changes in residence time over time. We see a strong seasonal signal in DO and also strong tidal fluctuation in flow. So I developed some tools to look at model output as averaged over seasons and also different tidal phases. We've already seen this in part focusing on specific tidal phases when we hypothesized that the formation/persistence of two distinct flow cells and how they may move and interact may cause increased residenct time at the head of Penn Cove. This makes use of my older wb1_r0_xn11b model (that actually simulates hypoxia and matches observations). Tidal phase is calculated with UTide at an extraction point in the middle of Penn Cove using SSH. Please squint at these plots with me:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/50cc06d4-9474-4423-9786-6afb70a8d550" width="800"/><br>Fig 1. 2017 modeled seasonal/tidal/depth-averaged velocity fields for Penn Cove.</p><br>

What would make my job really easy here is if something about Penn Cove in September/October (our most likely hypoxia season) was drastically different than the other seasons. And what we do see if that the spring flood has reduced velocity during this time. However the biggest changes seasonally appears to happen during November/December. This supports the hypothesis that hypoxia is really a race against time - as soon as the flow patterns coincident with winter begin to occur, DO increases. The most severe months just happen to be severe because they are the latest months before more mixing occurs...

Another analysis idea I've followed, mainly to understand these tools, is eddy detection. We have hypothesized that the interior region of Penn Cove disconnects from the exterior circulation, and potentially may trap water in a slowly rotating flow that remains in the head. This is very preliminary, but uses the [Okubo-Weiss](https://doi.org/10.1016/j.dsr2.2004.09.013) criteria. In theory, it detects eddies that are at minimum ~500m in diameter and persist for at least 10 hours... I developed these tools from the baseline of [SWIRL](https://github.com/jcanivete/swirl) eddy detection code, but ultimately have been using the slightly less tuned Okubo-Weiss parameter. Of course I had assistance from Claude too! But here are some preliminary eddy track results:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/47dc6797-3e01-4cbe-b1ae-d05fdccc5aa0" width="800"/><br>Fig 2. 2017 modeled seasonal/tidal/depth-averaged eddy tracking for Penn Cove.</p><br>

So...there's a lot going on, but I think we can generally surmise that there are two zones as we expect, and also that most of the tracks are counterclockwise (blue). There looks like there might be less eddy activity during September/October, which is then disrupted in November/December. But what does this say about residence time and hypoxia?

As I seek to quantify residence time more, here's some other plans that I've identified with some literature review:
* Lagrangian particle tracking (e.g., [Defne and Ganju, 2014](https://doi.org/10.1007/s12237-014-9885-3))
  * What is the average "exit" time of a number of particles?
  * Jilian and Erin have done this in post-processing with LO!
* Box models with TEF and Eulerian passive tracers (e.g., [MacCready et al., 2021](https://doi.org/10.1029/2020JC016738))
  * Requires drawing boundaries a priori for quantification of residence time in different zones
  * I think - requies another model run (dye release)...

I'm still wrapping my head around this... Stay tuned!
