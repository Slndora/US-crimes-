# Comprehensive Crime Report Analysis: Trends, Victimology, and Geographic Insights (2020-2024)
![alt text]()
# Objective 
The objective of this project is to analyze U.S. crime data from 2020-2024, focusing on trends in crime classification, victim demographics, geographic patterns, weapon usage, and case statuses. The goal is to uncover insights into crime dynamics, inform law enforcement strategies, and highlight areas for policy improvement and crime prevention.

## Table of Contents
- [Table of Contents](#table-of-contents)
- [Data Overview](#data-overview)
- [Analysis Goals](#analysis-goals)
- [Methodology](#methodology)
- [Technologies Used](#technologies-used)
- [Importing the data](#importing-the-data)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Dashboard](#dashboard)
- [Acknowledgments](#acknowledgments)

## Data Overview
- Core Crime Information
1) DR_NO: Unique identifier for each reported crime. 
2) Date Rptd: Date the crime was reported to law enforcement. 
3) DATE OCC: Date the crime occurred. 
4) TIME OCC: Time the crime occurred. 
5) AREA: Geographic area or precinct where the crime took place. 
6) AREA NAME: Descriptive name of the area. 
7) Rpt Dist No: Reporting district number. 
- Crime Classification
8) Part 1-2: Indicates whether the crime is a Part 1 (serious) or Part 2 (less serious) offense. 
9) Crm Cd: Crime code or classification number. 
10) Crm Cd Desc: Description of the crime code. 
11) Mocodes: Motivations or circumstances related to the crime. 
- Victim Information
12) Vict Age: Age of the victim. 
13) Vict Sex: Sex of the victim. 
14) Vict Descent: Racial or ethnic background of the victim. 
- Location and Context
15) Premis Cd: Premises code (e.g., residential, commercial). 
16) Premis Desc: Description of the premises. 
17) Weapon Used Cd: Code for the weapon used (if any). 
18) Weapon Desc: Description of the weapon. 
- Additional Information
19) Status: Current status of the case (e.g., open, closed). 
20) Status Desc: Description of the case status. 
21) Crm Cd 1, 2, 3, 4: Additional crime codes if applicable. 
22) LOCATION: General location of the crime. 
24) Cross Street: Intersection or nearby street. 
25) LAT, LON: Latitude and longitude coordinates of the crime location.

## Analysis Goals
1) Crime Trend Analysis
- Identify and track changes in crime rates over time.
- Examine the fluctuations in crime frequency, distinguishing between serious (Part 1) and less serious (Part 2) crimes, and observe temporal trends such as annual, seasonal, or monthly variations.
2)Geographic Crime Distribution
- Analyze the spatial distribution of crimes across different areas and precincts.
- Identify high-crime areas, such as crime hotspots, and determine if certain regions experience higher concentrations of particular crime types. Assess how crime rates vary by neighborhood or district.
3) Victim Demographics Analysis
- Understand the demographic characteristics of crime victims.
- Analyze the age, sex, and descent of crime victims to identify which groups are most vulnerable to specific types of crime and whether certain demographic groups are disproportionately impacted by particular offenses.
4) Weapon Usage in Crime
- Examine the relationship between weapon usage and crime severity.
-  Identify the prevalence and types of weapons involved in crimes, and assess whether crimes involving weapons are more likely to be classified as serious (Part 1) offenses. Understand how weapon usage impacts the nature and outcome of crimes.
5) Case Status and Resolution Rates
- Track the progress and outcomes of reported crimes.
- Analyze the status of crime cases (e.g., open, closed, under investigation) to assess the effectiveness and efficiency of the criminal justice system. Identify trends in case resolution, and explore whether certain crime types have higher closure rates.
6) Crime Severity and Type Classification
- Compare the occurrence of different crime types based on severity.
- Examine the distribution of crime types (e.g., violent crimes vs. property crimes) and the number of incidents categorized as serious (Part 1) versus less serious (Part 2). This will provide insight into the overall safety landscape.
7) Crime Motivations and Circumstances
- Assess the relationship between crime location and premises type (e.g., residential, commercial).
- Analyze how different premises (residential, commercial, public spaces) are associated with different crime types, helping to identify vulnerabilities in specific types of locations and informing targeted prevention strategies.
8) Age-Group Specific Crime Patterns
- Investigate how different age groups are involved in falling victim to crime.
- Understand crime trends based on the age of victims. This could reveal whether youth, young adults, or older populations are more susceptible to being involved in certain crimes as victims.

