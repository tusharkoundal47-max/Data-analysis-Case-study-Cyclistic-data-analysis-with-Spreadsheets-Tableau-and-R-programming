# Data analysis Case study : Cyclistic data analysis with Spreadsheets Tableau and R programming
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
6 Act

The following notebook conveys my approach to analysing data for the case study which  explores the business problem of a hypothetical bike-sharing service named Cyclistic.

# Scenario
         
You are a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your recommendations, so they must be backed up with compelling data insights and professional data visualizations.

## Background
    
 Cyclistic has grown into a fleet of 5,824 bicycles that are geo-tracked and locked into a network of 692 stations across Chicago over the years since 2016. The bikes can be unlocked from one station and returned to any other station in the system anytime.

```R


```
# Ask (1st phase)

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
# Prepare (2nd phase)

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

### Installing and loading tidyverse packages in R posit cloud

```R
#Install and load tidyverse packages
install.packages("tidyverse")
```
Installing package into ‘/cloud/lib/x86_64-pc-linux-gnu-library/4.6’
(as ‘lib’ is unspecified)
also installing the dependencies ‘fastmap’, ‘sys’, ‘bit’, ‘ps’, ‘sass’, ‘digest’, ‘cachem’, ‘farver’, ‘labeling’, ‘RColorBrewer’, ‘viridisLite’, ‘rappdirs’, ‘rematch’, ‘askpass’, ‘base64enc’, ‘bit64’, ‘prettyunits’, ‘processx’, ‘evaluate’, ‘highr’, ‘xfun’, ‘yaml’, ‘bslib’, ‘fontawesome’, ‘htmltools��, ‘jquerylib’, ‘tinytex’, ‘backports’, ‘generics’, ‘glue’, ‘lifecycle’, ‘memoise’, ‘blob’, ‘DBI’, ‘R6’, ‘tidyselect’, ‘vctrs’, ‘withr’, ‘data.table’, ‘gtable’, ‘isoband’, ‘S7’, ‘scales’, ‘gargle’, ‘uuid’, ‘cellranger’, ‘curl’, ‘ids’, ‘rematch2’, ‘cpp11’, ‘pkgconfig’, ‘mime’, ‘openssl’, ‘timechange’, ‘utf8’, ‘systemfonts’, ‘textshaping’, ‘clipr’, ‘crayon’, ‘vroom’, ‘tzdb’, ‘progress’, ‘callr’, ‘fs’, ‘knitr’, ‘rmarkdown’, ‘selectr’, ‘stringi’, ‘broom’, ‘conflicted’, ‘cli’, ‘dbplyr’, ‘dplyr’, ‘dtplyr’, ‘forcats’, ‘ggplot2’, ‘googledrive’, ‘googlesheets4’, ‘haven’, ‘hms’, ‘httr’, ‘jsonlite’, ‘lubridate’, ‘magrittr’, ‘modelr’, ‘pillar’, ‘purrr’, ‘ragg’, ‘readr’, ‘readxl’, ‘reprex’, ‘rlang’, ‘rstudioapi’, ‘rvest’, ‘stringr’, ‘tibble’, ‘tidyr’, ‘xml2’
trying URL 'http://rspm/default/__linux__/noble/latest/src/contrib/fastmap_1.2.0.tar.gz'

#### Load the core tidyverse packages
```R
library("tidyverse")
```
The downloaded source packages are in
	‘/tmp/RtmpQoamUH/downloaded_packages’
library('tidyverse')
── Attaching core tidyverse packages ────────────────────────── tidyverse 2.0.0 ──
✔ dplyr     1.2.1     ✔ readr     2.2.0
✔ forcats   1.0.1     ✔ stringr   1.6.0
✔ ggplot2   4.0.3     ✔ tibble    3.3.1
✔ lubridate 1.9.5     ✔ tidyr     1.3.2
✔ purrr     1.2.2     
── Conflicts ──────────────────────────────────────────── tidyverse_conflicts() ──
✖ dplyr::filter() masks stats::filter()
✖ dplyr::lag()    masks stats::lag()
Use the conflicted package to force all conflicts to become errors


#### Importing dataset
#### uploaded dataset to posit cloud as csv file then imported in the project
```R
cydata525 <- read.csv("")
cydata625 <- read.csv("")
cydata725 <- read.csv("")
cydata825 <- read.csv("")
cydata925 <- read.csv("")
cydata1025 <- read.csv("")
cydata1125 <- read.csv("")
cydata1225 <- read.csv("")
cydata126 <- read.csv("")
cydata226 <- read.csv("")
cydata326 <- read.csv("")
cydata426 <- read.csv("")

# here i have named the cyclistic data files as cydata[myy] ie from May 2025 to April 2026
```


I also used the compiled dataset in posit R the step involved is as follows:

```R
Cyclisticdata <- read.csv("/cloud/project/divvy-tripdata6months.csv")
```

#### View the head (viewing the first 6 rows helps in verifying weather the data has been loaded correctly)
```R
head(Cyclisticdata)
```

      ride_id rideable_type              started_at                ended_at start_station_name start_station_id end_station_name end_station_id
