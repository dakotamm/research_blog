# New Whidbey Basin model is scaring me

This week, I ran my new Whidbey Basin model, wb1_t0_xn11ab, for 2024 and through about April 2025, with intent to run for all of 2025. I ran some checks before it got to the expected "hypoxia" season and saw no red flags, but now seeing this, I've stopped the model.


I spent the time to update all the King County data since the last time I did so, in early 2024. So now we should have a lot of data to compare to the model, and we're also using nceiSalish and ecology_nc data. The first plot is a simple property property plot with bottle data for 2024.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/3223cba1-1440-4691-9743-f53a5212df67" width="800"/><br>Fig 1. 2024 bottle obs/mod property-property plot for wb1_t0_xn11ab.</p><br>

To note: not tons of bottle data, but it seems pretty reasonable. The model overpredicts NO3 and DIN however.

Now, let's look at the same plot but using CTD data:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6ed9fc90-a2d7-42e9-9a1c-7ab8ce16e36f" width="800"/><br>Fig 2. 2024 ctd obs/mod property-property plot for wb1_t0_xn11ab.</p><br>

I'm pretty sure this is a little concerning... So I checked it out in a variety of different ways. Here's a map of how overpredicted the model is compared to observations for 2024 CTDs:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/d3d4b258-25c2-4be9-91f4-402b3e983761" width="800"/><br>Fig 3. 2024 ctd obs/mod overprediction plot for wb1_t0_xn11ab.</p><br>

Here's another concerning plot, showing that hypoxia actually doesn't develop in Penn Cove during 2024 (showing hypoxic days), despite observations suggesting that it should, and hypoxia developing elsewhere, including right at the mouth of the Skagit...?

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/fe79858f-71b4-4e10-8429-63ee66091cb9" width="800"/><br>Fig 4. 2024 ctd obs/mod hypoxic days plot for wb1_t0_xn11ab.</p><br>

Finally, here's the three Penn Cove stations' bottom DO comparing the model to observations for the full duration of the model output so far (note CW is not resolved in the model but provided for completeness):

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f4ba989d-63cc-43ce-9d44-c0b18cab4141" width="800"/><br>Fig 5. 2024 Penn Cove obs/mod bottom DOtime series plot for wb1_t0_xn11ab.</p><br>

The model is sort of the same shape, but not getting close to the minima.

So a few thoughts/troubleshooting planning:
* Am I mishandling model output? Always possible but haven't found a bug yet...
* Did I somehow totally mess with the BGC model in the changes I made? Here's what I changed:
  * Modified the bathymetry of Penn Cove to better resolve headlands and shallows
  * Incorporated TRAPS
  * Used cas7_t2_x11b for nesting - my understanding is this should have updated 50% burial, use TRAPS, and use GLORYS boundary conditions...
* Any chance I'm mishandling the observations? Again, seems unlikely so far but always possible.

My suspicion (and hope) is that I accidentally messed up the grid. While I haven't yet deep-dived on this, I have some plots comparing the two grids:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/319b0c76-a4e0-4241-a52e-d9af831d3085" width="800"/><br>Fig 6. Grid comparison for wb1_t0_xn11ab vs. wb1_r0_xn11b/wb1_r0_xn11ab.</p><br>

Penn Cove itself doesn't look terribly different, but perhaps these changes are significant enough?

I'd love some help figuring out some systematic next steps to fix whatever is happening.
