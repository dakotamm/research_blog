# New Whidbey Basin Model is Worrying Me

This week, I ran my new Whidbey Basin model, wb1_t0_xn11ab, for 2024 and through about April 2025, with intent to run for all of 2025. I have now stopped it because it's freaking me out a bit.

I spent the time to update all the King County data since the last time I did so, in early 2024. So now we should have a lot of data to compare to the model, and we're also using nceiSalish and ecology_nc data. The first plot is a simple property property plot with bottle data for 2024.

[BOTTLE PROP-PROP 2024]

To note: not tons of bottle data, but it seems pretty reasonable. The model overpredicts NO3 and DIN however.

Now, let's look at the same plot but using CTD data:

[CTD prop 2024]

I'm pretty sure this is a little concerning... So I checked it out in a variety of different ways. Here's a map of how overpredicted the model is compared to observations for 2024 CTDs:

[overpred map 2024 ctd]

Here's another concerning plot, showing that hypoxia actually doesn't develop in Penn Cove during 2024 (showing hypoxic days), despite observations suggesting that it should, and hypoxia developing elsewhere, including right at the mouth of the Skagit...?

[hyp days map 2024]

Finally, here's the three Penn Cove stations comparing the model to observations for the full duration of the model output so far:

[penn cove stations time series not combined]

The model is sort of the same shape, but not even getting close to the minima.

So a few thoughts/troubleshooting planning:
* Am I mishandling model output? Always possible but haven't found a bug yet...
* Did I somehow totally mess with the BGC model in the changes I made? Here's what I changed:
  * Modified the bathymetry of Penn Cove to better resolve headlands and shallows
  * Incorporated TRAPS
  * Used cas7_t2_x11b for nesting - my understanding is this should have updated 50% burial, use TRAPS, and use GLORYS boundary conditions...
* Any chance I'm mishandling the observations? Again, seems unlikely so far but always possible.

My suspicion (and hope) is that I accidentally messed up the grid. While I haven't found this to be the case yet, I hope to have some further updates by tomorrow.

I'd love some help figuring out some systematic next steps to fix whatever is happening.



After closing the loop on the simple TEF volume budgets last week, I implemented an adaptation of Jilian's budget codes that actually estimates air-sea flux and biological processes, as modeled by LO. Jilian used a higher light attenuation in specific portions of her model, but for now I opted to stay with the model default. Here are the test budgets for the January 1-21, 2026:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/cf4d38e8-cb22-4fad-a17b-11df0e42a24f" width="800"/><br>Fig 1. Heat budget for Penn Cove model year 2017 using Jilian's code, adapted.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b26492f3-20d6-4593-8242-b16bcad619dd" width="800"/><br>Fig 2. Oxygen budget for Penn Cove model year 2017 using Jilian's code, adapted.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/c9593198-0bfe-4f20-a455-49ad4bc9f005" width="800"/><br>Fig 3. TN budget for Penn Cove model year 2017 using Jilian's code, adapted.</p><br>

Notably, the individual DO and TN sources and sinks that are calculated within this codebase tend to increase in magnitude over the three weeks. Are these physical, a product of model "spin-up", or an error on my end? Stay tuned as I dive in and investigate these budgets for a full year!