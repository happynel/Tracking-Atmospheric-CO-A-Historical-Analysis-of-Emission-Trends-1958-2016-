 Project Title
# Tracking-Atmospheric-CO2-A-Historical-Analysis-of-Emission-Trends-1958-2016-
This data science research project investigates the long-term trends in atmospheric carbon dioxide (CO₂) concentrations from 1958 to 2016.


## Project Overview
This data science research project investigates the long-term trends in atmospheric carbon dioxide (CO₂) concentrations from 1958 to 2016.
Utilizing high-resolution time-series data from the Mauna Loa Observatory and other verified sources, the project explores the seasonal and annual patterns of CO₂ emissions over nearly six decades.
Through trend analysis and robust data visualization, the study provides compelling evidence of the accelerating rise in CO₂ levels driven by anthropogenic activity.
By presenting clear, data-backed insights into historical CO₂ emissions, this project aims to inform public discourse, support environmental advocacy, and encourage policy interventions for climate action.


### Objectives
- To analyze the trend of atmospheric CO₂ concentrations from 1958 to 2016.
- To quantify the annual growth rate in CO₂ levels.
- To communicate findings using visualizations that are accessible to both scientific and non-scientific audiences.

### Data Source
Mauna Loa Observatory CO₂ Data: Provided by NOAA [National Oceanic and Atmospheric Administration](https://gml.noaa.gov/ccgg/trends/)

### Methodology
 Loaded the data from a CSV file into a Pandas Dataframe
- Converted the data into time-series format for seasonal decomposition
- Handled missing values and smoothed data using rolling averages
- Visualized the data to uncover the trend in co2 emmision from 1958 to 2016.

### Data Pre-Processing
The dataset is provided by NOAA [National Oceanic and Atmospheric Administration](https://gml.noaa.gov/ccgg/trends/),  contains records of the change in climate in the last half a century or so. 

The data is in a CSV file called `climate_change` with three columns. 

- 1. The `"date"` column indicates when the recording was made and is stored in the year-month-date format.
     A measurement was taken on the 6th day of every month from 1958 until 2016. 
- 2. The  `"co2"` column contains measurements of the carbon dioxide in the atmosphere.
     The number shown in each row is parts-per-million of carbon dioxide. 
- 3. The  `"relative_temp"` column denotes the temperature measured at this date, relative to a baseline which is the average        temperature in the first ten years of measurements.
 
### Data Loading
__Task_1:__ Follow the appropriate steps in reading a CSV file into a pandas Dataframe, 
and  Read the data stored  in the csv file named:  `climate_change` From on your computer.
The resulting Dataframe should be named : `climate_change_df`

'''python
# solution 
import pandas as pd

climate_change_df = pd.read_csv("C:/Users/HP/Desktop/_EXCLUSIVE DATA SCIENCE BOOT CAMP_STUDENT FOLDER/_DATASET/climate_change.csv")

climate_change_df 
'''
![Data_Loading](https://github.com/user-attachments/assets/04797266-faa6-4d6f-b33b-5ee7997b8370)



###  Data Analysis
- **Time-Series Decomposition**: This was used to separate trend, seasonality, and residuals.

- **Visualization:** Created line plots,  seasonal subseries plots, and anomaly detection visuals using Python library (Matplotlib)

'''python
climate_change_df = pd.read_csv("C:/Users/HP/Desktop/_EXCLUSIVE DATA SCIENCE BOOT CAMP_STUDENT FOLDER/_DATASET/climate_change.csv", parse_dates = ["date"], index_col = "date")
climate_change_df.head()
'''
![Data_Analysis](https://github.com/user-attachments/assets/9f063b4f-4f26-41fb-894f-b9993303ea69)



###  Data Inspection(check for missing values)
'''python
climate_change_df.isna().any()
'''
![Data_Inspection](https://github.com/user-attachments/assets/c3c86107-3ec8-4467-9c0a-ddaae1675347)

## counting the number of missing values
'''python
climate_change_df.shape
climate_change_df.isna().sum()
'''
![Data_MissingValues](https://github.com/user-attachments/assets/2276cd73-5657-4ce4-8fe2-33ce58dba917)


### Data Cleaning (handling missing values)
'''python
climate_change_df.mode()

climate_change_df["co2"].mean()

# filling the missing value with the mean value 352.32 on the column
climate_change_df = climate_change_df.fillna(352.32)
climate_change_df.head()

# Checking if all Missing Values have been replaced by the Mean
climate_change_df.isna().any()
'''
![Data_Cleaning](https://github.com/user-attachments/assets/5134de45-3be9-4634-b8d7-08ae5d8fa87d)
![Data_Mean](https://github.com/user-attachments/assets/3a15318e-fc93-4212-ae8b-ec57aee9da8d)
![Data_Analysis3](https://github.com/user-attachments/assets/315d3571-e4e8-45bc-b037-3a59f86f3551)
![Data_Corr_Confirmation](https://github.com/user-attachments/assets/73d78712-381f-4c62-a345-a4b660d88a38)


### Data Visualization
'''python
#Solution

#Importing Matplotlib

import matplotlib.pyplot as plt


#Creating The Plot

fig, ax = plt.subplots()


ax.plot(climate_change_df.index, climate_change_df["co2"], color = "red")


ax.set_xlabel("Time")

ax.set_ylabel("co2(part per million)")

fig.suptitle("Co2 Emission Due to Climate Change")

plt.show()
'''
![Data_plot](https://github.com/user-attachments/assets/b1c0f8d2-032b-4e62-9c46-a9276d062d7b)


###  Data Interpretation
### Key Findings
-**Steady Increase**: CO₂ levels rose from approximately 315 ppm in 1958 to over 403 ppm by 2016.

-**Seasonal Patterns**: A regular saw-tooth pattern was observed, corresponding to seasonal plant activity (photosynthesis cycles).

-**Acceleration in Emissions**: Linear curve indicates steady growth and increasing acceleration in emissions, especially post-2000.

### Conclusion
-The findings of this study provide compelling evidence of the dramatic rise in atmospheric CO₂ over the last half-century.

-While natural seasonal variations exist, the long-term upward trend is unmistakably driven by industrialization, fossil fuel combustion, and land-use changes. 

-These results underscore the urgency for global climate mitigation strategies and support the scientific consensus on anthropogenic climate change.

### Recommendations
-I strongly reconmmend  the global adoption of renewable energy sources.

-I strongly reconmmend the Promotion of  global CO₂ emission monitoring for real-time policy response.

-I strongly reconmmend that this  findings should be used as part of educational material in environmental science curricula.

-I strongly reconmmend the Extension of this  study to include temperature anomaly data for correlation analysis.

## ------THE ENDS--------
