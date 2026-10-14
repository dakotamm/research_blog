# More particle tracking, retention mechanisms, and bonus TEF/Eulerian decompositions in Penn Cove

## Particle tracking for source water

I've started some more particle tracking runs based on some reading by Brasseale and MacCready [(2021)](http://doi.org/10.1175/JPO-D-20-0080.1) to understand source waters. I seed particles in the head of Saratoga Passage at a spacing of every other gridcell horizontally and every 4m for depth. I released particles to mirror the retention time tracking from last week. I am only showing August 2025 here since the whole year is still running. This plot is an example mid-August released divided based on entry depth into Penn Cove and colored based on the DO concentration along that track.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/e708c668-9321-4538-8460-14b4b9f954f9" width="800"/><br>Fig 1. Saratoga head particle release example on flood 2025/08/15; divided by entry depth and colored by DO concentration.</p><br>

Surface-entry particles largely enter from the north; deep entry is largely from the south! Not many particles entering at depth start hypoxic; those that do have likely already been in Penn Cove! I will have that test done shortly.

## Retention mechanisms: eddies vs. slow velocities

After chatting with Alex last week, I investigated the two "slowing" mechanisms possible in Penn Cove for the spaghetti plot examples I showed last week. To investigate slow velocities as a trapping mechanism, I used the bottom tidal excursion in both an Eulerian and particle tracking sense to plot these maps and compare them to distance to the mouth:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/aee21ed5-b91f-4423-8436-0c946363daaa" width="800"/><br>Fig 2. Penn Cove Eulerian tidal excursion at bottom during specific releases.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/00d074c0-e1c3-46b0-9f6f-45610ed41f8f" width="800"/><br>Fig 3. Penn Cove particle tidal excursion at bottom during specific releases.</p><br>

Note that the tidal excursion does vary a lot around the July 17 release (this was selected since it had minimal diurnal inequality in the tides)!

To investigate eddy mechanisms, I moved away from the Okubo-Weiss mechansism because the currents are just so slow and the domain is small! However, I did try to get an estimate of residence for particles that headed one direction for a full rotation averaged tidally during their residence time vs. those that didn't! This is a course pass, but a start.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/44b99355-2aea-4251-9644-deb0c7b6ff79" width="800"/><br>Fig 4. Penn Cove particle looping vs. non-looping averaged over tidal cycles; distance from mouth overtime.</p><br>

Ultimately it seems that slow velocity is more correlated with enhanced residence time than eddies. I still need to link these both to DO more formally.

## TEF vs. Eulerian decompositions and residence time estimates

This week, I've been settling into the nuts of bolts of analyzing Penn Cove circulation, flushing, and transport to understand hypoxia. A lingering item from a few weeks ago was to go back through the TEF and Eulerian decompositions for Penn Cove mouth circulation, both for my own understanding and to ensure that we are using all the tools available to understand circulation. Going back through MacCready [(2011)](http://doi.org/10.1175/2011JPO4517.1), I have been able to use hourly model snapshots to calculate the terms in the following decompositions. For brevity in typing, I'll just go to the paper if we want to look at the math!

For the Eulerian decomposition, the salt flux can be broken down into three components: the tidally- and spatially-averaged component (F_R, or the river flow component), the tidally-averaged but spatially-varying component (F_E, or the exchange flow), and the tidally- and spatially-varying component (F_T, or the tidal pumping component). Here is a plot of how these terms work together using my Penn Cove section at Long Point:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/1ceed677-0338-4438-a296-e95a98022984" width="600"/><br>Fig 1. Eulerian decomposition for Penn Cove model salt flux time series at Long Point section.</p><br>

We know that the issue with this decomposition is that the F_T component is not known a priori. TEF circumvents this by considering a decomposition of the salt flux here using salinity coordinates. If we compare the tidally-averaged distribution of salt flux through the water column between the tidally-averaged component of the Eulerian decomposition and TEF, we get the following:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/418548eb-c2b9-4758-ad48-96646af53b05" width="600"/><br>Fig 2. TEF vs. tidally-averaged Eulerian decomposition for Penn Cove model salt flux at Long Point section.</p><br>

If we compare the tidally-averaged Eulerian salt flux and volume flux we get:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/8e8d4da1-d4e3-4604-8929-c79956ddac09" width="600"/><br>Fig 3. TEF vs. tidally-averaged Eulerian decomposition for Penn Cove model salt and volume flux time series at Long Point section.</p><br>

Now I've considered a cumulative salt integrated flux using hourly average model output:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/8e8d4da1-d4e3-4604-8929-c79956ddac09" width="600"/><br>Fig 4. TEF vs. full Eulerian decomposition vs. tidally-averaged Eulerian decomposition for Penn Cove model integrated salt flux cumulative time series at Long Point section.</p><br>

I think I've done the math right (which was half the battle here) and I think I have an understanding of the different components of this flow over the course of the model run. Here are some initial takeaways:
* F_E brings salt into the cove; F_T exports it
* TEF components account for this tidal pumping more than the tidally-averaged Eulerian decomposition; again this speaks to the importance of F_T since this is not included in the tidally-averaged Eulerian decomposition
* To further this point further, F_T is required to balance a salt budget.

Calculating a residence time per this paper, using the average salinity vs. the inflowing salinity, gives a median residence time of all model hours of 6.4 and 5.9 days for TEF and the tidally-averaged Eulerian decomposition. These assume that the water is well-mixed in Penn Cove and that entering water is new! This is about twice the length of our ~3 day average e-folding scale of particles.

What interpretation am I missing here? I have done the math right but am likely missing nuance that I need to account for.


