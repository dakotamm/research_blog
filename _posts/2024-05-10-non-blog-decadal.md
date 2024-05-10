# Off-Piste Data Update - Decadal Surface/Seasonal DO/SA/CT Analysis

I want to throw these plots out for your perusal! After a lot of finagling this week, I've settled on the following sites as viable for decadal analysis:
1. Carr Inlet Mid
2. Hat Island
3. Hood Canal Mouth
4. Lynch Cove Mid (considering bottom 60% of water column)
5. Near Seattle Offshore (Vashon to Alki, approximately)
6. Point Jefferson (really awesome time series here from Taylor)
7. Saratoga Passage Mid
8. Saratoga Passage North

A side note that I tried to get some decadal resolution for Elliott Bay but sampling depth was too inconsistent.

Now I have my 8 sites, and I wanted to follow Carstensen et al. (2014) in presenting some time annualized time series. For our purposes, I've split this into two seasons for a few reasons. One is that simple monthly seasons seemed a little arbitrary and prone to interannual variability, and also that we tend to observe low DO during most of what I'd refer to as the "growing" season. So my seasons here are:
1. Yearday 125-325 = "Grow"
2. Else = "No Grow"

Carstensen et al. (2014) use a lot of cool time series like depth of halocline, Brunt-Vassala frequency, and AOU - but for now I stuck with surface and bottom measurements. For these plots:
1. Surface = top 10% of deepest site gridcell
2. Deep = bottom 20% of deepest site gridcell (EXCEPT Lynch Cove, which considers the bottom 60%...)

For each point, I average each cast within these depth bins, then I calculate an annual mean for each season and assign a 95% confidence interval.

With all of this, I now have some time series that I think are worth disecting further:


<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/5b29c555-7769-481a-b642-0becff15501b" width="800"/><br>Fig 1. Carr Inlet Mid seasonal surface/deep SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/1533adef-f49c-406e-8078-3318a709b070" width="800"/><br>Fig 2. Hat Island seasonal surface/deep SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/550166e8-ae04-4793-8d0f-e519af70dece" width="800"/><br>Fig 3. Hood Canal Mouth seasonal surface/deep SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/55763e73-a0e7-47ec-9cbf-7c79d968a4a4" width="800"/><br>Fig 4. Lynch Cove Mid seasonal surface/deep (bottom 60%) SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/e3dc87dc-0433-41c1-ac14-ed129fc18047" width="800"/><br>Fig 5. Near Seattle Offshore seasonal surface/deep SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/8d9690b2-faec-46ba-a5c8-bcb65781e9bd" width="800"/><br>Fig 6. Point Jefferson seasonal surface/deep SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/c3284b91-3b52-4c1c-ab4c-fd3e2314ac86" width="800"/><br>Fig 7. Saratoga Passage Mid seasonal surface/deep SA/CT/DO.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/91be59ae-80a6-4ffc-b575-d53c930ef088" width="800"/><br>Fig 8. Saratoga Passage North seasonal surface/deep SA/CT/DO.</p><br>

I haven't spent a ton of time analyzing all the nuances but it's cool to see the seasonal differences (despite my strange seasons), where bottom DO is lower in the grow season and temperatures are higher at the surface. However, there is not such a clear seasonal variation in seasonal salinity like I would expect. In particular in Saratoga Passage, I kind of expected there to lower salinity overall in the "No Grow" season, which corresponds to rainy winter months. My seasons are weird and don't well capture water year, so that's something to consider. There's a whole ton of surface variability in salinity, however, so maybe that's something to look into more.

Also - for surface temperature and salinity at some of the better resolved sites, there appears to be some multi-annual oscillation. Even though depth is less well-resolved, we do see some oscillation at certain sites.

Looking at Point Jefferson in particular...it looks pretty convincing that there is a warming trend and maybe a tiny little DO downward trend.

I think I've gotten to the point this week where I've played with this data so much this week that I need to start writing about it. So I think I'll start :).

Next steps with these decadal series:
1. Confirm these are the variables we care about. Confirm seasons, depth bins, etc.
2. Formalize trend tests (e.g., Mann-Kendall).
3. Trends in variability?
4. Describe oscillation.
5. Concurrently, describe regional variability.

I'd really appreciate your feedback on this. Happy weekend!
