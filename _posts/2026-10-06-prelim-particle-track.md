# Preliminary findings from Penn Cove particle tracking experiments

**Paper 2 Science Questions:** What is the circulation in Penn Cove? How does this vary spatially and temporally? How does residence time and flushing variation modulate hypoxia in Penn Cove?

**Methods:** Release neutrally-buoyant particles throughout 2025 model year and model residence time and flushing using e-folding of particle retention in Penn Cove. Compare to dye-release and TEF.

**Hypotheses:** Preliminary particle tracking indicates that residence time modulates seasonally and subtidally, concurrent with the scales of modulation of hypoxia. From model observations, we think that residence time scales with stratification and wind, both of which vary seasonally. There is some evidence to suggest that spring-neap modulation may influence residence time and episodic hypoxia.

**This last week:** I simulated particle release seeded according to Figure 1. Particles are spaced approximately 2m apart and are tracked for 14 days using hourly time steps during 2025. I started particle releases during each major flood and ebb in a lunar day, then subsampled this to every 3 days for simulation efficiency. ~220 particle releases for 14 days took only ~20 hours to run, so I can make modifications to this set up. I am currently in the process of going through this output, but have some fun plots to share!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/2dbc331a-15cc-446b-95cb-1c38dd000b1d" width="800"/><br>Fig 1. Penn Cove particle release locations. Areas are considered in post-processing.</p><br>

First, let's look at some spaghetti plots. I made animations of two different releases close to the median "particle retention curve" - in this case, these are the major ebb and flood of July 10, 2025.



https://github.com/user-attachments/assets/94254da1-df14-47ec-95f6-9d392b9dff08




w/o WWTP + thinking no wind for a month or something

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
  * Entire Skagit Basin region (including Penn Cove) - Poincare maps (like [Banas et al., 2005](https://doi.org/10.1029/2005JC002950))
  * Just Penn Cove
  * Specific depth/region (backbay at the bottom)

Here are example releases from my PECS presentation including release location (bottom half of water column) and particle retention for matched spring/neap and seasonal variation.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0a483848-20df-400a-8308-1c028a3d5e47" width="800"/><br>Fig 7. Penn Cove particle release location.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/92269ba5-568c-49bf-ab31-4001def33214" width="800"/><br>Fig 8. Penn Cove particle retention time for spring/neap and seasonal variation.</p><br>


Method 2: Age tracer (like [Banas et al., 2005](https://doi.org/10.1029/2005JC002950))
* Using non-conservative tracer initially set to 0 but allowed to grow at constant rate within only Penn Cove; provides age estimate at equilibrium using concentration at each grid cell
* Requires rerunning the model!


**Plan:** Both methods provide spatial + temporally varying information about residence time. Ultimately I will correlate these two method results to environmental factors such as freshwater/wind.
