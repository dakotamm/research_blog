# Penn Cove Renewal and Hypoxia Paper Plan IN PROGRESS

*Please note - this planning document is in progress.*

## Background

We know from Aurora's paper that the most significant differentiators of hypoxic vs. oxygenated terminal inlets are the concentration of inflowing DO and the flushing time of inlets. Penn Cove DO follows a similar seasonal cycle as outside in Saratoga Passage; however, hypoxic events in the model only occur in Penn Cove and exhibit some episodic modulation that appears local to Penn Cove. We hypothesize that physical environmental factors like freshwater flow and wind drive changes in DO flux and retention time and lead to hypoxia in Penn Cove.

## Goals

Using our high resolution numerical model of Penn Cove, our goals are as follows:
* Understand the effects of physical processes, such as transport/renewal in Penn Cove, on hypoxia

To do this, we need to understand:
* How is volume transported in Penn Cove?
  * What does the subtidal + tidal residual flow look like across cross-sections of Penn Cove? In a depth-averaged sense?
* What modulates volume transport?
  * Seasonal modulation - tied to freshwater/wind?
  * Tidal modulation - tied to spring/neap cycling?
* How does residence time vary spatially in Penn Cove? How is this modulated?
  * Are there stagnant locations in Penn Cove that may lead to growing hypoxia?
  * How does this vary seasonally? Tidally?
* What physical processes/modulation are most linked to DO minima and hypoxia in Penn Cove?
  * Is DO most sensitive to inflowing DO concentration? If so, what modulates episodic low DO events?
  * Is DO more sensitive to slower flushing?
  * How do all of these stack up against the background "biology" seasonal signal of low DO?
 
## How do we do this?

### Possible Tools

When we discuss residence time and flushing in Penn Cove, three tools are considered:
* Lagrangian particle tracking
* Dye release of passive tracer
* TEF

For reference, here are the three sections that I will reference throughout Penn Cove.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/32971bb2-cfb1-4b9d-b157-6e05a165351a" width="800"/><br>Fig 1. Penn Cove TEF sections.</p><br>

#### Assessing DO transport variation

While TEF is of course a gold standard in discussing estuarine exchange flow, the preliminary concern with using TEF is that it will underestimate flux in highly tidally dominated fields where not a lot of modification takes place given the lack of freshwater input in the model (i.e., the frozen field issue). To illustrate this quickly, I calculated the subtidal Qin and Qout across pc_lp with TEF, TEF using DO coordinates (a topic of discussion perhaps), and then the hourly average Qin from model output directly. Here we can see that TEF is similar using both coordinate systems but fails to match the modeled Qin and Qout.


<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/60c01d35-e52e-46fd-8032-18d04a8995ea" width="800"/><br>Fig 2. Modeled Qin/Qout/Qnet calculated using just model output, TEF, and TEF with DO coordinates through PC's Long Point section for the full model run (2024-2025).</p><br>

To assess the pathways volume and DO transport, I have tried to get an average sense of the subtidal and tidally-varying flow fields in Penn Cove using just model output. To do so simply, I used the hourly average flow rate and oxygen and created depth-averaged and sectional DO transport maps for several sections. This is for the mouth of Penn Cove during the full year and for the Low-DO season.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/71d2f448-83af-4078-af22-18ff3454616f" width="800"/><br>Fig 3. Modeled subtidal, Eulerian (advective), and tidal pumping components of DO flux through PC's Long Point section for the full model run (2024-2025).</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/717c2bec-3f9a-4749-9a8e-a308a9379702" width="800"/><br>Fig 4. Modeled subtidal, Eulerian (advective), and tidal pumping components of DO flux through PC's Long Point section for the full model run Low-DO seasons (Aug-Nov, 2024-2025).</p><br>

Taking this simple calculation at face-value, we see the dominant exchange is the "exchange flow" as compared to "tidal pumping". The shape of this exchange is very familiar given our previous work with average velocity fields. However, the next DO transport is much smaller than total DO flux, suggesting significant tidal reversal. We note that Penn Cove is a net exporter of DO in this view, but that tidal pumping opposes the tidally-averaged exchange flow by acting as a net importer of DO.

Using a simple budget again that uses just model output, I have a flux decomposition using this same method for the whole water column and also the bottom 1/3 of sigma layers.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/906bec6e-e1f9-4949-bedd-06c0e9fc753a" width="800"/><br>Fig 5. Modeled subtidal, Eulerian (advective), and tidal pumping components of DO flux through PC sections for the full model (2024-2025).</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/637432e6-daee-45fb-b049-461f6b48bf68" width="800"/><br>Fig 6. Modeled subtidal, Eulerian (advective), and tidal pumping components of DO flux through PC sections for the full model and bottom 1/3 of the water column(2024-2025).</p><br>



**Plan:** Use Eulerian decomposition for assessment of DO flux variation. Correlate to changes in freshwater/wind.

#### Assessing residence time variation

Method 1: Particle tracking released during selected seasons/tide phases
* As I did in my PECS presentation, select several comparable release times and track for several tidal cycles.
* Release Times:
  * Monthly spring and neap tides, release at "start" of spring and neap cycle, match tidal release (e.g. at high tide)
* Release Extent Options:
  * Entire Skagit Basin region (including Penn Cove) - Poincare maps (like Banas et al., 2005)
  * Just Penn Cove
  * Specific depth/region (backbay at the bottom)

Here are example releases from my PECS presentation including release location (bottom half of water column) and particle retention for matched spring/neap and seasonal variation.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0a483848-20df-400a-8308-1c028a3d5e47" width="800"/><br>Fig 7. Penn Cove particle release location.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/92269ba5-568c-49bf-ab31-4001def33214" width="800"/><br>Fig 8. Penn Cove particle retention time for spring/neap and seasonal variation.</p><br>


Method 2: Age tracer (like Banas et al., 2006)
* Using non-conservative tracer initially set to 0 but allowed to grow at constant rate within only Penn Cove; provides age estimate at equilibrium using concentration at each grid cell
* Requires rerunning the model!<img width="2200" height="1800" alt="20260921_pc_sections_map_wb1_pc1" src="https://github.com/user-attachments/assets/32971bb2-cfb1-4b9d-b157-6e05a165351a" />


**Plan:** Both methods provide spatial + temporally varying information about residence time. Ultimately I will correlate these two method results to environmental factors such as freshwater/wind.
