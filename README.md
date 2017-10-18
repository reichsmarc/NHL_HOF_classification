# Project \#3 - # NHL Hall of Fame Classification #
--------
My third Metis project involved using clustering/supervised learning techniques to solve a binary or multi-class classification problem. As a lifelong hockey player and fan, I chose to use my new skills to classify which players in the National Hockey League will make the Hall of Fame, using the [Open Source Sports Hockey Database.](http://www.opensourcesports.com/hockey/)

### Data Overview ###
This data includes personal information and career statistics by season on all professional hockey players in each of the major leagues (WHA, PCHA, WCHL, NHA and NHL) from 1909 to 2011. Because we know which players have been inducted into the Hall of Fame since the end of the dataset in 2011, we have a natural holdout set on which to test our classifiers.

The dataset includes skaters (forwards and defensemen), goalies and coaches from both men's and women's leagues. I chose to focus on classifying only NHL skaters for my project, which makes this a binary classification: Hall of Fame (1) or non-Hall of Fame (0).

### Data Cleaning ###
The main challenge in terms of preparing the data for analysis was handling missing values. Because many players played during a time when the leagues did not track advanced statistics, there are many missing values. In addition, fewer than half of the players in each league make the playoffs each year, at which point scoring statistics restart and are tracked separately. 

To address these issues, I summarized playoff statistics as 'playoff series wins' and 'championship wins' and dropped the individual player statistics for the postseason. I also removed player records with no values for the most significant categories: Points, Assists, Goals, Games Played and Position. For the remaining sparsely populated features, including Powerplay Assists, Shorthanded Assists, and Game-Tying Goals, I filled missing values with zeroes as these are important indicators of player skill which were not tracked until the modern era; many players do not achieve points in these categories as these are special situations within a game, so zero is a reasonable average assumption.

### Feature Engineering ###
While the dataset allows one to easily compare all players in absolute value, I wanted to analyze how each player compared to his team and the rest of the league each season, and on average. I added percentile rank *vs. Team* and *vs. League* features for Goals, Assists, Points, +/- and Shots on Goal to capture these comparisons.

I also included a feature which capture the player's country of birth as represented in the Hall of Fame.

### Code cleanup in progress. ###
***To Do:***
------------
1. Further modularize code into functions.
2. Combine ROC plots and improve visualization of distinction between classifiers.

***Future:***
-------------
1. Re-run analysis with [complete, official NHL data made available as of 9/27/17.](https://www.nhl.com/news/nhl-historical-stats-press-release/c-291394420)

