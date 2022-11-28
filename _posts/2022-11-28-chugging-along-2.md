# Chugging Along 2

### Goals From Last Week:
1. Familiarize with cas6 grid.
2. Begin to understand LO daily output formats + lowpass tidal-averaging (after).
3. Bring down and organize DFO data from CIOOS ERDDAP server.
4. Get Endnote up and running - lit. review + notetaking.
5. Meet with Kate (scheduled for Tuesday, 11/22/2022).

### Completed Goals:
1. Gained understanding of working with cas6 grid.
2. Starting to understand LO daily output formats (lowpass tidal-averaging filter later).
3. Downloaded DFO data in .nc - use nco tools to concatenate.
4. Met with Kate - casual working meetings scheduled.

---

## Updates & Discussion

Despite the short week last week, I've been able to get more familiar with LO_data/LO_outputs/LO_roms. I've also been able to meet with Kate, who has been super helpful for discussing hypoxic volume estimation and for future questions.

Since Parker's generous tutorial last week, I've gained more familiarity with the cas6 grid and LO functions set up (i.e., using command-line arguments). Generally, I'm getting more used to LO structure and functions.

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/204375154-7bad4cfb-4ff2-4ecd-b785-af4a7c2703c7.png" width="1200"/><br>Fig 1. cas6 psi-grid depth values.</p><br>

The next objective is to start working with actual LO output data. I haven't gotten too far, but I can access the LO_roms live data. As I learn to work with it, a few questions to minimzie wheel-spinning:
1. Are there processed data products I should be working with instead of straight ROMs outputs?
2. Can you point me in the direction of a README to understand the field outputs for each "ocean_his_\*.nc" file? Is this ROMS- or LO-specific?

After I understand the output I should be using, the next step is to work with the outputs at each grid cell and hypoxic thresholds to start calculating hypoxic volume. This will provide a "source-of-truth" (i.e., add up the volume of each hypoxic grid cell). Kate has suggested using values of "intermediate hypoxia" = 2.0 mg/L as a test threshold, working on the assumption that this level exists at least at depth. Currently I'm working with 11/30/2022 data for the test case.

After I can do this at each grid cell, I will take casts and begin finding hypoxic threshold depth. I will need to define cast locations (perhaps similar to DFO?) and understand the applicable area. I will also need to define time ranges and tidal-averaging, but for just getting a scheme to work, I will shorten the time domain, then deal with lowpass filtering (I think).

For the rest of the quarter, I'm still targeting getting a volume estimation scheme up and running using "casts" with LO output. Ideally, I will be able to apply this to DFO casts within a few weeks of getting it working with LO data.

---

### Issues/Questions:
1. See above discussion.

### Looking Ahead:
1. Find hypoxic gridcells - get "source of truth" hypoxic volume from LO output.
2. Figure out LO "casts" - start depth-based estimation scheme.
3. Concatenate/organize DFO data using nco tools.
4. Get Endnote up and running - lit. review + notetaking.

### Goals For This Week:
