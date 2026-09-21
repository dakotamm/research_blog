# Penn Cove Renewal and Hypoxia Paper Plan

## Background

We know from Aurora's paper that the most significant differentiators of hypoxic vs. oxygenated terminal inlets are the concentration of inflowing DO and the flushing time of inlets. Penn Cove DO follows a similar seasonal cycle as outside in Saratoga Passage; however, hypoxic events in the model only occur in Penn Cove and exhibit some episodic modulation that appears local to Penn Cove.

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

### Volume/DO Transport - Preliminary Assessment + Possible Methods

To assess volume and DO transport, first I have tried to get an average sense of the subtidal and tidally-varying flow fields in Penn Cove. To do so simply, I used the hourly average flow rate and oxygen and created depth-averaged and sectional DO transport maps for several sections. This is for the mouth of Penn Cove during the full year and for the Low-DO season.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/71d2f448-83af-4078-af22-18ff3454616f" width="800"/><br>Fig 1. Modeled subtidal, Eulerian (advective), and tidal pumping components of DO flux through PC's Long Point section for the full model run (2024-2025).</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/717c2bec-3f9a-4749-9a8e-a308a9379702" width="800"/><br>Fig 2. Modeled subtidal, Eulerian (advective), and tidal pumping components of DO flux through PC's Long Point section for the full model run Low-DO seasons (Aug-Nov, 2024-2025).</p><br>







Important takeaways here:
* xn11abbur00 matches observations better than xn11b - though there is still bias
* t1_xn11abbur00 quickly converges with t0_xn11abbur00 at the beginning of 2025, suggesting that the results are not very sensitivie to the burial in the initial condition
* All the models follow similar general patterns but are biased high.
* The models do not capture the timing of DO minima in observations.

For completeness, here are the two xn11abbur00 models' lowpass-filtered time series within all of Penn Cove (minimum and mean bottom DO) and hypoxic days/extent.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/bcc8196f-f49d-4bcc-b2f3-16360f38b054" width="800"/><br>Fig 2. Two models Penn Cove minimum and average bottom DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/afcd144f-298a-4397-add4-4ec0b6568210" width="800"/><br>Fig 3. Two models Penn Cove hypoxic extent.</p><br>

These models seem to predict a LOT of hypoxia - just not necessarily at the bottom or where KC's records capture it.

Finally, I took a look at our recent acquisition of field data in December 2025. I compare it to wb1_t0_xn11abbur00. I'm showing some TS diagrams, property-property plots, and then selected sectional comparisons for temperature, salinity, DO, and velocity. I have every lap-components section comparisons if need be, but am showing just a few examples.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6fc4182b-eaac-47a0-a136-14c1ba684a6e" width="800"/><br>Fig 4. TS plots for wb1_t0_xn11abbur00 vs. December 2025 recon observations.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a030db0a-ad27-468d-9146-96896b9cc372" width="800"/><br>Fig 5. Property-property plots for wb1_t0_xn11abbur00 vs. December 2025 recon observations.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0143cac2-18e3-4420-8663-6a35c89a9cbb" width="800"/><br>Fig 6. Velocity at entrance section (eastward +) for wb1_t0_xn11abbur00 vs. December 2025 recon observations.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f786aa1d-ae05-4d37-a868-8acf156c0bf4" width="800"/><br>Fig 7. Temperature at entrance for wb1_t0_xn11abbur00 vs. December 2025 recon observations.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/2e7bb820-fca8-42a6-9fcc-79740d945cd7" width="800"/><br>Fig 8. Salinity at entrance for wb1_t0_xn11abbur00 vs. December 2025 recon observations.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/883b8068-007c-447f-b044-aa244bbf3fac" width="800"/><br>Fig 9. DO at entrance for wb1_t0_xn11abbur00 vs. December 2025 recon observations.</p><br>

A few takeaways:
* DO minima are not captured by the model
* Speed maxima are not captured by the model
* Freshwater layer is less pronounced in the model
* Model bottom water is much cooler than observed.

With all this - is this model fit for purpose? Let's discuss!
