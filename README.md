# PowerBIprojects
This repository showcases all my Power BI projects where i dive into different datasets, visualizations, and insights.It's a growing collection of my hands-on work with dashbords and reports.
# Mumbai Indians IPL Stats Dashboard

### Dashboard Link : https://app.powerbi.com/groups/me/reports/52cbcf35-df2a-4e37-bb74-3511142f7603/5b432ed5d6a4765ecacb?experience=power-bi

## Problem Statement

This dashboard provides a detailed statistical analysis of the Mumbai Indians’ performance in the Indian Premier League (IPL). Using data collected from ESPN Cricinfo (https://stats.espncricinfo.com/), the dashboard covers batting, bowling, and fielding across seasons.

It helps stakeholders to:

Track season-wise and player-wise performance trends.

Compare batting, bowling and fielding efficiencies.

Assess win/loss performance across venues and opponents.

Identify key players contributing to team success.

Through these insights, the Mumbai Indians team management can take informed decisions on strategy, player rotation, and match preparation.


### Steps followed 

Step 1: Collected Mumbai Indians IPL data from ESPN Cricinfo for all seasons.

Step 2: Imported the data using web links into Power BI Desktop.

Step 3: Cleaned and transformed data in Power Query Editor:

Removed duplicates and blank rows.

Standardized player names and formats.

Converted text to numeric where applicable.

Handled null values for certain match stats (e.g., DNB - Did Not Bat, DNB - Did Not Bowl).

Step 4: Enabled “Column distribution”, “Column quality” & “Column profile” options in Power Query for data validation.

Step 5: Created calculated columns and measures in DAX for metrics like:

Batting → Runs, Strike Rate, Average, 4s, 6s.

Bowling → Wickets, Economy Rate, Bowling Average, Strike Rate.

Step 6: Added slicers for filtering by Season and Player Name.

Step 7: Added visualizations:

Player rankings for runs and wickets.

KPI cards for quick stats.

Step 8: Created custom measures and used visual-level filters to exclude null or irrelevant entries.

Step 9: Applied Mumbai Indians’ brand colors for thematic consistency.

Step 10: Published to Power BI Service for interactive use.
 

DAX Measures Created

1. Total Runs Scored
Total Runs = SUM(Batting[Runs])

2. Total Wickets Taken
Total Wickets = SUM(Bowling[Wickets])

3. Batting Strike Rate
Batting SR = 
DIVIDE(SUM(Batting[Runs]), SUM(Batting[Balls Faced])) * 100

4. Bowling Economy Rate
Economy Rate = 
DIVIDE(SUM(Bowling[Runs Conceded]), SUM(Bowling[Overs Bowled]))

5. Win Percentage
Win % = 
DIVIDE(
    CALCULATE(COUNTROWS(Matches), Matches[Result] = "Won"), 
    COUNTROWS(Matches)
) * 100

6. Boundaries Count
Total Boundaries = SUM(Batting[4s]) + SUM(Batting[6s])

7. Player Contribution Percentage
Contribution % = 
DIVIDE(
    SUM(Batting[Runs]), 
    CALCULATE(SUM(Batting[Runs]), ALL(Batting[Player Name]))
) * 100


Power BI Report Images

<img width="1919" height="1016" alt="Screenshot 2025-08-15 165737" src="https://github.com/user-attachments/assets/d7ee074e-84e2-47e1-a059-eb9356738c84" />

<img width="1919" height="1018" alt="Screenshot 2025-08-15 165802" src="https://github.com/user-attachments/assets/7f33771d-7087-444c-8809-1ff2b8052a59" />

<img width="1919" height="1014" alt="Screenshot 2025-08-15 165817" src="https://github.com/user-attachments/assets/212a2e01-3a4e-4210-9d2d-e1d64ca29c88" />

