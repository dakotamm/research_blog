# Preliminary findings from Penn Cove particle tracking experiments

**Paper 2 Science Questions:** What is the circulation in Penn Cove? How does this vary spatially and temporally? How does residence time and flushing variation modulate hypoxia in Penn Cove? *More later:* How does DO transport into and out of the Cove modify hypoxia and how is this modulated?

**Current Methods:** Release neutrally-buoyant particles throughout 2025 model year and model residence time and flushing using e-folding of particle retention in Penn Cove. Compare to dye-release and TEF.

**Hypotheses:** Preliminary particle tracking indicates that residence time modulates seasonally and subtidally, concurrent with the scales of modulation of hypoxia. From model observations, we think that residence time scales with stratification and wind, both of which vary seasonally. There is some evidence to suggest that spring-neap modulation may influence residence time and episodic hypoxia.

**This last week:** I simulated particle release seeded according to Figure 1. Particles are spaced approximately 2m apart and are tracked for 14 days using hourly time steps during 2025. I started particle releases during each major flood and ebb in a lunar day, then subsampled this to every 3 days for simulation efficiency. ~220 particle releases for 14 days took only ~20 hours to run, so I can make modifications to this set up. I am currently in the process of going through this output, but have some fun plots to share!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/2dbc331a-15cc-446b-95cb-1c38dd000b1d" width="600"/><br>Fig 1. Penn Cove particle release locations. Areas are considered in post-processing.</p><br>

I got these bulk retention curves for all of the particles released in Penn Cove. The variability is shown.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/8347f770-d205-4b01-a17b-2a7c91a2b9a2" width="800"/><br>Fig 2. Penn Cove bulk retention curves.</p><br>

We care about this because we think DO varies with retention time. And we see this in retention curves if we color by DO at the end of the release period.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a846d730-5dd4-4169-b2c9-3d04a2af2b57" width="800"/><br>Fig 3. Penn Cove bulk retention curves colored by DO at end of period.</p><br>

To dig in, let's look at some spaghetti plots (yum). I made animations of two different releases close to the median particle retention curve - in this case, these are the major ebb and flood of July 10, 2025.

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/dcfc5afa-3c68-44e4-a94f-70d2d9c68776" controls="controls" style="max-width: 800px;"></video><br>Fig 4. Median retention time EBB release on July 10, 2025; trajectories shown for one lunar day. Particles initial positions are broken into quadrants and top and bottom half of the water column.</p><br>

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/e405e9af-6f7f-4bff-9a47-ac423a4914bf" controls="controls" style="max-width: 800px;"></video><br>Fig 5. Median retention time FLOOD release on July 10, 2025; trajectories shown for one lunar day. Particles initial positions are broken into quadrants and top and bottom half of the water column.</p><br>

Note that these particles are downsampled (not all are shown). But we see a few things that we have already observed here. First, the surface tends to disperse faster than the bottom layers and ebb and flood have different starting patterns. Second, those particles seeded in the outer-S part of the cove tend to exit fastest and dive south into Saratoga Passage. Finally, we see some evidence of "eddy" behavior in the head of the cove.

In a bulk sense, ebb and flood releases don't have significant differences in retention - which makes sense!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/365773cd-b769-4e71-86af-db7dab362b82" width="800"/><br>Fig 6. Penn Cove bulk retention curves ebb vs. flood.</p><br>

Note this tidal cycle is diurnally-dominated, so I also looked at a lunar day that was more semidiurnal. In this case, let's just look at the flood on July 17, 2017.

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/50b5df72-4fae-40c2-a35c-c99921c110e6" controls="controls" style="max-width: 800px;"></video><br>Fig 7. FLOOD release on July 17, 2025; trajectories shown for one lunar day. Particles initial positions are broken into quadrants and top and bottom half of the water column.</p><br>

