# KC Debrief, Continuing Initial Conditions, and A Bit of Data Exploration

### Goals From Last Meeting:
1. Initial conditions for 2017!!!
2. KC draft by end of week.
3. Looking ahead to TS plots, more data exploration.
4. Remote work plan by end of the week.

### Completed Goals:
1. KC draft and meeting!
2. TS plots - more data exploration.
3. Remote work plan by end of the week.
4. Progress on initial conditions...

---

## KC Debrief

The KC summer update was short and sweet and since there were a few people missing/having to leave early, there wasn't as much opportunity for feedback. However, here's a few takeaways:
1. Mike asked if I'd made T/S plots (as an addendum to the property plots I showed as preliminary for Hood Canal), which I hadn't.
2. We met Tall (Susan's post-doc at UBC) who inquired about observational data sources - I've scheduled a meeting with him to compare resources and get acquainted.
3. Given the interesting trends seeming to come out of the observational data record and Taylor's previous CEE presentation, we noted that we should schedule her into our October group meeting to discuss some of her finds. (I will also watch her lecture recording!)

---

## 2017 Initial Conditions Using Observational Data

I'm so close! This is the week!!!

I have one strategy question: When applying cast properties, I'm doing it by finding the nearest data depth to each gridcells' center. If the grid depth exceeds the nearest neighbor cast, I intend to apply the same algorithm and just give all cells beneath the maximum depth of the applicable cast the same properties as the last point. **Confirming this makes sense?**

---

## A Wee Bit of Data Exploration

Since last Thursday, I followed Mike's question and made some property-property plots including T/S. Focusing on Hood Canal, first I looked at the T/S colored by season:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/61a1831b-fd2d-4033-af8d-4f8684edd574" width="400"/><br>Fig 1. Hood Canal bottom 20% of water column temperature vs. salinity monthly averages colored by season.</p><br>

We can see an interesting trend where temperature and salinity tend to vary directly, though with significant spread. This is likely due to the fact that warmer temperatures correspond to summer and fall, during when there is lesser freshwater influx. However, this needs further verification.

Taking this a step further, I looked at the variation of DO with T and S:

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/444c75b8-3bb5-42a3-a0dc-d26e0ca8bf1d" width="400"/><br>Fig 2. Hood Canal bottom 20% of water column temperature vs. salinity monthly averages colored by DO.</p><br>

This is pretty interesting. Highest DO is correlated with moderate salinity and lower temperature (which makes sense due to winter mixing). On the other hand, lowest DO is not necessarily correlated with an extreme in T/S and tend to be somewhat scattered.

To get a little more intrigue, I took a quick look at T/S, S/DO, and T/DO plots broken out by season and colored by the non-axis property. I need to work a little on the presentation of this but I think this provides an interesting look at correlations in Hood Canal.

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm.github.io/assets/55995675/444c75b8-3bb5-42a3-a0dc-d26e0ca8bf1d" width="800"/><br>Fig 3. Hood Canal bottom 20% of water column property-property plots **colored by the non-axis property**.</p><br>

---

## Questions Toward Paper 1

I was asked to make my data exploration a little more honed via asserting questions that I might seek to answer in my first paper, which is helpful! We didn't get to chat about it much last week so I'm leaving it here:

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

