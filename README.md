# election_analysis
Supporting data and analysis for report "Analysis of Voting Anomalies in Several States". A PDF and DOCX version of the report are available in this repository at 

<a href="https://github.com/beckett76/election_analysis/raw/main/Analysis%20of%20Voting%20Anomalies%20in%20Several%20States.docx">DOCX</a>

<a href="https://github.com/beckett76/election_analysis/raw/main/Analysis%20of%20Voting%20Anomalies%20in%20Several%20States.pdf">PDF</a>

Excerpt from Intro Summary:

The 2020 US presidential election continues to be mired in controversy amid accusations of voter fraud. 
This report presents an examination of the voter data in six states from 2000-2020 with the goal of making an independent determination that these allegations are plausible. 
The conclusion of the analysis is that massive, systemic voter fraud is not ruled out due to strong, structured trends in differential voting statistics repeated 
across all states examined that do not appear (collectively) to have a natural demographic explanation. 

The clearest example is in the state of GA. The figure below shows differences in Republican presidential percentage point (pp) scores for each GA county between the 2004 and 2020 elections. 
(The label of blue or red is determined based on the county’s preference in 2008). 
The data are plotted against a log scale on the X axis by total number of votes in each county. The data for counties below 10k votes appear normal, 
but the data from counties with 10k-100k votes show a consistent decrease in Republican voting percentage with an almost perfect slope of 25pp/dec (logarithmic decade, not years). 
This means that (on a linear scale) the decrease in Republican votes follows the trend of a logarithmic curve with population size.

![Image_GA_2004_2020](https://github.com/beckett76/election_analysis/raw/main/GA_diff_2004_2020.png)

The remainder of this report shows that this large trend is due to separate trends of the same form but with smaller magnitude occurring in the differential data of the 2008, 2016, and 2020 elections. 
From the above figure, it appears that the metro Atlanta counties do not fit the stated trend, but it will be shown that in fact they are in family with the other counties when the difference in relative Republican leaning is accounted for (See Figure 14 in the report). 
Trends of the same form and similar magnitude occur in every other state examined in this report for the 2016 and 2020 election, and some for the 2008 election. The states chosen were FL, GA, NC, OH, PA, and VA. 
These states were chosen randomly by the author, although their choice was influenced by the fact that these are generally considered “swing” states politically and/or were reported to have other anomalies in the 2020 election.

In fact, the regularity of the trend and results leads the author to propose the following functional form for an algorithm that is consistent with the trends in the data. 
This algorithm is conjecture, however, performing its inverse on the data appears to yield results consistent with normal voting and demographic patterns. 
Therefore, it represents a reasonable “educated guess” as to a systemic process that could generate the observed anomalies.
If T_i is the number of total votes in a given county and R_i are the Republican votes, then the “missing” Republican votes in that county (ΔR_i) appear to follow the following equation

<img src="https://render.githubusercontent.com/render/math?math=\Delta{R_i} =  k \log_{10} (\frac{T_i}{T_0})"> for
<img src="https://render.githubusercontent.com/render/math?math=T_i>T_0">

and otherwise zero, where k is a slope parameter and T_0 the intercept (onset) parameter. 
For the data in the above figure, k=0.225 and T_0=10,000. 
If the effect of this equation is applied to the data in reverse, it yields the data in the second figure.

![Image_GA_fix_2004_2020](https://github.com/beckett76/election_analysis/raw/main/GA_diff_adj_2004_2020.png)

The data in the second figure are much more in line with what we would expect to see in a standard demographic analysis over time. 
There are clear clusters of Republican and Democratic voting patterns. The total number of votes in the adjustment is 610k.
Tables at the end of each analysis section in the report summarize the estimated impact of the anomalies if they are in fact due to artificial manipulation by the proposed algorithm. 
In multiple states, this analysis shows the potential for 100s of thousands to millions of switched votes based on this assumption.
Furthermore, a cursory analysis of the adjusted data sets shows that the proposed algorithm leads to corrections that appear resilient under leading digit analysis (Benford’s law).
