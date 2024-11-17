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
- [Data Manipulation](#data-manipulation)
- [SQL for Data Insights](#sQL-for-data-insights)
- [Insights Generated with SQL Queries](#insights-generated-with-sQL-queries)
- [Measures in Power BI](#measures-in-power-bI)
- [Dashboard](#dashboard)
- [Acknowledgments](#acknowledgments)

## Data Overview
Core Crime Information
1) DR_NO: Unique identifier for each reported crime. 
2) Date Rptd: Date the crime was reported to law enforcement. 
3) DATE OCC: Date the crime occurred. 
4) TIME OCC: Time the crime occurred. 
5) AREA: Geographic area or precinct where the crime took place. 
6) AREA NAME: Descriptive name of the area. 
7) Rpt Dist No: Reporting district number. 
Crime Classification
8) Part 1-2: Indicates whether the crime is a Part 1 (serious) or Part 2 (less serious) offense. 
9) Crm Cd: Crime code or classification number. 
10) Crm Cd Desc: Description of the crime code. 
11) Mocodes: Motivations or circumstances related to the crime. 
Victim Information
12) Vict Age: Age of the victim. 
13) Vict Sex: Sex of the victim. 
14) Vict Descent: Racial or ethnic background of the victim. 
Location and Context
15) Premis Cd: Premises code (e.g., residential, commercial). 
16) Premis Desc: Description of the premises. 
17) Weapon Used Cd: Code for the weapon used (if any). 
18) Weapon Desc: Description of the weapon. 
Additional Information
19) Status: Current status of the case (e.g., open, closed). 
20) Status Desc: Description of the case status. 
21) Crm Cd 1, 2, 3, 4: Additional crime codes if applicable. 
22) LOCATION: General location of the crime. 
24) Cross Street: Intersection or nearby street. 
25) LAT, LON: Latitude and longitude coordinates of the crime location. 
