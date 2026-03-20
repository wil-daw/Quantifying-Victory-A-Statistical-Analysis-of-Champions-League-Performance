# Quantifying Victory: A Statistical Analysis of Champions League Performance

This project analyzes historical UEFA Champions League club performance to identify which team-level factors are most strongly associated with winning success. Using statistical modeling and data visualization in R, the analysis explores how offensive and defensive performance relate to a club’s win/loss ratio.

## Project Overview

The UEFA Champions League is one of the most competitive club soccer tournaments in the world. This project investigates whether:

- scoring more goals per game increases a team’s success
- conceding fewer goals per game improves a team’s success
- offensive and defensive performance can help explain differences in club win/loss ratios

The goal is to quantify how strongly average goals scored and average goals conceded relate to a team’s historical success in Champions League play.

## Research Questions

This analysis focuses on questions such as:

- Do teams that score more goals per game tend to have higher win/loss ratios?
- Do teams that concede fewer goals per game tend to perform better?
- Which of offense or defense appears to have the stronger relationship with winning success?

## Dataset

The project uses historical Champions League data compiled from a sports statistics source. The primary dataset includes club-level records such as:

- Club
- Titles
- Games Played
- Wins
- Draws
- Losses
- Goals For
- Goals Against
- Goal Differential
- Points

From these variables, additional metrics were created for analysis:

- **WinLoss** = `Win / (Win + Loss)`
- **averageGoalsScored** = `Goals_For / Played`
- **averageGoalsConceded** = `Goals_Against / Played`

## Methods

The analysis was completed in **R** using:

- **tidyverse**
- **lubridate**
- **data.table**
- **readxl**
- **modelr**
- **ggplot2**
- simple **linear regression**

### Main steps:
1. Import historical club data from Excel
2. Create derived performance variables
3. Visualize relationships using scatterplots
4. Fit linear regression models
5. Interpret coefficients, test significance, and examine residuals

## Key Findings

The analysis finds that:

- Teams that score more goals per game tend to have a **higher win/loss ratio**
- Teams that concede more goals per game tend to have a **lower win/loss ratio**
- Offensive production shows a strong positive relationship with winning success
- Defensive weakness shows a strong negative relationship with winning success

### Regression Results

#### 1. Average Goals Scored vs Win/Loss Ratio
Estimated model:

WinLoss = 0.28726 × averageGoalsScored + 0.02522

Interpretation:
- A 1-goal increase in average goals scored per game is associated with an expected **28.7 percentage point increase** in win ratio

#### 2. Average Goals Conceded vs Win/Loss Ratio
Estimated model:

WinLoss = -0.127955 × averageGoalsConceded + 0.575292

Interpretation:
- A 1-goal increase in average goals conceded per game is associated with an expected **12.8 percentage point decrease** in win ratio

## Visualizations

The project includes:

- scatterplot of **average goals scored per game vs win/loss ratio**
- scatterplot of **average goals conceded per game vs win/loss ratio**
- residual plot for offensive model
- residual plot for defensive model

These visualizations help assess both the strength of the relationships and the fit of the regression models.

## Project Files

Typical files used in this project include:

- `qv_champions_league.Rmd` — main R Markdown analysis
- `AllTimeRankingByClub.xlsx` — input dataset
- generated plots and regression output within the knitted document

## How to Run

1. Clone the repository
2. Open the `.Rmd` file in RStudio
3. Install required packages if needed:
   ```r
   install.packages(c("tidyverse", "lubridate", "data.table", "readxl", "modelr"))
