# Revising Paper 1 Scope

This work is part of revising my Paper 1 to fortify my discussion of salinity change mechanisms. I'm using our long-term site time histories as well as Ecology 

This work is part of revising my Methods section in Paper 1 and incorporating GRL reviewer feedback.

Reviewer #1 wanted my to try evaluating secular trends using some sort of smoothing regressions, like the Generalized Additive Model (GAM) which apparently is non-parametric and is robust to overfitting. I had been skeptical given the data was is gappy and has has more modern than historical observations. Nonetheless, I wanted to show you these to see if this is something we should consider adding to the paper.

Here's my first attempt, using a linearGAM. Realistically I don't know exactly what all the parameters are that I can control with this since I haven't delved in too deeply, but this simply model shows the following time histories on my current Paper 1 Figure 6:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b48581c6-9934-46bf-8a1f-e86da4d6e2f9" width="800"/><br>Fig 1. GAM test on August-November bottom long-term time histories for Paper 1.</p><br>

This is showing a bit of decadal oscillation, which would be a potentially helpful thing to call out in the Results section, though we ultimately focus on monotonic trends. However, the big data gap makes this fitting a little wacky.

I also did the same method but sectioned the data into a "through-1988" and "post-1988" sets to resolve the GAM on either side of that big gap. Here's what I got there:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/62173568-7d67-483e-aa63-d17cb73b1bad" width="800"/><br>Fig 2. Partitioned GAM test on August-November bottom long-term time histories for Paper 1.</p><br>

Here, there is a vast difference in the shape of the GAM on either side of the gap, due to the sampling differences. In the more modern samples, we can resolve some wiggles on a smaller timescale - but I think this is just a step too far. I think this may be too much stats for what is also just kind of imperfect observational data.

This was just a quick effort, but I wanted to show this in case this was something we opted to include given the reviewer comments from GRL. If included, my current plan is to say something brief in the Results section, to the effect of: "GAM shows decadal variation, which may be correlated with Eastern Pacific decadal cycles like PDO, but are outside the scope of this work as we focus on monotonic trends. However, this does necessitate using a signficantly long time history to assess monotonic trends despite this decadal variation."

If we want to go in more depth here, I can - but for now I'll show you these and stay the course with monotonic trends.
