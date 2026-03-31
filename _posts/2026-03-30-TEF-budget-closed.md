# Penn Cove TEF Debugged

Closing the loop on the saga of my simple Penn Cove TEF budgets, I've implemented a few changes that has made it all look "closed".

First, I've been able to run my model with hourly average output in addition to hourly history files. In ROMS, writing average output allows us to write the volume flux as a model field instead of calculating it from instantaneous snapshot velocities and sea surface heights. This allows us to tighten the ocean flux term. For the dV/dt term, I use the hourly snapshot total volume of my TEF segment.

The second piece of the puzzle is a slight error I made in the interpretation of specifying "open boundaries" in various locations in the file. Specifically I needed to define the boundary section for the terminal segment, not the open boundary for the whole domain in budget_functions.py. All that said, both solutions are required to get a nicely closed budget. 

Here are my closed budgets (huzzah!):

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0367ae00-ed18-449d-a1eb-f8fc90fcc5cf" width="800"/><br>Fig 1. Salt budget for Penn Cove model year 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/3291daba-0ccf-4dc1-a979-b775eefe53c0" width="800"/><br>Fig 2. Heat budget for Penn Cove model year 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/6a27ea16-82eb-4402-9b29-13e984a02dc3" width="800"/><br>Fig 3. Oxygen budget for Penn Cove model year 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f66931f3-087e-4fdf-b2c2-26732a3e1c5e" width="800"/><br>Fig 4. Volume budget for Penn Cove model year 2017.</p><br>

Next step with budgets is to run Jilian's more nuanced oxygen budget code to elucidate bio and air-sea flux components of the budget.

For posterity, finally debugging this has been the result of actually using Copilot, VSCode's AI agent - specifically, Claude Opus 4.6. I'd love to discuss more what I've found really valuable about this process and how it made debugging this more efficient, as well as what our next steps as a group can and should be as AI becomes more of a required skillset for writing and testing code.
