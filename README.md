# Nick-Sierra.Excel.Cyclistic

## Quick Links:
### Data: [divvy_tripdata](https://divvy-tripdata.s3.amazonaws.com/index.html)

## Introduction
This case study is part of the Google Data Analytics Professional Certificate program. As part of the Capstone Project, the following objective is to be completed. 

## Objective
You work for Cyclistic, a bike-share company based in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Your
team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will
design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve your
recommendations, so your recomendations must be backed up with compelling data insights and visualizations.


## Tools used in Analysis
- Data Cleaning & Analysis: Microsoft Excel 
- Visualization: Tableau Public

  ## Lets Use the 6 Data Analysis Phases
### Ask Phase:
To address the business task of understanding how annual members and casual riders use Cyclistic bikes differently, lets ask some questions to guide our analysis:

- Percentage of Casual Riders vs Annual Members
- Proportion of Rides by Bike Type
- Total Rides by Day of Week 
- Average Ride Duration by Member Type (in minutes) 
- Average Ride Duration by Day (in minutes)
- Frequency of Rides per Hour
  
### Prepare Phase:
- The dataset used for this project is publicly available and provided by Motivate International Inc. This project will focus on data from February of 2022.
- The original dataset contains 13 columns with 115,610 rows related to individual bike rides. 
- Each column provides detailed information about each ride, including:
    - ride_id, rideable_type, Started_weekday (added), started_at, started_time, ended_at, ended_time, ride_length, start_station_name, start_station_id, end_station_name, returned_to_original_station (added), end_station_id, member_type

### Process Phase:
#### Data Cleaning and Transformation in Excel:

