# Findings

Construction, a major industry in America. In itself supplies countless jobs, supports other industries such as manufacturing  and most times requires all levels of skilled labor.
Whether we are referring to a residential home building/renovations or commercial real estate and government contracting, money is being spent. The question I am researching is,
does an increase in total construction cost relate to a better economy for the citizen?


Using the [Federal Reserve Bank of St. Louis](https://fred.stlouisfed.org/) a nationally respected source of economic information.
I collected a number of API's 

### Independent Variable:
Total Construction [TTLCONS](https://fred.stlouisfed.org/series/TTLCONS) 

### Dependent Variables: 
Unemployment Rate [UNRATE](https://fred.stlouisfed.org/series/UNRATE) Consumer Price [CPIAUCSL](https://fred.stlouisfed.org/series/CPIAUCSL) US Regular Gas Price [GASREGM](https://fred.stlouisfed.org/series/GASREGw#)


Using the Pandas model in Python I created a Data Frame structuring the API's. In order to keep the data as balanced as possible, I used a structure with a reported value on the first of month for the time period 
01-01-1993 - 06-06-2026. The raw data in the DataFrame did vary numerical, taking logs of certain columns such as TTLCONS and CPIAUCSL helped to even things for further comparison.
`python df["log_TTLCONS"] = np.log(df["TTLCONS"])` The API itself also contained access dates which were removed as columns to keep the visual better for the viewer. 

<img width="762" height="267" alt="df head" src="https://github.com/user-attachments/assets/602e290d-dba5-453c-9d5a-8ececbc85725" />

In order to work with the large set of data we have, 5 sets of 2 year blocks were structured. This was decided based off the base chart provided by FRED. 

#### 94-96, 00-02, 06-08, 12-14, 20-22
It is important to note this was decided in a way that would highlight the early 2000's, housing market crash of 2008, and COVID. These specific events are factors that heavily effect the data when comparing to the economy as a whole, others variables not included in this study could also sway the study. 

### [Selected Points of Interest](FREDconstruction.png)


<img style="width: auto; max-width: 100%;" alt="lineplot" src="https://github.com/user-attachments/assets/ded56054-efa0-4880-9fea-f7a695d1a800" />
*This chart was created with the assistance of AI, model ChatGPT Free*

The chart above is a collection of line graphs analyzing our variables during the selected time periods of interest. The data was normalized by taking the highest value in each range and setting it at 1 while the lowest 
value is set at 0. This method allows us to visualize change over time across the different variables in the period. 

### Data Obervations
 - First its important to note that Total Construction Cost (log-TTLCONS) and Consumer Price Index (log_CPIAUSCL) throughout all five charts have a very similar change. This is dictated by construction spending increasing with an increase in CPI, however this does not mean a negative relationship for the economy as the research question is testing. The measure of CPI reported in this research does include information on energy cost and food which is emitted in other CPI models as these factors can be heavily swayed from outside mechanisms. For our research it is fitting to use this version as we are testing with a variable exclusive to gas prices as well.
 - This general steady rise in CPI is proof of a strengthening economy as supported by our construction cost and unemployment rate following the same rise while remaining low respectively. With the initial tanking of the housing market during the period 2006-2008 with construction spending dropping followed closely the next year with a decrease in CPI and severe spike in unemployment. Although this event is the worst economic disruption since the Great Depression we can use it as proof construction spending supports overall economic strength. Looking at the chart for 2012-2014 once spending started to recover we see a drop in unemployment with the same slight healthy rise in CPI referenced prior.
 - Finally to address outliers within the data, I highlight the seemingly high unemployment rate during the 2000-2002 as well as 2020-2022. Immediately the 2020 level is associated with COVID an outlier that was expected and gave reason to use this specific range. Despite this the rate of other variables remained relatively resistant, further supporting increase in spending. The 2000 level of unemployment is attributed to the "dot com" burst and fallout of the September 11th terrorist attacks, another point in which outside variables sway the data. 

<img style="width: auto; max-width: 100%;" alt="boxenplot" src="https://github.com/user-attachments/assets/4c152e6f-d621-4b14-bc93-5df8196e955c" />
*This chart was created with the assistance of AI, model ChatGPT Free*

The above chart is a collection of boxenplots graphing a single variable per chart. Each chart contains 5 instances respective to the corresponding time group on the x-axis. Chart is used for showing the raw grouping of each variables data over time without normalization. 

### Data Observations
- The Box plots above are used to highlight the spread of smaller samples of data in order to make the larger set more digestible. Data represented in the chart is raw, no values are normalized to make sure points of bias associated with manipulation could be countered. The first chart representing Total Construction Spending shows the trend referenced above, a slow increase in spending across the last two decades. To the right we see a chart with CPI data. Once again following the same trend addressed earlier a slow increase.
- Analyzing the specific points of interest such as the housing market crash of 2008 are visible within this visualization. Total Construction had a peak happen 2006-2008 followed by the overall spread starting lower four years later. Once again supporting the idea that increased Construction spending is good for the economy. Viewing the close grouping of all CPI intervals, visual proof of low variance shows that change has been constant and steady. Addressing the 2012-2014 section we see the smallest grouping in all the data, showing that low Constructing spending was holding the CPI steady while the economy stabilized  itself.
- Boxenplots help us with seeing places in which factors outside the scope of the study could be skewing the results. The variable for Gas Price is highlighted in how volatile the spread can be within this factor. During simple two year time groupings the price can change almost two+ dollars. Once again a previous point to consider becomes relevant, the CPI measure used in this study includes energy cost giving insight into why that number might be higher than other reported values.

### Limitations, Ethics, and Reflection
Most economic studies choose points of focus. This can pose a challenge when trying to address the idea of an entire country's economy. My study is not without these constraints either, for example certain historic economic disruptions that occurred during our points of interest. September 11th terrorist attacks, housing market crash of 2008, and the COVID pandemic are unavoidable factors that will skew data. As a researcher I needed to be aware of these facts addressing them as they become apparent. Looking at the conclusions drawn through the data collected and analyzed in this study I feel it leaves a question for a future researcher. Introduction of a potential variable looking at the price of finished products, either single family home or commercial real estate within the year groupings. Including a raw materials cost could be argued as well due to a higher bottomline resulting in increased cost. I feel that a better measure is total sale price, not only does this help in showing true profit for the economy but as a society cost is not the only thing we attribute  for valuation. 


[**Bibliography**](bibliography.md)

