# Eddies and tidal circulation in Penn Cove

## Do eddies trap water in the Cove?

We've been discussing two possible mechanism for retaining water in Penn Cove: slow velocities and persistent eddy trapping.

I used Okubo-Weiss to detect eddy presence from Eulerian residuals (Godin-filtered hourly snapshots of velocity). After reviewing quite a bit of literature, I believe that the simple Okubo-Weiss parameter (comparing deformation vs. rotation at all points in the domain using velocity) is the best way to assess for rotating points in this small-scale environment. I used thresholds that enable me to detect eddies with a radius of 400m or greater given grid resolution. This gave me an idea of where particles might circle an eddy, and also allowed me to track where eddy centers might move seasonally. I did this for different depths: 0-4m, 4-10m, and 10m-bottom.

I found some interesting things with this analysis. Effectively, eddies are modulated BY flushing (or they spin-up and are more detectable when velocities are higher). This is a schematic that I asked Claude to help me make given all the different metrics I was trying to assess:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/2092d976-0dd6-4540-98f0-381120995329" width="800"/><br>Fig 1. Eddy modulation schematic.</p><br>

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
