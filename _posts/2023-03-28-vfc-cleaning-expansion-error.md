# Volume-From-Casts (VFC) Method Cleaning, Domain Expansion, and Error Quantification Preview

### Goals From Last Meeting:
1. Fix bug causing erroneous "zero-ing" at domain edges.
2. Expand volume-from-casts method domains.
3. Continue error-estimations.
4. Continue discussion with KC for Whidbey Basin monitoring data.
5. Finish out quarter!!!
6. Start studying for quals.

### Completed Goals:
1. Fix bug causing erroneous "zero-ing" at domain edges.
2. Expand volume-from-casts method domains.
3. Continue error-estimations.
4. Finished Winter Quarter.
5. Quals studying commenced.

---

## Follow-Up From Last Meeting

From last meeting, we discussed sources of error in the VFC/LO subthreshold thickness. It was identified that some gridcells near land were showing erroneous 0 mg/L dissolved oxygen values due to my LO output subthreshold calculations. Debugging to ensure land mask match between the LO and VFC methods has removed the 0 values, and thus we can see better agreement between VFC and LO subthreshold volumes and thicknesses. The following figures illustrate improved agreement.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228362440-f7ed4b4d-adeb-4017-8358-f2f1b7bc69c1.png" width="600"/><br>Fig 1. Subthreshold volume using 0.0 mg/L throughout 2022 (first of each month) for LO output and VFC method.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228362090-398b52ae-eb47-4e57-9d01-2e0ef5787a56.png" width="600"/><br>Fig 2. Subthreshold volume using 5.0 mg/L throughout 2022 (first of each month) for LO output and VFC method.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228362908-926dc303-5500-473a-b6fe-df387ff58d75.png" width="600"/><br>Fig 3. Subthreshold thickness using 0.0 mg/L for April 1, 2022 for LO output and VFC method.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228363016-2f9c4963-495f-4c40-9383-c5e3e46c7a4b.png" width="600"/><br>Fig 4. Subthreshold thickness using 5.0 mg/L for April 1, 2022 for LO output and VFC method.</p><br>

---

## Volume-From-Casts Progress

Since our last meeting, I have focused on organizing my workflow and cleaning up my VFC code. This has included defining flexible methods, breaking out functions to be in line with the LO ecosystem style, and enabling more automated workflow that is machine-agnostic, which will eventually allow full domain flexibility in time and space. This has elucidated some bugs rooted in lack of generality throughout the domain, which I'm working through.

As I've been working through the overhaul, I've been able to extend the domain to more segments in the Strait of Georgia. In this demonstration, they are: G1, G2, and G3. For reference, Figure 1 shows the Strait of Georgia segments.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228325464-b0bf802a-86a8-4de4-b734-02f9a7daab82.png" width="300"/><br>Fig 1. LO segments in Strait of Georgia and Strait of Juan de Fuca.</p><br>

For this brief study, I've specified a subthreshold volume for oxygen as 4.0 mg/L, and have specified casts from DFO locations during June 2019. Like previous studies, I've taken casts from LO history files on the first of each month throughout 2022. In order to understand the relative performance of VFC in each segment, I've calculated the RMSE and plotted the LO subthreshold volume for the three segments considered herein.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/228346349-6cad61a4-27c7-4ccd-9dfa-d7a85ee0dd61.png" width="900"/><br>Fig 2. DO subthreshold (4.0 mg/L) volume calculated using the volume-from-casts method and LO model output through 2022; LO output is compared to VFC output. RMSE is shown for each segment.</p><br>

We see that there is a higher normalized RMSE for the G3 region; there are also more months with subthreshold values in G3 (meaning that both LO and VFC predict subthreshold values during more months than in the other regions). Also there is a larger volume in this segment. These may explain the increase in normalized RMSE, but further investigation is required.

I intend to extend this error analysis to evaluate error; this will be conducted throughout the time and space domains. Through this I will incorporate additional observational data sets (i.e., ecology) as locations for this error analysis. Later, this will enable a framework to explore observational data and validate LO model output.

---

## Bookkeeping 
* Ocean Visions Summit:  flyng Monday, 4/3/2023 - Thursday, 4/6/2023
* Gordon Conference: flying Monday, 6/19/2023 (LATE) - Friday, 6/23/2023
* Quals: April 24-28, 2023 - oral defense Friday, 4/28/2023 at 10am
* WOAC Cruise: July 10-14, 2023

---

### Issues/Questions:
1. Common error estimation methods - need lit. review.
2. Figure out comments section on blog!!!

### Looking Ahead:
1. Quals studying...
2. AGU Ocean Visions next week

### Goals For This Week:
1. Confirm class schedule.
2. Quals studying - approximately 3-3.5 days a week.
3. Compare segment indices to land mask to check for mismatch (ref. bug discussed in "Follow-Up from Last Meeting" section.
4. Debug indexing issue that occurs when casts fall on masked domain.
5. Expand domain/cast location source.
