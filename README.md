# Cyclistic Customer Segmentation Analysis 🚲

## Objective:
- I am a junior data analyst working on the marketing analysis team at Cyclistic, a fictional bike-share
company in Chicago.
- The director of marketing believes the company’s future success
depends on maximizing the number of annual memberships.
- Therefore, the marketing team wants to
understand how casual riders and annual members use Cyclistic bikes differently. From these
insights, the team will design a new marketing strategy to convert casual riders into annual
members.
## Data Source :
The data sets provided through the project documentation include the Cyclistic Riders data  for the whole year (Jan - Dec) , 2023 .
## Tools  Used :
- Excel : used for data cleaning | Documentation for the data cleaning can be found here [Download the Documentation Here](https://docs.google.com/spreadsheets/d/1P44InQQkjKurzNW1CTrT7-MQ40wFVVPHCoCgiP5EOz8/edit?usp=sharing)
    - Handling Null Values
    - Inconsistent field values
- Python : _Jupyter Notebook_ used for data merging as datasets were too large to handle on normal databases

   _The following was the code  used to merge the datasets found in Full_Year file directory, which will then output a file named Full_Year.csv in the same directory_
```
import os
import pandas as pd
import csv

input_directory = '/path/Excel_Versions/Cleaned_CSVs/Full_Year'

merged_df = pd.DataFrame()
output_file = '/path/Full_Year/Full_Year.csv'
for file in os.listdir(input_directory):
    if file.endswith('.csv'):
        file_path = os.path.join(input_directory, file)
        df = pd.read_csv(file_path)
        merged_df = pd.concat([merged_df, df], ignore_index=True)

merged_df.to_csv(output_file, index = False)
```
- Tableau : used for data visualization | [To view the dashboard click here](https://public.tableau.com/views/CasualVsMemberBikeUsage/Casual_Vs_Member_Dashboard?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)

  - Notable Features :
      - Implemented the use of ``` WINDOW_MAX ``` function in the calculated fields section in order to aggregate already aggregated columns.
    
      - 
           Used Sheet Headers such as _Member_ and _Casual_ as clickable filters in the final dashboard.
      - Used  Sheet  Headers of Quarters as clickable headers for filtering with quarters.
---
## Exploratory Data Analysis ( EDA) 
### After conducting exploratory data analysis , the following _insights_ were deduced :
  ✅ Quarterly Trends: 
 - Summer (Q3) has the highest ridership among casual riders. 

  ✅ Weekend Preference: 
 - Casual riders peak on days 1 & 7 (weekends) in Q3, suggesting leisure-focused usage.

  ✅ Ride Percentages (Q3 Weekends):

- Casual riders: 38.9% of total Q3 rides occur on weekends (days 1 & 7).
- Annual members: Only 25.6% of Q3 rides are on weekends.
- Key gap: +13.3% difference in weekend usage.

 _Strategic Insight: This disparity highlights casual riders’ strong leisure preference, making weekends a prime target for membership conversion campaigns._


---
## Recommendations :
### Based on the analysis , the following  marketing strategies were recommended:-
- Marketing campaigns targeted at casual riders in the summer (Q3) such as :
    - Discounts on annual memberships. _%_

    - Extra perks when using the bikes while on a membership on weekends, (i.e. sharing membership with family members).
---
 ## Potential Results :-
  - Casual riders converting to annual memberships in Q3

  - Incentivizing the casual riders using their own behavior, which is riding more frequently on weekends, to convert to annual memberships would see a possible 13% increase in weekend rides made by annual members.

---
### Link to Canva Presentation : [View Canva Presentation](https://www.canva.com/design/DAGj-utIxW4/U42SXYctFp48TjZfveaIrw/edit?utm_content=DAGj-utIxW4&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
### Layout Inspired by :  [How to Document Data Analysis Project by Her Data Project](https://youtu.be/0N9xekdKCwk?feature=shared)

