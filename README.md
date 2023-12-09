# LIS706_Wisconsin-Homicide

Authors: Sveta Bartholomew and Aimee Tobin
Date: 12-09-2023

Files:
Data_Exploration.ipynb - initial data exploration and cleaning and encoding of the data
Modeling.ipynb - Spliting the data into training, testing, and hold out. Baseleine model, Regression model, Decision Tree model

Link to the .pdf on the whole report:

Background:

The model will predict if a Firearm is used or not in committing a homicide in Wisconsin based on the data during the years 2000-2021. The dataset we chose to focus on is sourced from the Murder Accountability Project (MAP) and contains our country’s unsolved homicides. The entire data set is for the entire United States and the years 1976 through 2021. 
We plan to create models to predict the type of weapon used in a homicide based on variables like victim and offender demographics, location, and circumstances. With the focus on a type of weapon prediction model, then the “Weapon” variable would be a “class variable.” Also, based on the correlation map that we produced; it seems that a weapon’s choice is a very significant detail in murder prediction. 
Background information on the dataset:
The Murder Accountability Project is the most complete database of homicides in the United States currently available. The project was founded by Thomas K. Hargrove, a retired Washington, D.C., -based investigative journalist and former White House correspondent. Based on recent statistics, every year, around 5,000 killers get away with their crimes. Sadly, the rate at which police clear homicides through arrest has declined over the years until, today, nearly half of these homicides go unsolved. MAP is dedicated to educating people on the importance of accurately accounting for unsolved homicides within the United States. 
This dataset includes murders from the FBI's Supplementary Homicide Report from 1976 to 2021 and Freedom of Information Act data on more than 33,000 homicides that were not reported to the Justice Department. This dataset includes the age, race, sex, ethnicity of victims and perpetrators, in addition to the relationship between the victim and perpetrator and weapon used. 

Description:

In the original dataset, there are 31 variables and 849,144 cases that cover unsolved homicides from 1976 to 2021. Many of these variables will not be included in the final dataset for machine learning algorithms, as either being redundant or having too many missing values. Out of these instances, 250,790 cases are unsolved and have only the victims’ demographics and place and year when the homicide was perpetrated. So, after all the cleaning we ended up with 3657 rows. We will describe the clearing steps that have been followed later in the paper.

Data attributes and description: 
The list of columns in the dataset are, 'County', 'Solved', 'Year', 'Month', 'VicAge', 'VicSex', 'VicRace', 'OffAge', 'OffSex', 'OffRace', 'Firearm', 'Murder'.

Name, Data Type, Max Value, Min Value, Mean, Number of instances

County, Nominal, Most frequent is Milwaukee, Least frequent is Richland
Solved, Nominal data type “Boolean” attribute, 1, 0, 0.998, 1=3649, 0=8
Year, Numeric/Interval, 2021, 2000, 2011
Month, Numeric/Interval, 12, 1, 7
VicAge, Ratio data type but put in ranges becomes ordinal, 0, 97, 32
VicSex, Nominal, M=Male F=Female U=Unknown
VicRace, Nominal, Black White Native American Unknown
OffAge, Ratio data type but put in ranges becomes ordinal, 8, 99, 30
OffSex, Nominal, M=Male F=Female U=Unknown
OffRace, Nominal, Black White Native American Unknown
Firearm, Nominal data type “Boolean” attribute,  1, 0, 0.622, 1=2273 0=1384
Murder, Nominal data type “Boolean” attribute, 1, 0, 0.916, 1=3351 0=306


State (state of the Originating Agency making the report), 
Solved (if the homicide is solved now), 
Year (Year of homicide), 
Month (Month name),
Homicide (type of homicide), 
VicAge (victim’s age), VicSex (victim's gender), VicRace, VicEthinicy, 
OffAge (offender’s age), OffSex (offender’s gender), OffRace, OffEthnicity, 
Weapon (the weapon used in the crime), 
Relationship (relationship between the victim and the offender, if any), 
Circumstance (the circumstances (or theory) for the crime), 


After running the first couple of models, we realized that “Relationship” and “Circumstance” columns are not as important as other factors, and we chose to remove them to make a more agile model.
