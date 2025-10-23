# Updated Whidbey Mooring Time Series + WWTP Loading

---

## Preliminary Time Series - Hourly and Lowpass Filtered

**NOTE:** I have not done further evaluation on the model at this point. These are meant to discuss hypotheses about Penn Cove and give begin to anser some initial questions about field planning for December.

I'm still using the very preliminary, very much not realistic mooring locations that were initially plotted on Google Maps:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b3316a98-b64f-4bef-8a9c-b2e6c6c644d7" width="800"/><br>Fig 1. Preliminary mooring locations in Penn Cove.</p><br>

Since last week, I was a little itched that the time series were a daily, hourly extraction at the mooring, which would be inherently aliased by tides. So I redid these plots a few ways. I'm putting all the plots here to be able to peruse. This first set is a hourly extractions for November 16-December 15, 2017:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/4ea7ab2b-3999-496f-bcaa-44f59a8c35a4" width="800"/><br>Fig 2. Hourly time series of M1 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/4321d18a-a3fc-43a8-b9b5-06030d2a4605" width="800"/><br>Fig 3. Hourly time series of M2 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a2adf547-ba5c-44a7-b9f7-50923b5d2b62" width="800"/><br>Fig 4. Hourly time series of M3 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/e5dd0dbe-0bcb-4c4a-ab0c-c3b8b4495eb6" width="800"/><br>Fig 5. Hourly time series of M4 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/f4e2015b-a480-47e3-ab75-174bd22a7b55" width="800"/><br>Fig 6. Hourly time series of M5 mooring extractions my high-resolution Whidbey Basin model.</p><br>

I also then ran a lowpass filter (LO's standard rolling 71-hour average) and got tidally-averaged mooring extractions from the entire water column:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/cb4e1258-54e2-4805-9a1a-1b3d71faa098" width="800"/><br>Fig 7. Lowpass filtered time series of M1 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/590cd765-c238-4a60-a58c-ee3e3afa7183" width="800"/><br>Fig 8. Lowpass filtered time series of M2 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/49470705-cb84-4ccf-a02f-487be9939bde" width="800"/><br>Fig 9. Lowpass filtered time series of M3 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/5050d92c-c4e8-4ee8-a160-6dc94e765194" width="800"/><br>Fig 10. Lowpass filtered time series of M4 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/7ca0c290-fe62-4346-a5dc-45fbc916dbb6" width="800"/><br>Fig 11. Lowpass filtered time series of M5 mooring extractions my high-resolution Whidbey Basin model.</p><br>

Takeaways:
* Tide stage seems very important in hourly velocity extractions!
* We can still see some cool flow reversal associated with the freshwater plume in early December.
* BIG: There seems to be some serious flow asymmetry between M2 and M4, with M2 having the dominant tidally-averaged INWARD flow in Penn Cove and M4 having dominant OUTWARD flow, suggesting some clockwise circulation around Penn Cove...

---

## WWTP Loading Trend?

In revising my Paper 1, I have taken a look at Aurora's valiantly cleaned WWTP effluent data from Mohamedeli et al., 2020 and Wasieliewski et al., 2024. This plot is the nitrogen loading in kg/day from all WWTP continuously monitored during this time:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/3451126f-bd5a-4062-be51-e608e199de12" width="800"/><br>Fig 12. WWTP monitoring loading time series for continuously monitored plants in Puget Sound.</p><br>
