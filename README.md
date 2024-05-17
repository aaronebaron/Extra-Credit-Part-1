# Extra-Credit-Part-1

# Analyzing Home Court Advantage in a Post Pandemic NBA
   * Aaron Baron (ab9175)

## Description of Project
* "Analyzing Home Court in a Post Pandemic NBA" aims to delve into a breadth of data to assess the role that home court advantage played in the National Basketball Association (NBA) during its post-pandemic era. This application will uncover a comprehensive analysis of various metrics including team performance, player statistics, game outcomes, and fan attendance. By scrutinizing this data, we seek to uncover patterns and trends regarding the significance of home court advantage in seasons where occupancy limitations differed depending on the attendance restrictions put on different stadiums by their local state governments. This analysis will provide valuable insights into how factors such as crowd presence, travel fatigue, and venue familiarity impact game outcomes, thus contributing to a deeper understanding of the evolving dynamics within professional basketball.

## Data Sources
1. Primary Dataset (NBA Statistics):
   * Source/Link: Nathan Lauga's Kaggle Dataset, [NBA Games Data](https://www.kaggle.com/datasets/nathanlauga/nba-games)
   * Schema: The games.csv includes the game date, name of the home team, name of the away team, season number, and relevant statistics pertaining to the home team (including points, total assists, total rebounds, field goal percentage, 3 point percentage, etc.)
   * Description: The dataset contains comprehensive information on NBA games, including details such as game dates, teams involved, points scored, field goals made and attempted, and turnovers committed. It provides the necessary game-level data to analyze team performances both at home and away venues.
2. Secondary Dataset (NBA Attendance):
   * Source/Link: ESPN, [NBA Attendance Data](https://www.espn.com/nba/attendance/_/year/)
   * Schema: TEAM: String–Name of the NBA team, AVG: String–Team’s average attendance during specified season (shown both for home and road games).
   * Description: The dataset provides information on the average attendance of all 30 NBA teams, both at home and on the road, during the seasons following the coronavirus pandemic.

## Division of Responsibilities
* Aaron Baron worked with the NBA game/team/player dataset. He performed the data profiling, ETL (Extract, Transform, Load) tasks, data ingestion, and the analytics code to derive insights from the unified datasets.

## Steps

1. Profiling Code
   * ab9175 (Aaron Baron)
      * This file calculates and prints the total number of records and performs additional mapping to count records again. It also identifies and displays distinct values for each column.

2. ETL Code
   * ab9175 (Aaron Baron)
      * This file filters records by specific dates and transforms the 'SEASON_ID' column to a more readable format. It also removes unnecessary columns and writes the cleaned data back to a new CSV file.

3. Data Ingestion Code
   * In FirstCode.scala, the cleaned datasets were joined, and the mean, median, and mode of the numerical data were found. We also calculated the standard deviation of the win percentage column. Text formatting and binary column cleaning options were utilized by marking specific columns in all caps for normalization/future joining and by adding a column that would output “yes” or “no” to affirm whether a team had a winning record or not.

4. Analytics Code
   * In SecondCode.scala, the home and away records were converted to decimal format through a udf function to process them as analytics. We then pulled the columns of interest and cast their values to the proper data type (double). We calculated the correlations between:
      * HOME_RECORD_DECIMAL and AVG_HOME == 0.1400
      * HOME_RECORD_DECIMAL and PCT_HOME == 0.1472
      * ROAD_RECORD_DECIMAL and AVG_ROAD == -0.0460
      * ROAD_RECORD_DECIMAL and PCT_ROAD == -0.0416
   * Findings:
      * Home Record and Average Home Attendance: This positive correlation suggests that teams with higher average home attendance tend to have slightly better home records, although the correlation is relatively weak.
      * Home Record and Percentage Home Attendance: This also indicates a positive but weak relationship, implying that a higher percentage of filled capacity at home games slightly correlates with better home records.
      * Road Record and Average Road Attendance: This negative correlation is very weak, suggesting there is barely any relationship, if at all, between road records and the average road attendance.
      * Road Record and Percentage Road Attendance: Similar to the average road attendance, this also indicates a very weak negative correlation with the road record.

---
