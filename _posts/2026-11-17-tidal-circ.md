# Describing tidal and residual circulation in Penn Cove

...is not easy, so it seems. I am hoping that y'all can help me focus on what's important for my Chapter/Paper 2.

The main dependent variable we care about is DO, but having some description of at least the kinematics of tidal circulation seems like an important step.

I have tried very many ways to get a descriptive model of tidal circulation; unfortunately, the more I try to simplify, the more complicated it becomes! So here's some of my understanding so far...

## What does the velocity look like in Penn Cove?

I have taken a look at this in a few ways. One way has been to look at all floods and ebbs and average them, or lesser/greater floods/ebbs. In general I am taking a Godin-filtered hourly velocity and then averaging that over each time period. In this case, I have all the PEAK flood and ebb hours averaged over the course of 2024, then the average Godin-filtered residual.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/09be122c-c3c2-46ab-bd5a-a4605dafb0e7" width="800"/><br>Fig 1. Map of averaged PEAK flood and ebb hours + Godin-filtered hourly residual over 2024 for surface 1/3, bottom 1/3, and depth-averaged velocities.</p><br>

Conversely, I can represent an identical view for a specific lunar day that represents an "average" tide in terms of spring/neap, tropic/equatorial, stratification, and wind stress at the surface. Selecting these days has required hypothesizing which variables are the most important drivers of tidal variation (these four for now), making time series of these variables, ranking each day on the time series, and the selecting the day closest to average on all these axes. The same plot of ONE "average" lunar day (2024.08.31-2024.09.01) is as follows:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f99c5f8e-3c46-45c3-b61b-83b0f7d87046" width="800"/><br>Fig 2. Map of baseline day PEAK flood and ebb hours + Godin-filtered hourly residual for surface 1/3, bottom 1/3, and depth-averaged velocities.</p><br>

Similarly, I can look at the cross-sections anywhere, but here we look at the Lovejoy line I've defined.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0c69aa0d-9838-4b23-998a-2480e4f5c038" width="800"/><br>Fig 3. Section at Lovejoy of average PEAK flood and ebb hours + Godin-filtered hourly residual over 2024.</p><br>

And now the baseline day!

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/bab3893b-1776-401d-b1a3-c3e02b88fbec" width="800"/><br>Fig 4. Section at Lovejoy of baseline day PEAK flood and ebb hours + Godin-filtered hourly residual.</p><br>

Is there a way to do this that anyone has seen more of or would prefer? Clearly there is variation in what can be considered the baseline, and how to represent it is something I am struggling with.

## Tidal ellipses?

Part of this study has been decomposing the tidal constituents as well. So I ran utide and created tidal ellipses.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/ef96bc48-951e-44e0-ba3b-29be93029a02" width="800"/><br>Fig 5. Top 1/3, bottom 1/3, and depth-averaged tidal ellipses for top 4 constituents over 2024-2025.</p><br>

## What does tidal velocity look like at Lovejoy?

One way I've been trying to see patterns here is creating profiles and cross-sections of velocity. Both the layered and lateral transport are important parts of both the tidal and residual circulation.

Here I've also broken out the greater and lesser ebb and have plotted in gray every hourly profile. The thick orange line is the average profile and the dotted line is our baseline day profile.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/89380897-14ef-4eb3-81e1-cadd7b0de018" width="800"/><br>Fig 6. Greater and lesser flood and ebb profiles at Lovejoy during 2024.</p><br>

## What modifies tidal velocity?

If tidal velocity are modified, then that might lend clues as to the residence time experience by particles which ultimately leads to hypoxia. Also, there is clear variation in the individual tides we see in the model, which is an important physical process for us to summarize. So, I have tried to look at what could modify just tidal velocity from many directions, with limited success.

While I have ran EOF analyses on the full velocity field, I think I've been personally able to understand more from the profile shapes (though I'm still not sure how confident I am). Here are the EOFs of the Lovejoy velocity profiles and cross-sections.

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/493f33cd-a66b-4610-9a55-a611ee382b9a" width="800"/><br>Fig 7. EOFs of Lovejoy and profile shapes.</p><br>

After some statistics that I'm beginning now to understand a bit, these factors are standardized coefficients, or effectively, if each of these variables shifts by a standard deviation, how many standard deviations does the mode change? More is a bigger effect of that individual variable, based on linear regressions. Note that these variables were selected in part for their independence from each other after trying many (these are the most independent variables that represent a certain possible physical effect that I tested). Here are these coefficients:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/061845d2-686e-4d74-987f-9015b2846f41" width="800"/><br>Fig 8. Primary EOF modes' standardized coefficients from a list of physical forcing mechanisms at Lovejoy for 2024.</p><br>

Takeaways:
* Wind is the most consistent driver across.
* A deepening pycnocline through the tide strengthens the two-layer shape (this makes sense).
* Stratification at slack strengthens two-layer flow on big tides but weakens it on small tides?!
* Denser water outside the cove means less deep outflow (as in estuarine circulation counteracts the mode shape)?
* Higher diurnal inequality makes the greater flood more two-layered and the lesser flood less two-layered.
* Spring/neap (tide size) doesn't really modify the shape, just the speed.
* Denser surface water outside of Lovejoy enhances the mid-depth out mode!
* Up-cove wind weakens the mid-depth out mode!
* Lateral structure is super robust and isn't really modified by these variables too much.

About half of the variation in the model is not accounted for. I haven't considered cross-channel density gradients nor greater time lags in wind/velocities within the Cove, nor "nonlinear" interactions. I'm also not sure how much of this is necessary; this seems to corroborate that the shape is variable and depends somewhat on wind!

Anyway - send help. I need to get out of just describing tidal circulation!
