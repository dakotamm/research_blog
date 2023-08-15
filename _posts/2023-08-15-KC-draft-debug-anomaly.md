# Initial Conditions Progress and Temperature/Salinity Exploration

### Goals From Last Meeting:
1. Initial conditions for 2017!!!
2. KC draft by end of week.
3. Looking ahead to TS plots + digging more into 2015 anomaly.

### Completed Goals:
1. Initial conditions for 2017 - some progress.
2. KC draft sent yesterday, 8/15/2023.
3. Digging more into 2015 anomaly.


---

## KC Draft Review

I sent this Monday, 8/15/2023 and hope to spend time reviewing! In particular:

1. I'm not sure how to transition from error analysis to data exploration in the narrative. I feel like the error analysis is somewhat inconclusive...
2. What results should I present given how preliminary they are?
3. Taylor mentioned a cast and hypoxic depth plot styled after DOE's validation for the Salish Sea Model where casts depth properties are shown in color against a similarly-colored model output backdrop. This didn't quite make the cut of high priorities for this presentation but I can still make it!

---

## 2017 Initial Conditions Using Observational Data

This week I've managed to work through the issues caused by the change to cas7 grid. After the change, some segments were defunct due to the addition of the Swinomish Channel. After some digging into the tef segmentation code and working through with Parker I edited tef sections interacting with Swinomish Channel in my own local copy on LO_user and have solved the issue.

I'm so close! Goal is to finish this by the end of next week, so Aurora and I can debug and run by the end of next week.

---

## Data Exploration and Anomaly Debugging

Last week, I presented bottom 20% water column DO, temperature, and salinity seasonal averages. There was a significant outlier in both temperature and salinity during 2015, which correlated with particularly low DO. At first this seemed attributable to the Blob, but various sources including ORCA buoys and Department of Ecology's Eyes on Puget Sound recaps tended to disagree with the extremely low temperature and high salinity anomaly.

After some digging, I found some erroneous DFO casts with extremely low temperature and high salinity were being attributed to Puget Sound. Perhaps these are from an offshore region? While I'm not sure which portion of my processing code caused this error, rewriting my observational data frames has fixed the issue. This will certainly be something to watch out for in the future before I find the exact root cause.

I'll note that DFO does apparently have some casts in Puget Sound. The following plots in Figure 1 from Parker's obs scripts show DFO casts in Puget Sound. I'll dig into this further and confirm that these are not erroneous and/or also satisfy my curiosity as to why DFO has US sampling during certain years.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/92b9e83b-b02e-45d8-9171-0696e827dcc5" width="800"/><br>Fig 1. DFO 2015 CTD data from Parker's obs scripts.</p

Following the anomaly fix, I can recreate the following plots with only Puget Sound data:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/f17754e9-dcb3-4913-b107-16622286ce2b" width="800"/><br>Fig 2. Main Basin regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/1de5c0c3-bb86-4504-b969-d061e252637c" width="800"/><br>Fig 3. Admiraly Inlet regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/d4d62f35-8a4d-4c93-b015-89df4bcc74ae" width="800"/><br>Fig 4. South Sound regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/a333eee0-87fb-43e3-a503-0388b4072b38" width="800"/><br>Fig 5. Whidbey Basin regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/26375149-ac5a-40d1-a84e-0ab13f9a852f" width="800"/><br>Fig 6. Hood Canal regional bottom 20% of water column DO, temperature, and salinity seasonal averages.</p><br>

The anomaly in 2015 appears to have been erroneous and there is potentially a slightly less pronounced upward trend until 2010-ish. However, it seems inconclusive still that there is a distinct downward trend.

---

## Questions Toward Paper 1

From two weeks, I was asked to make my data exploration a little more honed via asserting questions that I might seek to answer in my first paper, which is helpful! We didn't get to chat about it much last week so I'm leaving it here:

1. Is there an observable multi-decadal trend in DO throughout the whole Salish Sea?
   * So far, we've seen that there is really sparse data (in current datasets) before the 2000s. With this data, we can't really make out an upward or downward trend in the Salish Sea as whole, or in the Strait of Georgia, Strait of Juan de Fuca, and Puget Sound as a whole.
2. Are there observable multi-decadal trends in DO throughout different regions? How do regions compare and contrast in DO trends?
   * We DO see some variation since 2000; however, the trend is increasing DO peaking at 2012 and then a decrease reaching a low during 2015 (Blob year). Some regions seem to show a slight decline since 1999 (like South Sound) and some regions show a "mountain" pattern (like Hood Canal).
3. Does DO co-vary with temperature, salinity, NO3, etc.? What are the most significant predictors of DO, if there are any?
4. What's the correlation between environmental indicators and events (i.e., the Blob, PDO, ENSO) that correlate with these trends?
5. Are there significant events that warrant further study, like the Blob?
   * 2015 seems to be a spicy year - so maybe!

---

## Bookkeeping 
* KC Quarterly Update - Thursday, August 17, 2023
* August 21 - September 15, 2023 remote work

---

### Issues/Questions:
1. Common error estimation methods + statistical bias/error - need lit. review.
2. Organize literature - Endnote or Bibtex.
3. CTD/bottle duplicate DO in ecology set - clean this in VFC (output not affected, only number of casts included).
4. Weird "1-cast = np.nan hyp_vol" issue comes up on 4/2017, 5/2019, and 6/2019. May be an averaging problem.
5. Data cleaning (1950 DO concentrations).
6. Averaging casts in same location.
7. Write VFC-specific command-line tags.
8. Weighted averages are not doing a linear interpolation between gridcell depths yet.
9. Averages below threshold depth are only written for obs data so far.
10. Write plotting functions.

### Looking Ahead:
1. Initial conditions for 2017.
2. Finish KC data cleaning.
3. KC meeting deliverables ongoing.
4. VFC for Aurora's LO output.
5. Readings with Aurora.
6. Reach out to Greg Johnson!
7. Remote work next week!

### Goals For This Week:
1. Initial conditions for 2017!!!
2. KC draft by end of week.
3. Looking ahead to TS plots, more data exploration.
4. Remote work plan by end of the week.