## Methodology
- Data Cleaning & Preparation: Ensure data integrity and consistency.
- Descriptive Analysis: Generate summary statistics and visualizations to identify trends.
- Inferential Analysis: Apply statistical methods to test hypotheses and draw conclusions.
- Data Visualization: Utilize tools like Microsoft Excel to create interactive dashboards.

## Technologies Used
- I used Python for Exploratory Data Analysis (EDA) and data cleaning in this project. Python’s powerful libraries, such as Pandas, NumPy, and Matplotlib, were essential in handling and manipulating large datasets. I used Pandas to clean the data by addressing missing values, formatting date and time fields, and ensuring consistent data types. For EDA, I employed Matplotlib and Seaborn to visualize distributions, trends, and correlations within the data. Python allowed me to perform data transformations efficiently, calculate summary statistics, and prepare the dataset for deeper analysis, making it the backbone of the data preprocessing phase.
- I used Excel for data visualization and reporting to present the insights in an easily understandable format. Excel’s pivot tables were used to aggregate and summarize crime data across various dimensions, such as crime type, area, and victim demographics. I also utilized Excel’s charting tools to create visualizations, including bar charts, line graphs, and heat maps, to illustrate trends and patterns over time. Conditional formatting helped highlight key data points, such as high-crime areas. Finally, I designed a user-friendly dashboard in Excel to consolidate and present the most important findings for stakeholders and decision-makers.

## Importing the data
To begin the analysis, I imported the vehicle sales dataset from a CSV file into Python using the Pandas library. The pd.read_csv() function was used to load the dataset into a DataFrame, which allowed for efficient data manipulation, cleaning, and analysis. This step enabled me to explore and preprocess the dataset before performing any further visualizations.

