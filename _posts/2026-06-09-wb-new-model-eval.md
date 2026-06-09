# Updated Whidbey Basin Nested Models Evaluation

As we try to understand hypoxia mechanisms in Penn Cove, I have run several nested models for at least one year, summarized here:
* wb1_r0_xn11b
  * 2017
  * hourly history files
  * 50% burial in nested model
  * no TRAPS
  * uses cas7_t0_x4b as initial + boundary condition - 0% burial
* wb1_t0_xn11ab
  * 2024-2025
  * hourly history + average files
  * 50% burial in nested model
  * TRAPS included
  * uses cas7_t2_x11b as initial + boundary condition - 50% burial
* wb1_t0_xn11abbur00
  * 2024-2025
  * hourly history + average files
  * 0% burial in nested model
  * TRAPS included
  * uses cas7_t2_x11b as initial + boundary condition - 50% burial
* wb1_t0_xn11abbur00
  * 2025 only - designed to assess the effect of the the IC vs. t0 above
  * hourly history + average files
  * 0% burial in nested model
  * TRAPS included
  * uses cas7_t2_x11b as initial + boundary condition - 50% burial

For my purposes, I care primarily about how these models represent the observations that we have in Penn Cove, especially bottom DO. Focusing on the years where we have some of the observations, I am showing the time series of King County's two main sampling stations in Penn Cove for the three models in 2024-2025, compared to observations.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/d6243e7b-0289-494b-b676-368c610ea917" width="800"/><br>Fig 1. Three models compared to observations at King County Penn Cove sampling stations for bottom DO.</p><br>

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
