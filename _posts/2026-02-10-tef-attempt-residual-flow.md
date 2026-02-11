# Penn Cove TEF Attempt and Plotting Residual Flow

## TEF Attempt

I wanted to jump in on TEF using Parker's README [documentation](https://github.com/parkermac/LO/tree/main/extract/tef2), even though I don't fully understand how this code works yet. I drew a simple section at the entrance of PC and attempted TEF for 2017.

Here's that section, and then two layer transport, salinity, and then Qin\DeltaS over the year.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0679db67-b00f-4edd-bd72-a2253fd8ad56" width="800"/><br>Fig 1. Bulk plot from TEF 2017 Penn Cove test and section line.</p><br>

Ultimately, I should get tracer budgets for my section. However, these examples look a little wild (NOTE: the label for Puget Sound is a typo - sorry):

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f68fc278-e507-4831-90d5-63f3d2f6d924" width="800"/><br>Fig 2. Salt budget for Penn Cove model year 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a9111d0a-249b-4c36-abb3-d9dc067d85a6" width="800"/><br>Fig 3. Heat budget for Penn Cove model year 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/ea1a28c2-4efa-4ffc-abca-9ae3c4ad1b00" width="800"/><br>Fig 4. Volume budget for Penn Cove model year 2017.</p><br>

The only term really doing anything here is "ocn", which is logical since Penn Cove doesn't have any rivers or inputs in this model. But I'd expect at least a bit of surface heat flux. So I think I did something wrong. I have quite a few questions to hopefully make sense of what I'm doing here (most of which I hope to discuss with Parker).

## Penn Cove Residual Flow Plots

From last week, I'm trying to visualize the spatial extent and timescale for hypoxia persistence with my 2017 Penn Cove model. First, I took an average over a "neap" time period, or a period has more symmetric tides. "Spring", conversely has higher amplitude and more tidal asymmetry.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/fcea172d-314b-4953-9be3-86da7aad54c2" width="800"/><br>Fig 5. September 2017 tidally- and depth-averaged u velocities overlaid with depth-averaged velocity vectors.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/74eb593d-1255-4f19-baad-7da3e0a16b62" width="800"/><br>Fig 6. September 2017 tidally-averaged bottom DO overlaid with depth-averaged velocity vectors.</p><br>

It appears that are two persistent zones in Penn Cove: a fairly stagnant cell that has just a bit of persistent counter clockwise circulation, and then a cell appears to come in from the north then out at the south with higher velocities. We don't really see a basin-wide clockwise circulation.

During the "neap" period, the outer "cell" intrudes more into Penn Cove than during the "spring" period. DO is distributed more toward the head of Penn Cove during "neap" than "spring". Perhaps this indicates a flushing process that is tidally modulated - low DO water may be advected along the south side toward exiting.

I made a movie of the hypoxia development (August-October) period using lowpass-filtered output since hourly output is overwhelming for this extent of time.

Putting some exploratory plots here. Using my Penn Cove model, I identified some spring/neap and ebb/flood tides. Starting with DO:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/1c7d13ed-7782-4f6f-8eef-566cdccaf38f" width="800"/><br>Fig 1. September neap flood bottom DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5cb6e698-4de9-4262-9831-7da5e701cfa9" width="800"/><br>Fig 2. September neap ebb bottom DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f6ece37e-c2fa-4b8f-8ddc-6c3baa1902c8" width="800"/><br>Fig 3. September spring flood bottom DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/94b919fb-97a9-414e-b95b-5c384dac3f60" width="800"/><br>Fig 4. September spring ebb bottom DO.</p><br>

Now bottom u-velocity:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/69c7eba7-ffe4-4bf7-b8f8-639e25e3f753" width="800"/><br>Fig 5. September neap flood bottom u-velocity.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/27ed2965-9173-454f-9683-bf41f3784904" width="800"/><br>Fig 6. September neap ebb bottom u-velocity.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a2d274a8-a65a-4537-86ae-c1f133019b0c" width="800"/><br>Fig 7. September spring flood bottom u-velocity.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b4b7c010-9bdf-4210-bb0e-61070f4debbe" width="800"/><br>Fig 8. September spring ebb bottom u-velocity.</p><br>

Now depth-averaged u-velocity:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0899c817-2751-4ff8-af2d-a861477578b4" width="800"/><br>Fig 9. September neap flood depth-averaged u-velocity.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/10f229c4-04e0-4240-823d-3eda5a2293cf" width="800"/><br>Fig 10. September neap ebb depth-averaged u-velocity.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/80f81747-2b70-4624-b63a-27a942e62251" width="800"/><br>Fig 11. September spring flood depth-averaged u-velocity.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/8a75f6f6-6509-4402-8d49-db24041f4e84" width="800"/><br>Fig 12. September spring ebb depth-averaged u-velocity.</p><br>