```
import pandas as pd
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
import plotly.express as px
import plotly.graph_objects as go
import plotly.offline as pyo 
import plotly.io as pio
from plotly.offline import iplot
import warnings
warnings.filterwarnings("ignore")

df=pd.read_csv('C:/Users/akash/Downloads/.kaggle/Crime_Data_from_2020_to_Present.csv')
```
```
df.head()

DR_NO	Date Rptd	DATE OCC	TIME OCC	AREA	AREA NAME	Rpt Dist No	Part 1-2	Crm Cd	Crm Cd Desc	...	Status	Status Desc	Crm Cd 1	Crm Cd 2	Crm Cd 3	Crm Cd 4	LOCATION	Cross Street	LAT	LON
0	190326475	03/01/2020 12:00:00 AM	03/01/2020 12:00:00 AM	2130	7	Wilshire	784	1	510	VEHICLE - STOLEN	...	AA	Adult Arrest	510.0	998.0	NaN	NaN	1900 S LONGWOOD AV	NaN	34.0375	-118.3506
1	200106753	02/09/2020 12:00:00 AM	02/08/2020 12:00:00 AM	1800	1	Central	182	1	330	BURGLARY FROM VEHICLE	...	IC	Invest Cont	330.0	998.0	NaN	NaN	1000 S FLOWER ST	NaN	34.0444	-118.2628
2	200320258	11/11/2020 12:00:00 AM	11/04/2020 12:00:00 AM	1700	3	Southwest	356	1	480	BIKE - STOLEN	...	IC	Invest Cont	480.0	NaN	NaN	NaN	1400 W 37TH ST	NaN	34.0210	-118.3002
3	200907217	05/10/2023 12:00:00 AM	03/10/2020 12:00:00 AM	2037	9	Van Nuys	964	1	343	SHOPLIFTING-GRAND THEFT ($950.01 & OVER)	...	IC	Invest Cont	343.0	NaN	NaN	NaN	14000 RIVERSIDE DR	NaN	34.1576	-118.4387
4	220614831	08/18/2022 12:00:00 AM	08/17/2020 12:00:00 AM	1200	6	Hollywood	666	2	354	THEFT OF IDENTITY	...	IC	Invest Cont	354.0	NaN	NaN	NaN	1900 TRANSIENT	NaN	34.0944	-118.3277
5 rows × 28 columns
```
## Data overview
```
df.shape
(982638, 28)
```
```
df.columns
Index(['DR_NO', 'Date Rptd', 'DATE OCC', 'TIME OCC', 'AREA', 'AREA NAME',
       'Rpt Dist No', 'Part 1-2', 'Crm Cd', 'Crm Cd Desc', 'Mocodes',
       'Vict Age', 'Vict Sex', 'Vict Descent', 'Premis Cd', 'Premis Desc',
       'Weapon Used Cd', 'Weapon Desc', 'Status', 'Status Desc', 'Crm Cd 1',
       'Crm Cd 2', 'Crm Cd 3', 'Crm Cd 4', 'LOCATION', 'Cross Street', 'LAT',
       'LON'],
      dtype='object')
```
```
df.count()
DR_NO             982638
Date Rptd         982638
DATE OCC          982638
TIME OCC          982638
AREA              982638
AREA NAME         982638
Rpt Dist No       982638
Part 1-2          982638
Crm Cd            982638
Crm Cd Desc       982638
Mocodes           837376
Vict Age          982638
Vict Sex          844193
Vict Descent      844182
Premis Cd         982624
Premis Desc       982053
Weapon Used Cd    326167
Weapon Desc       326167
Status            982637
Status Desc       982638
Crm Cd 1          982627
Crm Cd 2           68875
Crm Cd 3            2311
Crm Cd 4              64
LOCATION          982638
Cross Street      151849
LAT               982638
LON               982638
dtype: int64
```
```
df.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 982638 entries, 0 to 982637
Data columns (total 28 columns):
 #   Column          Non-Null Count   Dtype  
---  ------          --------------   -----  
 0   DR_NO           982638 non-null  int64  
 1   Date Rptd       982638 non-null  object 
 2   DATE OCC        982638 non-null  object 
 3   TIME OCC        982638 non-null  int64  
 4   AREA            982638 non-null  int64  
 5   AREA NAME       982638 non-null  object 
 6   Rpt Dist No     982638 non-null  int64  
 7   Part 1-2        982638 non-null  int64  
 8   Crm Cd          982638 non-null  int64  
 9   Crm Cd Desc     982638 non-null  object 
 10  Mocodes         837376 non-null  object 
 11  Vict Age        982638 non-null  int64  
 12  Vict Sex        844193 non-null  object 
 13  Vict Descent    844182 non-null  object 
 14  Premis Cd       982624 non-null  float64
 15  Premis Desc     982053 non-null  object 
 16  Weapon Used Cd  326167 non-null  float64
 17  Weapon Desc     326167 non-null  object 
 18  Status          982637 non-null  object 
 19  Status Desc     982638 non-null  object 
 20  Crm Cd 1        982627 non-null  float64
 21  Crm Cd 2        68875 non-null   float64
 22  Crm Cd 3        2311 non-null    float64
 23  Crm Cd 4        64 non-null      float64
 24  LOCATION        982638 non-null  object 
 25  Cross Street    151849 non-null  object 
 26  LAT             982638 non-null  float64
 27  LON             982638 non-null  float64
dtypes: float64(8), int64(7), object(13)
memory usage: 209.9+ MB
```
```
df.describe()
DR_NO	TIME OCC	AREA	Rpt Dist No	Part 1-2	Crm Cd	Vict Age	Premis Cd	Weapon Used Cd	Crm Cd 1	Crm Cd 2	Crm Cd 3	Crm Cd 4	LAT	LON
count	9.826380e+05	982638.000000	982638.000000	982638.000000	982638.000000	982638.000000	982638.000000	982624.000000	326167.000000	982627.000000	68875.000000	2311.000000	64.00000	982638.000000	982638.000000
mean	2.197437e+08	1338.945426	10.700277	1116.459887	1.404253	500.823555	29.079817	306.133008	363.840882	500.578668	958.167085	984.204673	991.21875	33.995725	-118.082225
std	1.294954e+07	651.537830	6.107808	610.893787	0.490747	206.211940	21.970094	219.053795	123.684663	206.010361	110.232109	51.485644	27.06985	1.636729	5.672940
min	8.170000e+02	1.000000	1.000000	101.000000	1.000000	110.000000	-4.000000	101.000000	101.000000	110.000000	210.000000	310.000000	821.00000	0.000000	-118.667600
25%	2.106089e+08	900.000000	5.000000	587.000000	1.000000	331.000000	0.000000	101.000000	311.000000	331.000000	998.000000	998.000000	998.00000	34.014600	-118.430500
50%	2.208146e+08	1420.000000	11.000000	1141.000000	1.000000	442.000000	30.000000	203.000000	400.000000	442.000000	998.000000	998.000000	998.00000	34.058900	-118.322500
75%	2.309153e+08	1900.000000	16.000000	1617.000000	2.000000	626.000000	44.000000	501.000000	400.000000	626.000000	998.000000	998.000000	998.00000	34.164900	-118.273900
max	2.499253e+08	2359.000000	21.000000	2199.000000	2.000000	956.000000	120.000000	976.000000	516.000000	956.000000	999.000000	999.000000	999.00000	34.334300	0.000000
```
```
df.columns = df.columns.str.strip().str.lower()
```
# Data Cleaning

