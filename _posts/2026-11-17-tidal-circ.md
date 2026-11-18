# Describing tidal and residual circulation in Penn Cove

...is not easy, so it seems. I am hoping that y'all can help me focus on what's important for my Chapter/Paper 2.

The main dependent variable we care about is DO, but having some description of at least the kinematics of tidal circulation seems like an important step.

I have tried very many ways to get a descriptive model of tidal circulation; unfortunately, the more I try to simplify, the more complicated it becomes! So here's some of my understanding so far...

## What does the velocity look like in Penn Cove?

I have taken a look at this in a few ways. One way has been to look at all floods and ebbs and average them, or lesser/greater floods/ebbs. In general I am taking a Godin-filtered hourly velocity and then averaging that over each time period. In this case, I have all the PEAK flood and ebb hours averaged over the course of 2024, then the average Godin-filtered residual.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/09be122c-c3c2-46ab-bd5a-a4605dafb0e7" width="800"/><br>Fig 1. Map of averaged PEAK flood and ebb hours + Godin-filtered hourly residual over 2024 for surface 1/3, bottom 1/3, and depth-averaged velocities.</p><br>

Conversely, I can represent an identical view for a specific lunar day that represents an "average" tide in terms of spring/neap, tropic/equatorial, stratification, and wind stress at the surface. Selecting these days has required hypothesizing which variables are the most important drivers of tidal variation (these four for now), making time series of these variables, ranking each day on the time series, and the selecting the day closest to average on all these axes. The same plot of ONE "average" lunar day (2024.08.31-2024.09.01) is as follows:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f99c5f8e-3c46-45c3-b61b-83b0f7d87046" width="800"/><br>Fig 2. Map of baseline day PEAK flood and ebb hours + Godin-filtered hourly residual for surface 1/3, bottom 1/3, and depth-averaged velocities.</p><br>

Similarly, I can look at the cross-sections anywhere, but here we look at the Lovejoy line I've defined.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0c69aa0d-9838-4b23-998a-2480e4f5c038" width="800"/><br>Fig 3. Section at Lovejoy of average PEAK flood and ebb hours + Godin-filtered hourly residual over 2024.</p><br>

And now the baseline day!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/bab3893b-1776-401d-b1a3-c3e02b88fbec" width="800"/><br>Fig 4. Section at Lovejoy of baseline day PEAK flood and ebb hours + Godin-filtered hourly residual.</p><br>


## Tidal ellipses?

*insert tidal ellipses*


## What does tidal velocity look like at Lovejoy?
- profile and cross-section
- greater/lesser ebb?
- standard "day"
- 

## What modifies tidal velocity?

### Tidal Umax? Top/bottom flood/ebb speed/direction?

### Shape of profiles?



## What's up with that eddy? residual but...
- driven primarily by the tidal velocity!

















## Do eddies trap water in the Cove?

We've been discussing two possible mechanism for retaining water in Penn Cove: slow velocities and persistent eddy trapping.

I used Okubo-Weiss to detect eddy presence from Eulerian residuals (Godin-filtered hourly snapshots of velocity). After reviewing quite a bit of literature, I believe that the simple Okubo-Weiss parameter (comparing deformation vs. rotation at all points in the domain using velocity) is the best way to assess for rotating points in this small-scale environment. I used thresholds that enable me to detect eddies with a radius of 400m or greater given grid resolution. This gave me an idea of where particles might circle an eddy, and also allowed me to track where eddy centers might move seasonally. I did this for different depths: 0-4m, 4-10m, and 10m-bottom.

I found some interesting things with this analysis. Effectively, eddies are modulated BY flushing (or they spin-up and are more detectable when velocities are higher). This is a schematic that I asked Claude to help me make given all the different metrics I was trying to assess:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/8392231f-1dda-4db7-b7be-2ecb596cdc5f" width="800"/><br>Fig 1. Eddy modulation schematic.</p><br>

I did use particles released in the model domain to see if particles actually circle the eddy and thus are retained longer. Each particle needed to start in the back bay (behind Coupeville); if a particle loops around the eddy center (defined above) it is defined as having looped the eddy! This is based on the trajectory of motion between hourly snapshots of the model. The results of this test are tricky and so I am still going through this/unclear if this aides the story, but ultimately the findings are the same as the Okubo-Weiss findings using Eulerian residuals.

I think the takeaway here is that the eddy retention mechanism is not independent of velocity. There is a persistent rotation in the back bay that has some depth variation. Eddies are detected and present when there is more flow and Eulerian residence time is low! Therefore, eddies do not appear to be an effective trapping mechanism and are more a product of the geometry in the Cove.

**Pervasive question for me:** What, then, causes the eddy? Just flow separation at Coupeville?

## How does the tide work at Penn Cove?

I got into this in more depth while trying to figure out why the eddy exists like it does. I did a lot of tidal ellipses (which largely show that the tide just goes in and out!). But then I got into some interesting stuff regarding the structure of the tides throughout tidal cycles.

We know that the tidally-averaged flow is almost entirely laterally-separated. However, there is definitely two-layer flow during the tidal cycle which may/do enhance the tidal excursion of particles beyond just a simple tidal prism. I made some animations of this if we want to check it out. But also, we hypothesize that there is differences in bottom water retention; perhaps this is modulated tidally. I wanted to look at this in more depth, so I made some simple cross-section schematics for tidal cycles at the mouth of Penn Cove. I am out of time to narrate this so let's look together!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/334e7c0c-f9b3-4bea-8b08-c33eb8387937" width="800"/><br>Fig 2. Typical layered flow across Penn Cove mouth during tidal cycle.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6f0dcb10-ad5e-4e36-9bc0-1251351d2083" width="800"/><br>Fig 3. Typical layered flow across Penn Cove mouth during spring/neap tidal cycle.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/943e9d8f-da8c-4ffd-b7be-0b4da3d4fa47" width="800"/><br>Fig 4. Typical layered flow across Penn Cove mouth during tropic/equatorial tidal cycle.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/e6424152-d579-4675-9d7a-72cacaafc836" width="800"/><br>Fig 5. Typical layered flow across Penn Cove mouth during high/low stratification tidal cycle.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/7b6cb51e-e5ba-48b6-8f5a-c83c817eda75" width="800"/><br>Fig 6. Typical layered flow across Penn Cove mouth during into/out of cove wind tidal cycle.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/bcd5508c-d54a-4aed-abf8-fa89f2b38dab" width="800"/><br>Fig 7. Typical layered tidal excursion during different events.</p><br>