During the process phase, the data cleaning steps were carried out in [Microsoft Excel](https://github.com/Tayyaba-Abro/Case-Study-Cyclistic-Bike-Share-Analysis/tree/main/Excel-clean-data). The following actions were performed: 
- **Checking for Duplicates:** Using Excel's built in function "remove duplicates" and the worksheets unique identifier, ride_id, no duplicates were found. This helped validate the data's integrity.
- **Validating Column Values:** rideable_type and member_casual were verified for errors through the filter function, none identified. 
- **Removing Blank Values:** Incomplete and blank values across all columns were assesed for viability. Blanks were removed from Start_station_name (17,708) and end_station_id (7,851), to ensure data completeness.
- **Removing Unused Columns:** Columns start_lat, start_lng, end_lat, and end_lng, were not relevant to the analysis and removed to streamline the dataset and focus on the essential variables.
- **Removing Data:** Rides less than 30 seconds (958), and rides greater than 24 hours (14), were removed.   
- **Adding the Started_Weekday Column:** A new column named "started_weekday" was added to to include the day of the week the ride was taken. The formula WEEKDAY(D2,1) was used, along with find and replace for the digits with the day of the week.  
- **Adding the Ride_Length Column:** A new column named “ride_length” was added to calculate the duration of each ride. Text to Columns > Fixed width > Short Date was used to separate the date from the time. The value in the ride_length column was obtained by subtracting the started_at timestamp from the ended_at timestamp.
- **Setting the Time Format:** Changed ride_length column format “HH:MM:SS” using the Format > Cells > Time > 37:30:55 option in Excel. This ensured that the ride duration was presented in a standardized time format.
- **Applying Conditional Formatting:** Conditional formatting was applied to the ride_length column to highlight ride lengths that fell outside the standard range. Specifically, any ride length values less than 00:01:00 (one minute) or greater than 24:00:00 (24 hours) were formatted differently, making them easily identifiable for further analysis or potential removal.
- **Sorting the Table:** The table was sorted in ascending order based on the started_at column to ensure data consistency.
By cleaning data in Excel, the dataset was refined, inconsistencies were addressed, and the ride length information was formatted appropriately for subsequent analysis.


### Analyze Phase:
During the Analyze phase, our objective is to explore the dataset thoroughly, revealing valuable insights and addressing significant discoveries pertaining to the distinct usage patterns of Cyclistic bikes by annual members and casual riders. Our primary emphasis lies in comprehending their behavior, preferences, and trends, with the ultimate goal of informing marketing strategies aimed at converting casual riders into annual members. To tackle the critical findings, a series of analyses were conducted using Microsoft Excel. 

#### 1. Percentage of Casual Riders vs Annual Members

![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/2ce7a88b-707c-45cd-831b-0a87a42b34e8)

#### 2. Proportion of Rides by Bike Type 

![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/6269b124-2ca3-400b-8b3e-29448be214b3)

#### 3. Number of Riders per Weekday and Percentage of Membership type

![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/4c297c51-0bab-4141-b1fc-4447ad83d942)

#### 5. Average Ride Duration by Day (in minute)

![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/5574bb42-4828-46d9-b138-139f736bb762)


### Share Phase:
In the Share phase, we showcase the insights and discoveries obtained through the examination of Cyclistic Bike Share data using Tableau Public, a robust data visualization tool. The analysis uncovered a multitude of significant findings, including:

#### 1. Percentage of Casual Riders vs Annual Members
In February of 2022, annual members accounted for the majority of the rides, representing 82.97% of the total 88,206 rides.
![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/52808587-4a66-4493-b779-0d933880d634)


#### 2. Proportion of Rides by Bike Type
The analysis of bike types reveals that annual members have a higher percentage of using classic bikes compared to casual riders. Additionally, annual members show a greater preference for electric bikes compared to casual riders. However, when it comes to docked bikes, casual riders demonstrate a higher inclination towards using them compared to annual members.

![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/a6e9e400-0741-402b-811c-e6d35fe4d659)


#### 3. Percentage of Rides per Weekday  
This analysis reveals that casual riders are more common on weekends, specifically Sunday. We also see Monday with the highest overall volume, reaching 20% of the total weekly rides. We also see a large rise in rides taken on Monday, with a gradual decrease throughout the week. 

![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/051a7690-78e6-4e9b-bfc6-f11c52a43d18)


#### 4. Average Ride Duration by Day (in minutes)
On average, casual riders have significantly longer ride durations compared to annual members.
![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/097ebcd1-5ef7-421f-978d-ceaf95ad9584)


#### 5. Frequency of Rides per Hour
The line graph illustrates distinct variations in the frequency of rides per hour for both annual members and casual riders. Notably, both rider type experience peak usage at 17:00 (5 p.m.), with annual members recording 273,000 rides and casual riders with 167,000 rides during that hour.
![image](https://github.com/Nick-Sierra/Nick-Sierra.Excel.Cyclistic/assets/149681943/f3bc84bd-e449-4e8e-99f1-d60dc061dfb8)


### Act Phase:
#### Key Takeaways: 
Based on my analysis, we've uncovered some valuable insights:

- **Bike Type Preference:** Annual members exhibit a strong preference for classic and electric bikes, whereas casual riders lean more towards docked bikes.
- **Daily Variation:** Annual members consistently outperform casual riders in terms of ride frequency across all days. Notably, Monday stands out with a high proportion of annual members, while Saturday and Sunday see an influx of casual rides.
- **Weekday vs. Weekend Usage:** Weekdays are prime riding days for annual members, while casual riders tend to favor weekends.
- **Ride Duration:** Casual riders typically engage in longer rides compared to annual members.
- **Peak Usage Hour:** BBoth groups peak at 5 p.m., but annual members log more rides during this time.
- **Time of day Trends:** Annual members predominantly ride during morning, afternoon, and evening hours, whereas casual riders make up the night crowd.

#### Strategies to convert more Casual Riders into Annual Member

- **Targeted Promotions:** Implement exclusive discounts and incentives to motivate casual riders to transition into annual memberships, emphasizing the long-term cost savings and benefits.
- **Diverse Bike Selection:** Expand the bike fleet to accommodate the preferences of casual riders, particularly classic and electric bikes, enhancing the overall riding experience.
- **Tailored Membership Plans:** Create specialized annual membership plans tailored to docked bike users, offering additional perks and incentives to encourage their shift.
- **Strategic Marketing:** Launch focused marketing campaigns during peak hours, weekends, and seasonal peaks to highlight the advantages of annual membership and its value for casual riders.
- **Enhanced Convenience:** Improve bike storage facilities, especially on weekends, to facilitate extended rides for casual riders and enhance overall convenience, making annual membership more appealing.