```
#Dataframe summary

def summary(df):
    print(f'data shape: {df.shape}')
    summ = pd.DataFrame(df.dtypes, columns=['Data Type'])
    summ['Missing#'] = df.isna().sum()
    summ['Missing%'] = (df.isna().sum())/len(df)
    summ['Dups'] = df.duplicated().sum()
    summ['Uniques'] = df.nunique().values
    summ['Count'] = df.count().values
    desc = pd.DataFrame(df.describe(include='all').transpose())
    summ['Min'] = desc['min'].values
    summ['Max'] = desc['max'].values
    summ['Average'] = desc['mean'].values
    summ['Standard Deviation'] = desc['std'].values
    summ['First Value'] = df.loc[0].values
    summ['Second Value'] = df.loc[1].values
    summ['Third Value'] = df.loc[2].values

    display(summ)

summary(df)
data shape: (982638, 28)
Data Type	Missing#	Missing%	Dups	Uniques	Count	Min	Max	Average	Standard Deviation	First Value	Second Value	Third Value
dr_no	int64	0	0.000000	0	982638	982638	817.0	249925282.0	219743659.495798	12949544.834652	190326475	200106753	200320258
date rptd	object	0	0.000000	0	1735	982638	NaN	NaN	NaN	NaN	03/01/2020 12:00:00 AM	02/09/2020 12:00:00 AM	11/11/2020 12:00:00 AM
date occ	object	0	0.000000	0	1735	982638	NaN	NaN	NaN	NaN	03/01/2020 12:00:00 AM	02/08/2020 12:00:00 AM	11/04/2020 12:00:00 AM
time occ	int64	0	0.000000	0	1439	982638	1.0	2359.0	1338.945426	651.53783	2130	1800	1700
area	int64	0	0.000000	0	21	982638	1.0	21.0	10.700277	6.107808	7	1	3
area name	object	0	0.000000	0	21	982638	NaN	NaN	NaN	NaN	Wilshire	Central	Southwest
rpt dist no	int64	0	0.000000	0	1209	982638	101.0	2199.0	1116.459887	610.893787	784	182	356
part 1-2	int64	0	0.000000	0	2	982638	1.0	2.0	1.404253	0.490747	1	1	1
crm cd	int64	0	0.000000	0	140	982638	110.0	956.0	500.823555	206.21194	510	330	480
crm cd desc	object	0	0.000000	0	140	982638	NaN	NaN	NaN	NaN	VEHICLE - STOLEN	BURGLARY FROM VEHICLE	BIKE - STOLEN
mocodes	object	145262	0.147829	0	309364	837376	NaN	NaN	NaN	NaN	NaN	1822 1402 0344	0344 1251
vict age	int64	0	0.000000	0	104	982638	-4.0	120.0	29.079817	21.970094	0	47	19
vict sex	object	138445	0.140891	0	5	844193	NaN	NaN	NaN	NaN	M	M	X
vict descent	object	138456	0.140902	0	20	844182	NaN	NaN	NaN	NaN	O	O	X
premis cd	float64	14	0.000014	0	314	982624	101.0	976.0	306.133008	219.053795	101.0	128.0	502.0
premis desc	object	585	0.000595	0	306	982053	NaN	NaN	NaN	NaN	STREET	BUS STOP/LAYOVER (ALSO QUERY 124)	MULTI-UNIT DWELLING (APARTMENT, DUPLEX, ETC)
weapon used cd	float64	656471	0.668070	0	79	326167	101.0	516.0	363.840882	123.684663	NaN	NaN	NaN
weapon desc	object	656471	0.668070	0	79	326167	NaN	NaN	NaN	NaN	NaN	NaN	NaN
status	object	1	0.000001	0	6	982637	NaN	NaN	NaN	NaN	AA	IC	IC
status desc	object	0	0.000000	0	6	982638	NaN	NaN	NaN	NaN	Adult Arrest	Invest Cont	Invest Cont
crm cd 1	float64	11	0.000011	0	142	982627	110.0	956.0	500.578668	206.010361	510.0	330.0	480.0
crm cd 2	float64	913763	0.929908	0	126	68875	210.0	999.0	958.167085	110.232109	998.0	998.0	NaN
crm cd 3	float64	980327	0.997648	0	37	2311	310.0	999.0	984.204673	51.485644	NaN	NaN	NaN
crm cd 4	float64	982574	0.999935	0	6	64	821.0	999.0	991.21875	27.06985	NaN	NaN	NaN
location	object	0	0.000000	0	66265	982638	NaN	NaN	NaN	NaN	1900 S LONGWOOD AV	1000 S FLOWER ST	1400 W 37TH ST
cross street	object	830789	0.845468	0	10326	151849	NaN	NaN	NaN	NaN	NaN	NaN	NaN
lat	float64	0	0.000000	0	5424	982638	0.0	34.3343	33.995725	1.636729	34.0375	34.0444	34.021
lon	float64	0	0.000000	0	4980	982638	-118.6676	0.0	-118.082225	5.67294	-118.3506	-118.2628	-118.3002

# There are some records with missing or null values in the dataset, which may need to be cleaned or imputed. However, there are no duplicate rows—every row in the dataset is unique.
```
```
df.drop(columns=['crm cd 2', 'crm cd 3','crm cd 4'], inplace=True)
```
## Dealing with date data
```
#Convert the date column to datetime
df['date rptd'] = pd.to_datetime(df['date rptd'], errors='coerce')
df['date rptd'] = df['date rptd'].dt.strftime('%d %m %Y %H:%M:%S')

df['date occ'] = pd.to_datetime(df['date occ'], errors='coerce')
df['date occ'] = df['date occ'].dt.strftime('%d %m %Y %H:%M:%S')
```
```
df.head()
dr_no	date rptd	date occ	time occ	area	area name	rpt dist no	part 1-2	crm cd	crm cd desc	...	status	status desc	crm cd 1	crm cd 2	crm cd 3	crm cd 4	location	cross street	lat	lon
0	190326475	01 03 2020 00:00:00	01 03 2020 00:00:00	2130	7	Wilshire	784	1	510	VEHICLE - STOLEN	...	AA	Adult Arrest	510.0	998.0	NaN	NaN	1900 S LONGWOOD AV	NaN	34.0375	-118.3506
1	200106753	09 02 2020 00:00:00	08 02 2020 00:00:00	1800	1	Central	182	1	330	BURGLARY FROM VEHICLE	...	IC	Invest Cont	330.0	998.0	NaN	NaN	1000 S FLOWER ST	NaN	34.0444	-118.2628
2	200320258	11 11 2020 00:00:00	04 11 2020 00:00:00	1700	3	Southwest	356	1	480	BIKE - STOLEN	...	IC	Invest Cont	480.0	NaN	NaN	NaN	1400 W 37TH ST	NaN	34.0210	-118.3002
3	200907217	10 05 2023 00:00:00	10 03 2020 00:00:00	2037	9	Van Nuys	964	1	343	SHOPLIFTING-GRAND THEFT ($950.01 & OVER)	...	IC	Invest Cont	343.0	NaN	NaN	NaN	14000 RIVERSIDE DR	NaN	34.1576	-118.4387
4	220614831	18 08 2022 00:00:00	17 08 2020 00:00:00	1200	6	Hollywood	666	2	354	THEFT OF IDENTITY	...	IC	Invest Cont	354.0	NaN	NaN	NaN	1900 TRANSIENT	NaN	34.0944	-118.3277
5 rows × 28 columns
```
```
df['vict sex'].unique()
array(['M', 'X', 'F', nan, 'H', '-'], dtype=object)
```
```
# Let's delete data with "-"
mask = (df['vict sex'] == '-')
df = df.loc[~mask]
df['vict descent'].unique()
array(['O', 'X', 'H', 'B', 'W', nan, 'A', 'K', 'C', 'J', 'F', 'I', 'V',
       'S', 'P', 'Z', 'G', 'U', 'D', 'L', '-'], dtype=object)
```
```
# Let's delete data with "-"
mask = (df['vict descent'] == '-')
```
```
df = df.loc[~mask]
# Create 'date' column with only year and month.
df['date'] = pd.to_datetime(df['date occ'],format='mixed')
df['date'] = df['date'].astype(str)
df['date'] = df['date'].str[:7]
```
```
# Put the Dataset in chronological order.
df = df.sort_values(by='date')
```
```
df.head()
dr_no	date rptd	date occ	time occ	area	area name	rpt dist no	part 1-2	crm cd	crm cd desc	...	status desc	crm cd 1	crm cd 2	crm cd 3	crm cd 4	location	cross street	lat	lon	date
0	190326475	01 03 2020 00:00:00	01 03 2020 00:00:00	2130	7	Wilshire	784	1	510	VEHICLE - STOLEN	...	Adult Arrest	510.0	998.0	NaN	NaN	1900 S LONGWOOD AV	NaN	34.0375	-118.3506	2020-01
138771	211806087	10 02 2021 00:00:00	01 11 2020 00:00:00	1300	18	Southeast	1832	2	763	STALKING	...	Invest Cont	763.0	NaN	NaN	NaN	100 W 108TH ST	NaN	33.9401	-118.2761	2020-01
102652	201704985	25 01 2020 00:00:00	25 01 2020 00:00:00	1100	17	Devonshire	1752	1	440	THEFT PLAIN - PETTY ($950 & UNDER)	...	Invest Cont	440.0	NaN	NaN	NaN	9900 DE SOTO AV	NaN	34.2500	-118.5886	2020-01
72848	200905443	02 02 2020 00:00:00	23 01 2020 00:00:00	1100	9	Van Nuys	955	1	440	THEFT PLAIN - PETTY ($950 & UNDER)	...	Invest Cont	440.0	NaN	NaN	NaN	5200 TILDEN AV	NaN	34.1649	-118.4475	2020-01
173898	201805426	27 01 2020 00:00:00	27 01 2020 00:00:00	30	18	Southeast	1862	2	740	VANDALISM - FELONY ($400 & OVER, ALL CHURCH VA...	...	Adult Arrest	740.0	NaN	NaN	NaN	IMPERIAL HY	BROADWAY	33.9310	-118.2791	2020-01
5 rows × 29 columns
```
```
def grab_col_names(dataframe, cat_th=10, car_th=30):
    
    # cat_cols, cat_but_car
    cat_cols = [col for col in dataframe.columns if dataframe[col].dtypes == "O"]
    del cat_cols[1] 
    num_but_cat = [col for col in dataframe.columns if dataframe[col].nunique() < cat_th and dataframe[col].dtypes != "O"]
    cat_but_car = [col for col in dataframe.columns if dataframe[col].nunique() > car_th and dataframe[col].dtypes == "O"]
    cat_cols = cat_cols + num_but_cat
    cat_cols = [col for col in cat_cols if col not in cat_but_car]

    # num_cols
    num_cols = [col for col in dataframe.columns if dataframe[col].dtypes != "O"]
    num_cols = [col for col in num_cols if col not in num_but_cat]

    print(f"Observations: {dataframe.shape[0]}")
    print(f"Variables: {dataframe.shape[1]}")
    print(f'cat_cols: {len(cat_cols)}')
    print(f'num_cols: {len(num_cols)}')
    print(f'cat_but_car: {len(cat_but_car)}')
    print(f'num_but_cat: {len(num_but_cat)}')

    return cat_cols, num_cols, cat_but_car


cat_cols, num_cols, cat_but_car = grab_col_names(df)
Observations: 982636
Variables: 29
cat_cols: 7
num_cols: 13
cat_but_car: 9
num_but_cat: 2
```
```
df.to_csv('cleaned_crime_data.csv', index=False)
```
## Exploratory Data Analysis
## Categorical Columns
```
def cat_summary(dataframe, col_name, plot=False):
    print(pd.DataFrame({col_name: dataframe[col_name].value_counts(),
                        "Ratio": 100 * dataframe[col_name].value_counts() / len(dataframe)}))

    if plot:
        fig, axs = plt.subplots(1, 2, figsize=(10, 4))
        plt.subplot(1, 2, 1)
        sns.countplot(x=dataframe[col_name], data=dataframe, palette = "Set1")
        plt.title("Frequency of " + col_name)
        plt.xticks(rotation=90)

        plt.subplot(1, 2, 2)
        values = dataframe[col_name].value_counts()
        plt.pie(x=values, labels=values.index, autopct=lambda p: '{:.2f}% ({:.0f})'.format(p, p/100 * sum(values)))
        hole = plt.Circle((0, 0), 0.40, facecolor='white')
        plt.gcf().gca().add_artist(hole)        
        plt.title("Frequency of " + col_name)
        plt.legend(labels=['{} - {:.2f}%'.format(index, value/sum(values)*100) for index, value in zip(values.index, values)],
                   loc='upper center', bbox_to_anchor=(0.5, -0.2), fancybox=True, shadow=True, ncol=1)
        plt.show(block=True)

for col in cat_cols:
    cat_summary(df, col, True)
```
![alt text]()

## Numerical Columns
```
def num_summary(dataframe, numerical_col, plot=False):
    if plot:
            fig, axs = plt.subplots(1, 2, figsize=(10, 4))
            plt.subplot(1, 2, 1)
            dataframe[numerical_col].hist(bins=50, color = "#900C3F")
            plt.xlabel(numerical_col)
            plt.title(numerical_col)

            plt.subplot(1, 2, 2)
            sns.boxplot(y=numerical_col, data=dataframe, color = "#900C3F")
            plt.title("Frequency of " + numerical_col)
            plt.xticks(rotation=90)

            plt.show(block=True)      

            print("______________________________________________________\n")

for col in num_cols:
    print(col)
    num_summary(df, col, plot=True)
```
![alt text]()







