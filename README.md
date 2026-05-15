# Cyclistic-data-Project-Spreadsheets-and-R-programming-
Case study 1: How does a bike-share navigate speedy success? This is my practice project, that is part of the Google Data Analytics Professional Certificate helps convey my approach to analysing data.

Case Study cyclistic data

# Introduction
This case study have been done on the lines of Google Data analytics program under capstone project. The data used in this case study is sourced from Motivate International Inc under this license agreement.
 <https://divvybikes.com/data-license-agreement>
 #The steps involved my the data analysis process are: 
1 Ask
2 Prepare
3 Process
4 Analyse
5 Share
6 Act.

The following notebook conveys my approach to analysing data for the case study which  explores the business problem of a hypothetical bike-sharing service named Cyclistic.

#Scenario
         
You are a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## Background
    
 Cyclistic has grown into a fleet of 5,824 bicycles that are geo-tracked and locked into a network of 692 stations across Chicago over the years since 2016. The bikes can be unlocked from one station and returned to any other station in the system anytime.

```R


```
#Ask (1st phase)

###Three questions will guide the problem statement:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

### Approaching this phase:
*Business problem statement includes viewing the two types of subscribers i.e. Annual members and Casual riders and then analysing their usage patterns.
*Reason to why subscribers opt for annual memberships and what can trigger or accelerate this behaviour.
*How can we tweak the marketing strategy to make casual riders convert into annual subscribers.

After identification of Business tasks and considering the requirements of key stakeholders, gathering prerequisites for the task comes next. 


```r



```
#Prepare (2nd phase)

###These questions will guide the prepare step:
1. Status of data organisation and its location.
2. Are there any issues related to bias or credibility and data licencing?
3. What are problems with gathered data?

### Approaching this phase:
*Downloading the data and giving proper naming conventions to keep data organised and storing it appropriately.
*Taking a gist of what the data contains and how is it relevant for our problem statement.
*Sorting, filtering and combining the data.

The data used in this case study is publicly available with sharing license <https://divvybikes.com/data-license-agreement> , for the purpose of this study I have gathered data for past 12 months (May 2025 to April 2026) in 'csv' file format from this repository link <https://divvy-tripdata.s3.amazonaws.com/index.html>.

Then the data is first saved in appropriate folders with proper naming conventions and a backup of raw data is saved for future reference and other copy was utilized for processing purposes.

Processing involved deletion of redundant columns using spreadsheet program and then adding a column specifying "ride duration" by calculating difference between "Ride start at" and "Ride end at" times. The files were gathered in a single workbook and saved for further processing in Posit Cloud workspace where I used R programming language for further analysis.
