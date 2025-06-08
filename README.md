 Project Title
# Tracking-Atmospheric-CO-A-Historical-Analysis-of-Emission-Trends-1958-2016-
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


