# Fantasy Football Webscraper and Data Aggregator

## Overview
The "FFBallWebScrape.ipynb" file contains seven different functions used to scrape, wrangle, and transform statistics from three different websites to input into a Google Sheet for weekly tracking purposes.

Link to google sheet: https://docs.google.com/spreadsheets/d/1PD-MFUa4zdcL-9qaW1fuJ9MFvG5hyOQTR3NzNYrc2jU/edit?usp=sharing

## Function Descriptions
Insert_row_
  - Description: Inserts new rows into existing dataframe
  - Arguments: Executed within prodata function
prodata(year, pids)
  - Description: Scrapes, cleans, and transforms statistics from Pro-Football-Reference website
  - Arguments: year (integer), pids (static file of unique player ids)
  - Additional Notes: Flags when a player has played for more than one team and will scrape information from individual player pages to have specific statistics fro all teams they've played for. The Insert_row_ function is used here.
weeklydata(year, start, end, pids)
  - Description: Scrapes and cleans weekly fantasy scores from the Fantasy Pros website
  - Arguments: year (integer), start (integer, week to start scrape), end (integer, week to end scrape), pids (static file of unique player ids)
intscrape(week, pids)
  - Description: Scrapes interception data from the Fantasy Pros website to bridge gape between Fantasy Pros weekly scores and ESPN scoring (-1 vs -2 per interception)
  - Arguments: week (integer, the most recent played week of the season), pids (static file of unique player ids)
ffballleague(id, yr, s2, sw, week, pids)
  - Description: Pulls fantasy football league data from ESPN API
  - Arguments: id (integer, unique league id found in the url), yr (integer, year of league), s2 (string, the espn_s2 key for the league), sw (string, the SWID of the league), week (integer, most recently played week), pids (static file of unique player ids)
  - Find espn_s2: espn_s2 key can be found using Chrome (on league page and logged in) -> Right-click page and Inspect -> Application -> find espn_s2 value
  - Find SWID: Chrome (on league page and logged in) -> Right-click page and Inspect -> Application -> find SWID value. MUST BE STRING IN CURLY ({}) BRACKETS
oppscrape(week, pids)
  - Description: Scrapes player statistics, aggregating "opportunities" per week. This includes pass attempts, rushing attempts, and targets
  - Arguments: week (integer, the most recently played week), pids (static file of unique player ids)
league_sim(id, yr, s2, sw)
  - Description: Simulates remaining schedule of league to provide each team's playoff probabilities 
  - Arguments: id (integer, unique league id found in the url), yr (integer, year of league), s2 (string, the espn_s2 key for the league), sw (string, the SWID of the league)
  - Find espn_s2: espn_s2 key can be found using Chrome (on league page and logged in) -> Right-click page and Inspect -> Application -> find espn_s2 value
  - Find SWID: Chrome (on league page and logged in) -> Right-click page and Inspect -> Application -> find SWID value. MUST BE STRING IN CURLY ({}) BRACKETS


## Google Sheet Description

