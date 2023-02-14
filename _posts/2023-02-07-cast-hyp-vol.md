# Finding Hypoxic Volume from LO Casts

### Goals From Last Week:
1. Create estimation scheme for hypoxic volume in a cast area.
2. Start drafting Gordon Conference abstract.

### Completed Goals:
1. Started estimate scheme for hypoxic volume in a cast area.

---

## Hypoxic Volume from LO Cast Area

*After working furiously to creating plots and finish out this milestone, I'm not quite done. This update is short and sweet! :)*

Now that I can assign LO grid area to LO cast locations using KDTree, the next step is to put together the pieces and start to make estimates of hypoxic volume. From last week, I narrowed down to (9) cast locations occurring in real-life between June and August 2019 in the G1 segment.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/217370003-6bd60d30-c90e-41a3-a117-07d8e91f23ba.png" width="1200"/><br>Fig 1. KDTree assigning areas to (9) cast locations corresponding to those taken by DFO between June and Agust 2019 in G1 segment.</p><br>

For these test casts, I can find the depth at which the casts' reported DO passes a certain threshold. These test casts do not reach 2.0 mg/L, so I defined an arbitrary threshold (6.2 mg/L). Finding the minimum depth at which this "hypoxic" threshold is crossed, I will be able to calculate the volume below that minimum depth within that given area. Casts DO is shown below:

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/217370856-3f87d391-2e2c-4fd7-924b-00f233715a6c.png" width="800"/><br>Fig 2. DO vs. depth for (9) cast locations corresponding to those taken by DFO between June and August 2019 in G1 segment.</p><br>

Two of the casts fall below the arbitrary 6.2 mg/L threshold. If today was a better Python day, I would have plots showing you which cast area these are, and then the hypoxic volume of these cast areas given the minimum depth above the hypoxic threshold.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/217371932-8f896d2d-9bb3-4e71-8723-6923ea4e0431.jpg" width="400"/><br>Fig 3. Figure for aesthetic purposes from https://devs.lol/meme/python-can-hurt-you-in-other-ways-108.</p><br>


Some points of musing: 
1. If real casts do not reach lowest depth, do we infer the properties of the deepest cast point for that cast, or the properties of a point of the same depth from a different cast? Assuming time similariy.
2. Calculating volume from obs data casts using LO gridcells with large spacing (casts may have finer resolution than gridcells, may need to part out gridcells).

---

## Bookkeeping 
* KC Meeting scheduled for Friday, February 24, 2023
* EFM Talk scheduled for Thursday, March 2, 2023 (20 minute presentation).
* Quarter Planning...(in progress)
  * Remaining from last quarter:
    * Come up with estimation scheme using LO data.
  * Dig into obs data.
* Gordon Conference Abstract - tracking draft ASAP.
  * I may have a conflict with Sunday/Monday of conference dates.

---

### Issues/Questions:
1. DFO obs data - keep this on my radar for now.
2. In the thick of it with class workload - how to prioritize?

### Looking Ahead:
1. Gordon Conference abstract in the next days.
2. Fully implement test hypoxic volume scheme.
3. Next: hypsography!

### Goals For This Week:
1. Gordon Conference abstract in the next days.
2. Fully implement test hypoxic volume scheme.
3. KC document overview starting next week.
4. Set quals date with Mike/Parker/Alex.
