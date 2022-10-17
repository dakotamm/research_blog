## Ramping Up

### Goals for Last Week:
1. Copy LO_data/obs/dfo to local and LO/obs/dfo to LO_user/obs/dfo.
2. Run test code and start understanding pandas as data processing tool.
3. Read Fennel et al. 2022 paper to start to understand OBMs.

### Completed Goals:
1. Copy LO_data/obs/dfo to local and LO/obs/dfo to LO_user/obs/dfo.
2. Run test code and start understanding pandas as data processing tool.
3. 3. Read Fennel et al. 2022 paper to start to understand OBMs.

This week, I've been getting set up to try and test data loading and plotting DFO data. Largely, it's been helpful to continue to learn the LO framework and how to work between machines and with Github. I've been able to reproduce a few plots of CTD/bottle samples from DFO SQL data bases for various years.

The following are plots from the existing bottle and CTD cast plotting scripts. Figures 1 & 2 are for the default year 2017. Figures 3 & 4 are for 2014. Figure 5 is bottle samples from 2001 (no CTD data exists that year in the dataframe).

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/196265758-fef4c328-88d4-4b93-a22a-316d9cfe0636.png" width="600"/><br>Fig 1. DFO CTD data from 2017.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/196265828-4eb38969-a18f-46ee-b720-0cfa8c82b36b.png" width="600"/><br>Fig 2. DFO bottle data from 2017.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/196265943-12708589-6066-46b0-b7f1-102c181d97fa.png" width="600"/><br>Fig 3. DFO CTD data from 2014.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/196266007-195e53a6-7e22-4c0a-81b8-dbb3992db72a.png" width="600"/><br>Fig 4. DFO bottle data from 2014.</p><br>

<p style="text-align:center;"><img src="https://user-images.githubusercontent.com/55995675/196266083-e4aaf292-61f9-4308-8122-a92f40f03e9f.png" width="600"/><br>Fig 5. DFO bottle data from 2001.</p><br>

### Issues/Questions:
1. I ran into a bug in the GSW Python packages having to do with ufunc. It seems to be a known pandas issue (but hasn't yet been resolved in whatever we are getting from GSW). This specifically presents itself in the LO_data/obs/dfo scripts, but not in the LO/obs/dfo scripts. More info is here: https://github.com/pandas-dev/pandas/issues/39853

### Looking Ahead:
1. Continue to familiarize myself with pandas/general python/LO - I got "Python for Data Analysis"!
2. Review SQL (I've used it before but it's been awhile).
3. Work on 1-pager for KC review meeting (incorporate Baltic Sea examples of direction from Science of Salish Sea workshop) - FYI I won't be able to attend the meeting given YCSECA conference! :(
4. Review Ben's Jupiter Notebook with various data sources.
5. Work on academic year plan for review.

### Goals For Next Week:
For discussion in group meeting.