1 9B9C7B1E3F4FC96C electric_bike 2026-04-13 14:47:32.170 2026-04-13 14:48:57.868                                                                    
2 8FE476DD539B3402 electric_bike 2026-04-13 09:56:56.062 2026-04-13 10:24:12.047                                                                    
3 CFA502A5FDC3E2D6 electric_bike 2026-04-13 08:33:39.927 2026-04-13 08:55:36.991                                                                    
4 AE6216BBF65C38AC electric_bike 2026-04-13 12:04:56.051 2026-04-13 12:31:00.820                                                                    
5 65C4A1F96AA07A5A electric_bike 2026-04-26 08:50:42.378 2026-04-26 08:56:44.514                                                                    
6 85DFEBC925D79F5C electric_bike 2026-04-26 12:42:25.222 2026-04-26 12:47:11.556                                                                    
  start_lat start_lng end_lat end_lng member_casual
1     41.96    -87.65   41.96  -87.65        member
2     41.91    -87.66   41.88  -87.63        member
3     41.96    -87.65   41.91  -87.66        member
4     41.88    -87.63   41.96  -87.65        member
5     41.93    -87.64   41.92  -87.64        member
6     41.94    -87.65   41.96  -87.65        member



### Dataset contains several variables consisting of qualitative and quantitative data, now using the 'glimpse' function, we can see the column names, column data types, and a list of the first few rows of the dataset.

```R
glimpse(Cyclisticdata)
```
Rows: 448,252
Columns: 14
$ ride_id            <chr> "9B9C7B1E3F4FC96C", "8FE476DD539B3402", "CFA502A5FDC3…
$ rideable_type      <chr> "electric_bike", "electric_bike", "electric_bike", "e…
$ started_at         <chr> "47:32.2", "56:56.1", "33:39.9", "04:56.1", "50:42.4"…
$ ended_at           <chr> "48:57.9", "24:12.0", "55:37.0", "31:00.8", "56:44.5"…
$ Trip_duration      <chr> "01:25.7", "27:16.0", "21:57.1", "26:04.8", "06:02.1"…
$ start_station_name <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ start_station_id   <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ end_station_name   <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ end_station_id     <chr> "", "", "", "", "", "", "", "", "", "", "", "", "", "…
$ start_lat          <dbl> 41.96, 41.91, 41.96, 41.88, 41.93, 41.94, 41.91, 41.9…
$ start_lng          <dbl> -87.65, -87.66, -87.65, -87.63, -87.64, -87.65, -87.6…
$ end_lat            <dbl> 41.96, 41.88, 41.91, 41.96, 41.92, 41.96, 41.90, 41.9…
$ end_lng            <dbl> -87.65, -87.63, -87.66, -87.65, -87.64, -87.65, -87.6…
$ member_casual      <chr> "member", "member", "member", "member", "member", "me…

### Data insights I gathered from previewing are: 
* Membership data type will help sorting and filtering data for comparing between casual and annual subscribers.
* The Trip duration column that I calculated earlier will help in analysing duration comparisons among members.
* Geographic data will help in finding trends for location which are more accessible to cyclists and where is potential market for next phase of company expansion.

```R



```

# Process (3rd phase)

###The guiding questions for this phase will be:
1. What tools should I choose and why?
2. Ensuring data is clean and data integrity is maintained.
3. Documenting the cleaning and manipulation process properly.

Merging the workbook files into one big csv file is the first step in creating a workable file. After compiling this data in one big single data frame

Now converting raw text into recognizable date-time format:

```R
Cyclistic_cleaned <-  Cyclisticdata %>%
  mutate(
    formatted_datetime = ymd_hms(started_at),

    separated_month = month(started_at), 
    
    separated_day = day(formatted_datetime)
  )
```

# View the final result
```R
print("Cleaned Dataset with Separated Columns:")
glimpse(Cyclistic_cleaned )
```

This notebook keeps track of data processing phase and now the dataset has been renamed as "Cyclistic_cleaned" which will render the processed dataset when queried.

```R



```

# Analyze (4th phase)

###The guiding questions for this phase will be:
1. Is the data properly formatted for this step to proceed?
2. What are visible trends and relationships I have found so far in this data??
3. Organise and format the data then proceed for trend analysis.

```R
usercount <- trips %>%
    group_by(user) %>%
    summarize(total = n()) %>%
    mutate(overall_total = sum(total)) %>%
    group_by(user) %>%
    summarize(percent_total = total/overall_total)

```
##### The query tells, 55.83% of the riders in past 12 months were annual subscribers and rest were casual riders.

```R
casual_member_biketype_used <- trips %>%
    filter(user == "casual") %>%
    group_by(bike) %>%
    summarize(total = n()) %>%
    mutate(overall_total = sum(total)) %>%
    group_by(bike) %>%
    summarize(percent_casual = total/overall_total)

```
##### The query suggests that Casual riders used classic bike for 61.3% of the times and used docked bikes the least for less than 15% of their usage combined



