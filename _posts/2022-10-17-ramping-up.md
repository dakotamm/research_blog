## Ramping Up

### Goals for Last Week:
1. Copy LO_data/obs/dfo to local and LO/obs/dfo to LO_user/obs/dfo.
2. Run test code and start understanding pandas as data processing tool.

### Completed Goals:
1. Copy LO_data/obs/dfo to local and LO/obs/dfo to LO_user/obs/dfo.
2. Run test code and start understanding pandas as data processing tool.

This week, I've been getting set up to try and test data loading and plotting DFO data. Largely, it's been helpful to continue to learn the LO framework and how to work between machines and with Github. I've been able to reproduce a few plots of CTD/bottle samples from DFO SQL data bases for various years.

The following are plots from the existing bottle and CTD cast plotting scripts. Figures 1 & 2 are for the default year 2017. Figures 3 & 4 are for 2014. Figure 5 is bottle samples from 2001 (no CTD data exists that year in the dataframe).

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm-private/blob/main/research-blog/2022-10-17/2017_ctd.png?raw=true" width="600"/><br>Fig 1. DFO CTD data from 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm-private/blob/main/research-blog/2022-10-17/2017_bottle.png?raw=true" width="600"/><br>Fig 2. DFO bottle data from 2017.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm-private/blob/main/research-blog/2022-10-17/2014_ctd.png?raw=true" width="600"/><br>Fig 3. DFO CTD data from 2014.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm-private/blob/main/research-blog/2022-10-17/2014_bottle.png?raw=true" width="600"/><br>Fig 4. DFO bottle data from 2014.</p><br>

<p style="text-align:center;"><img src="https://github.com/dakotamm/dakotamm-private/blob/4101c67f7fa214441639a538c0a49944feadb148/research-blog/2022-10-17/2001_bottle.png" width="600"/><br>Fig 5. DFO bottle data from 2001.</p><br>

###Issues/Questions
1. I ran into a bug in the GSW Python packages having to do with ufunc. It seems to be a known pandas issue (but hasn't yet been resolved in whatever we are getting from GSW). More info is here: https://github.com/pandas-dev/pandas/issues/39853

###Looking Ahead
1. Continue to familiarize myself with pandas/general python/LO - I got "Python for Data Analysis"!
2. Review SQL (I've used it before but it's been awhile).
3. Work on 1-pager for KC review meeting (incorporate Baltic Sea examples of direction from Science of Salish Sea workshop) - FYI I won't be able to attend the meeting given YCSECA conference! :(
4. Work on academic year plan for review.
