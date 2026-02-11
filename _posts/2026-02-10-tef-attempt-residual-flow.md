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

I made a movie of the hypoxia development (August-October) period using lowpass-filtered output, trying to visualize if this two-cell circulation pattern is consistent, or if changes in this circulation may lead to the initial development of hypoxia. Note this is surface velocity - I'm working on really getting a clean plotting code base to work across machines, but we're working with some legacy scripts here for now.

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/e0d14f52-8b00-4aea-add9-7b072fb28745" controls="controls" style="max-width: 800px;"></video><br>Fig 7. Penn Cove lowpass-filtered bottom DO and surface velocities for 2017 August-October.</p><br>

Conversely, I made an hourly plot for just our spring and neap periods during 2017.

<p style="text-align:center;"><video src="https://github.com/user-attachments/assets/69b0c2e0-e031-4c2f-a21c-e93ee1088bc4" controls="controls" style="max-width: 800px;"></video><br>Fig 8. Penn Cove hourly bottom DO and surface velocities for 2017.09.05-2017.09.18.</p><br>