```R
riders_time_user <- trips %>%
    group_by(user) %>%
    summarize(avg_time = mean(ride_length), .groups = "drop")


riders_time_user$avg_time <- round(riders_time_user$avg_time , digits = 0)
```
##### This query returns average trip duration of casual users which is 28 minutes and annual subscribers ride for 13 minutes on average.

#### In conclusion it is found that casual riders spend twice as much time than annual members and also picks classic bikes for almost 62% of the time.


# Share (5th phase)

### These questions will guide this phase of analysis:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. How does findings relate to original questions and are they visually sharable?
3. Is the result accessible to stakeholders?

For this visualization I have used Tableau but R (posit cloud) itself can be utilized with its ggplot package.
To extract the csv file to be loaded on Tableau following step is to be used.

```R
write_csv(Cyclistic_cleaned, "cyclistic_cleaned.csv")
```

Sometimes it is hard to find the saved file so I used this command to find the file path.
```R
getwd()

#This helps display the address where file is saved by R console

```
The file itself can be shared too and be used for further visualization too.

## VISUALISATION RESULTS ARE AS FOLLOWS:


```R
library(ggplot2)
library(dplyr)
```

###### Aggregate:

```R
 hourly_trends <- trips %>%
+   # Force hour to be numeric and day_of_week to be a clean factor
+   mutate(
+     hour = as.numeric(as.character(hour)), 
+     day_of_week = factor(day_of_week, 
+                          levels = c("Monday", "Tuesday", "Wednesday", 
+                                     "Thursday", "Friday", "Saturday", "Sunday"))
+   ) %>%
+   group_by(day_of_week, hour, member_casual) %>%
+   summarise(ride_count = n(), .groups = 'drop')
```

###### Plotting
```R
ggplot(hourly_trends, aes(x = hour, y = ride_count, color = member_casual, group = member_casual)) +
+   geom_line(linewidth = 1.2) +
+   geom_point(alpha = 0.6) +
+   facet_wrap(~day_of_week, ncol = 4) + 
+   scale_color_manual(values = c("member" = "#2C3E50", "casual" = "#E74C3C")) +
+   # Continuous breaks from 0 to 23 hours
+   scale_x_continuous(breaks = seq(0, 23, by = 4)) +
+   theme_minimal(base_size = 14) +
+   labs(
+     title = "Hourly Bike-Share Usage Patterns",
+     subtitle = "Comparing Members vs. Casual Riders Across the Week",
+     x = "Hour of Day (24h format)",
+     y = "Number of Rides",
+     color = "User Type"
+   ) +
+   theme(
+     legend.position = "top",
+     strip.background = element_rect(fill = "#F0F3F4", color = NA),
+     strip.text = element_text(face = "bold"),
+     panel.grid.minor = element_blank()
+   )
```
For rest of the visualisations I am not attaching a log code block to keep this notebook clean, The "Logs" section has been assigned for the redundant code blocks for plotting the data.

# Visual Outputs:

#### Casual riders and Annual riders' riding behaviour/ usage patterns throughout the day. 
![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F32908132%2F4ca2a3bdb87e6fa86470b485400fa9b9%2Fride%20over%20day%20casualp.png?generation=1779097488369013&alt=media)


![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F32908132%2F35a4b3ff8a9737418010bf01c9ec93f0%2FRides%20over%20day%20annual%20membspp.png?generation=1779098282949169&alt=media)
.

#### Riders' Composition in the dataset.
![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F32908132%2Fb89e8ba393778256eb7fa3289e902abf%2Foverall%20piep.png?generation=1779098476355868&alt=media)
.
#### Bike preference Classic over Electric
![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F32908132%2F5fcae4ce4b8447821af534a095f8a83b%2Favg%20time%20spntd.png?generation=1779098765249371&alt=media)

.
#### Ride duration Casual VS Annual members
![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F32908132%2F80649b0df4e63d8dc0f64be4a55133d2%2Fride%20duration%20p.png?generation=1779098917774521&alt=media)



.
#### Trends in weekly usage patterns of the riders
![](https://www.googleapis.com/download/storage/v1/b/kaggle-user-content/o/inbox%2F32908132%2F4c06a48ed968a7748fcd4e1ff0570904%2Fusage%20ptrn.png?generation=1779098982318598&alt=media)
.

# Act (6th phase)

### The guiding questions for this phase will be:
1. What is the final verdict?
2. What are visible trends how are these insights helpful?
3. Any next steps that I may think of in order to meet the collective goal of stakeholders.


#                FINAL VERDICT
#### From the analysis performed on the data provided, I have the following recommendations:

## Have an advertising campaign focusing casual riders during the summer months.
## Increasing reach by strategies such as free trial schemes, discounted memberships for the casual riders.
## Advertising to the casual riders about how much they can save if they were annual members, this can be done by personalised messages, banner campaigns on cycle stations and social media ads.
## Including a reward system for the members that use the service on a daily basis, by giving them streak rewards.
## Incentivizing the Cyclistic service users both the members as well as casual riders with lucky draw coupons, this will attract other commuters to try out cyclistic services.
