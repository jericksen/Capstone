# Washington, DC Crime Analysis & Predictive Modeling

<img src="images/DC.png" width="850" height="400">

### Project Overview
The intent for this project is two-fold: 

- **Part One** - Involves exploratory data analysis of crime incidents throughout Washington, DC from July 2018 - 2019. The analysis will involve mappings of crime incidents within the city, crime volumes by certain time and day parameters, as well as crime incidents by geographical dimensions, i.e., DC Wards. 
 

- **Part Two** - Involves the classifying the type of crime that takes place given a number of feature variables. The DC Police Department recognizes instances of crime as one of the following classes:
     - Arson
     - Assault with A Dangerous Weapon
     - Burglary
     - Homicide
     - Motor Vehicle Theft
     - Robbery
     - Sex Abuse
     - Theft From Automobiles
     - Theft (Other)
The modeling portion will focus on identifying the best algorithm to classify the type of crime that took place. The problem we're trying to solve is whether or not a model can predict the type of crime with a reasonable accuracy score with the data provided by the DC police department. The implications of a successful model could feasibly assist the police department with allocating the appropriate resources as soon as as soon as a crime is to occur to reduce the

For both parts, we'll walk through the methods used for obtaining, cleaning, analyzing, conditioning, feature engineering, and modeling the data.

***
***

## Obtaining the Data

The crime data for this project was obtained through the Open Data DC platform maintained by the DC government: https://opendata.dc.gov. The particular dataset used is available for download via the following URL: https://opendata.dc.gov/datasets/crime-incidents-in-2019. 

Crime data was extracted for both 2018 and 2019. Both raw datasets can be found in the project repository titled: 'Crime_Incidents_in_2018.csv' & 'Crime_Incidents_in_2019.csv'.

***
***
## Data Cleaning
*The data cleaning steps are outlined in the accompanying jupyter notebook titled 'Capstone_EDA'.*

The data cleaning process was fairly straight forward as the datasets themselves are well kept. The 2018 dataset contained 33782 crime instances, while the 2019 dataset at the time of download contained 20620 crime instances.

The image below highlights the features contained within the crime datasets:

<img src="images/Features.png" width="700" height="400">

**Data Cleaning Highlights:**

- Features Removed: 
    - X', 'Y', 'CCN', 'BLOCK', 'XBLOCK', 'YBLOCK', 'ANC', 'PSA', BID', 'START_DATE', 'END_DATE'
- Features Split for Modeling Purposes (split by delimiters into individual features, i.e., 'DATE' --> 'DAY, 'MONTH, 'YEAR'): 
    - 'DATE', 'TIME'
- Features Added: 
    - 'COUNT' (for summing crime events), 'CITY' (for mapping purposes)
- Null Values Removed: 
    - The remaining dataset contained null values within some of the feature variables. The percentage of null values compared to the total dataset length was assessed and deemed insignificant enough to to remove these rows altogether: 
    - <img src="images/Percent_null_values.png" width="200" height="300">
