# Adapting Jilian's DO/TN/Heat Budgets for Penn Cove

After closing the loop on the simple TEF volume budgets last week, I implemented an adaptation of Jilian's budget codes that actually estimates air-sea flux and biological processes, as modeled by LO. Jilian used a higher light attenuation in specific portions of her model, but for now I opted to stay with the model default. Here are the test budgets for the January 1-21, 2026:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/cf4d38e8-cb22-4fad-a17b-11df0e42a24f" width="800"/><br>Fig 1. Heat budget for Penn Cove model year 2017 using Jilian's code, adapted.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b26492f3-20d6-4593-8242-b16bcad619dd" width="800"/><br>Fig 2. Oxygen budget for Penn Cove model year 2017 using Jilian's code, adapted.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/c9593198-0bfe-4f20-a455-49ad4bc9f005" width="800"/><br>Fig 3. TN budget for Penn Cove model year 2017 using Jilian's code, adapted.</p><br>

Notably, the individual sources and sinks that are calculated within this codebase tend to increase in magnitude over the three weeks. Are these physical, a product of model "spin-up", or an error on my end? Stay tuned as I dive in and investigate these budgets for a full year!