Here, we see LESS evidence of gyre activity and less dispersion of particles into Saratoga Passage! The intent was to control for other possible factors like spring/neap variability, stratification, and wind, so ideally this is just contrasting the tidal asymmetry. If we look at bulk retention curves, we see that this dispersion pattern is somewhat reflected.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/64a652d2-ff26-434e-9846-2f17e2bd25ad" width="800"/><br>Fig 8. Penn Cove bulk retention curves diurnal vs. semi-diurnal</p><br>

Both of these runs were in the middle of the spring/neap cycle. I show two floods during similar wind/freshwater conditions and tidal asymmetry, but varying spring/neap. 

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/50b5df72-4fae-40c2-a35c-c99921c110e6" controls="controls" style="max-width: 800px;"></video><br>Fig 9. SPRING flood release on August 21, 2025; trajectories shown for one lunar day. Particles initial positions are broken into quadrants and top and bottom half of the water column.</p><br>

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/50b5df72-4fae-40c2-a35c-c99921c110e6" controls="controls" style="max-width: 800px;"></video><br>Fig 10. NEAP flood release on August 28, 2025; trajectories shown for one lunar day. Particles initial positions are broken into quadrants and top and bottom half of the water column.</p><br>

Looking at the retention curves, interestingly, there is not a lot of difference between these two retention times! This is interesting and contradicts some earlier thoughts (but again this is just bulk curves)l. 

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b30bc85c-3c78-4529-a4f1-275eb206a4e2" width="800"/><br>Fig 11. Penn Cove bulk retention curves spring vs. neap</p><br>

Now let's actually look at some more retention curves. This is the bulk retention curves for all particles in Penn Cove, with seasonal lines shown. The top row is particles allowing return; the bottom is particles that never left. I'm using the same trimesters as Paper 1, but this may need some modification.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/29b62eb2-b1bd-43dc-b5f6-785699508566" width="800"/><br>Fig 12. Bulk retention curves with seasonal breakout.</p><br>

As we've observed, the Low-DO season has the longest retention time. Now let's dig a bit deeper into what could be varying. The biggest two physical components that we've hypothesized are freshwater (stratification) and wind. So let's look at varying stratification retention curves.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/aa99aaf2-57fd-4de2-8d06-4dc0c92969da" width="800"/><br>Fig 13. Bulk retention curves with stratification breakout.</p><br>

Stratification seems to have a big impact! Now looking at along-cove wind varying retention curves.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/01fb341e-b17a-4ffb-9baa-141c5c3fa885" width="800"/><br>Fig 14. Bulk retention curves with along-cove wind breakout.</p><br>

This is interestingly uninteresting! But if we look at seasonal breakouts and wind breakouts...

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6211205a-fcbe-4747-96e7-5c11215fee85" width="800"/><br>Fig 15. Bulk retention curves with along-cove wind AND seasonal breakout.</p><br>

...we see that perhaps within the Low-DO season, wind modulation may play a larger role than over the course of the year!

I have barely scratched the surface here, but I do have lots of plots without a bunch of interpretation yet. Especially interesting may be the spatial (top/bottom, quadrant) breakouts. To preview this, here is the quadrant breakout:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/dda4a2e6-b97c-4abd-9229-9611418dcd3f" width="800"/><br>Fig 16. Retention curves for per-quadrant starting position.</p><br>

Clearly, the inner quadrants have higher retention time and the pattern corroborates our circulation observations (counter-clockwise around Cove).

Looking at surface vs. bottom, however, is somewhat surprising.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/cb455dc3-0a4d-46b2-8706-1ce001ad3940" width="800"/><br>Fig 17. Retention curves for top-bottom starting position.</p><br>

There is surprisingly little difference between surface and bottom retention time in a bulk sense.

**If there is a plot you'd like to see, I probably have it, but had to omit for blogpost length!**

Next steps:
* More digging here. What variation of retention time is the most predictive of DO?
* More particle releases!!! Primarily to understand particle entry into Penn Cove (DO transport into/out of the Cove).
* Wind experiment (perhaps for one month in each season) - how does turning off wind modulate hypoxia?
* Dye release to evaluate particle retention time performance
* Comparison of retention time to TEF flushing time

I would love some feedback on different ways to look at this and/or other things I should be trying!
