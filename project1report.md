# Report

Construction, a major industry in America. In itself it supplies countless jobs, supports other industrys such as maufactoring and most times requires all types of skill labor.
Whether we are referring to a residential home building/renovations or commercial real estate and government contracting money is being spent. The question I am researching is,
does an increase in total construction cost relate to a better economy for the citizen?


Using the [Federal Reserve Bank of St. Louis](https://fred.stlouisfed.org/) a nationally respected source of economic information.
I collected a number of API's 

### Independent Variable:
Total Construction [TTLCONS](https://fred.stlouisfed.org/series/TTLCONS) 

### Dependent Variables: 
Unemployment Rate [UNRATE](https://fred.stlouisfed.org/series/UNRATE) Consumer Price [CPIAUCSL](https://fred.stlouisfed.org/series/CPIAUCSL) US Regular Gas Price [GASREGM](https://fred.stlouisfed.org/series/GASREGw#)


Using the Pandas model in Python I created a Data Frame structing the API's. In order to keep the data as balanced as possible, I used a structure with a reported value on the first of month for the time period 
01-01-1993 - 06-06-2026. The raw data in the DataFrame did very numerical heavily, taking logs of certain columns such as TTLCONS and CPIAUCSL helped to even things for further comparision.
`python df["log_TTLCONS"] = np.log(df["TTLCONS"])` The API itself also contained access dates which were removed as columns to keep viewer visual easier. 

<img width="762" height="267" alt="df head" src="https://github.com/user-attachments/assets/602e290d-dba5-453c-9d5a-8ececbc85725" />

In order to work with the large set of data we have, 5 sets of 2 year blocks are compared. This was decided based off the base chart provided by FRED. 

#### 94-96, 00-02, 06-08, 12-14, 20-22
It is important to note this was decided in a way that would highlight the early 2000's, housing market crash of 2008, and COVID. This specific events are factors that heavily effect our data when comparing to the economy as a whole, others variables not included in this study could sway our variables. 

### [Selected Points of Interest](FREDconstruction.png)


<img style="width: auto; max-width: 100%;" alt="lineplot" src="https://github.com/user-attachments/assets/ded56054-efa0-4880-9fea-f7a695d1a800" />
*This chart was created with the assistance of AI, model ChatGPT Free*

The chart above is a collection of line graphs analyzing our variables during the selected time periods of interest. The data was normalized by taking the highest value in each range and setting it at 1 while the lowest 
value is set at 0. This method allows us to visualize change over time across the different variables in the period. 

### Data Obervations
 - First its important to note that Total Construction Cost (log-TTLCONS) and Consumer Price Index (log_CPIAUSCL) throughout all five charts have very similar change. This is dictated by construction spending increasing with an increase in CPI, however this doesnt mean a negative relationship for the the economy as research question is asking. The measure of CPI reported in this research does include information on energy cost and food which is emmitted in other CPI models as those factors can be heavily swayed from outside mechanisms. For our research it is fitting to use this version as we are testing with a variable exclusive to gas prices as well.
 - This general steady rise in CPI is proof of a strengthing economy as supported by our construction cost and unemployment rate following the same rise while remaining low respectivily. With the initial tanking of the housing market during the period 2006-2008 with construction spending dropping followed during the next year with decrease in CPI and sever spike in unemployment. Although this event is the worst economic disruption since the Great Depression we can use it as proof construction spending supports overall economic strenght. Looking at the chart for 2012-2014 once spending started to increase again we see a drop in unemployment with the same slight healthy rise in CPI referenced prior.
 - Finally to address outliers within the data, I highlight the seemingly high unemployment rate during the 2000-2002 as well as 2020-2022. Immediately the 2020 level is associated with COVID an outlier that was expected and gave reason to use this specific range. Dispite this the rate our of other variables remained relativly resistant, further supporting increase in spending. The 2000 level of unemployment is attributed to the "dot com" burst and fallout of the September 11th terrorist attacks another point in which outside variables sway the data. 

