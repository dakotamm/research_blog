# Updated Whidbey Mooring Time Series + WWTP Loading

**NOTE:** I have not done further evaluation on the model at this point. These are meant to discuss hypotheses about Penn Cove and give begin to anser some initial questions about field planning for December.

I'm using the very preliminary, very much not realistic mooring locations that were initially plotted on Google Maps:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/b3316a98-b64f-4bef-8a9c-b2e6c6c644d7" width="800"/><br>Fig 1. Preliminary mooring locations in Penn Cove.</p><br>

I took daily mooring extractions from the entire water column (30 sigma layers) to create time series of mooring temperature, salinity, DO, u-velocity (eastward positive), and v-velocity (northward positive) at each mooring, and found some PRELIMINARY cool stuff:

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/100965a7-4971-4431-8e9e-fe8e8985f2b4" width="800"/><br>Fig 2. Time series of M1 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/0772eda1-5fdf-4fb0-ad2c-0554841a29e4" width="800"/><br>Fig 3. Time series of M2 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/c7738f00-fbc4-4859-9b36-64b81a356df9" width="800"/><br>Fig 4. Time series of M3 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/1b447251-64ee-4c1f-b578-895bc3537654" width="800"/><br>Fig 5. Time series of M4 mooring extractions my high-resolution Whidbey Basin model.</p><br>

<p style="text-align:center;"><img src="https://github.com/user-attachments/assets/a935216f-6717-4091-aeb8-eb400c3fdedb" width="800"/><br>Fig 6. Time series of M5 mooring extractions my high-resolution Whidbey Basin model.</p><br>

Cool stuff as follows:
* There is a significant freshwater intrusion occurring in early December (how convenient!). If you look at the M3 time series, you can see that we get a westward (-u) velocity at the surface corresponding to this intrusion, as well as southward (-v) velocity, which indicates this is likely from the Skagit River.
* Looking at M3 still, this westward flow at the surface has concurrent eastward flow at the bottom - corresponding to our hypothesized "reverse exchange flow"!!!
* Now we really only see hypoxia develop at M1 (and a little bit at M4). Contrary to some canonical hypotheses, the development of hypoxia is not preceded by salinity stratification. In fact, the summer appears to be fairly well mixed in terms of salinity.
* However - there is fairly significant thermal stratification. Perhaps this is an important mechanism for driving hypoxia development?
* We can see that the December freshwater intrusion brings cold, oxygenated water to the surface and nearly to the bottom at M1, seemingly breaking up the hypoxia. We don't see hypoxic mass advecting outward at M3, however, though other processes could have reoxygenated it above the hypoxia threshold coloring these time series.
* Maybe not as cool - there appears to be some asymmetry across the channel. In particular, M4 actually does have hypoxia unlike M2 and M3. Is this due to advection of the hypoxia from M1 that tends to flow southward out of the channel? Or is this due to local development?


<img width="2744" height="1755" alt="wwtp_din_kg_day" src="https://github.com/user-attachments/assets/3451126f-bd5a-4062-be51-e608e199de12" />
<img width="5549" height="6887" alt="M1_lowpass_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/cb4e1258-54e2-4805-9a1a-1b3d71faa098" />
<img width="5483" height="6887" alt="M2_lowpass_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/590cd765-c238-4a60-a58c-ee3e3afa7183" />
<img width="5483" height="6887" alt="M3_lowpass_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/49470705-cb84-4ccf-a02f-487be9939bde" />
<img width="5483" height="6887" alt="M4_lowpass_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/5050d92c-c4e8-4ee8-a160-6dc94e765194" />
<img width="5483" height="6887" alt="M5_lowpass_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/7ca0c290-fe62-4346-a5dc-45fbc916dbb6" />

<img width="5483" height="6887" alt="M1_hourly_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/4ea7ab2b-3999-496f-bcaa-44f59a8c35a4" />
<img width="5483" height="6887" alt="M2_hourly_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/4321d18a-a3fc-43a8-b9b5-06030d2a4605" />
<img width="5483" height="6887" alt="M3_hourly_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/a2adf547-ba5c-44a7-b9f7-50923b5d2b62" />
<img width="5483" height="6887" alt="M4_hourly_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/e5dd0dbe-0bcb-4c4a-ab0c-c3b8b4495eb6" />
<img width="5483" height="6887" alt="M5_hourly_CT_SA_DO_u_v" src="https://github.com/user-attachments/assets/f4e2015b-a480-47e3-ab75-174bd22a7b55" />
