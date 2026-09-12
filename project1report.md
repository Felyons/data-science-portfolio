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
*This chart was created with assistance of AI, model ChatGPT Free*

