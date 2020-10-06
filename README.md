# Score-Predictor
Built Score Predictor using few Regression models to predict scores for each MLB team.

# Problem Statement:
### NFL, MLB, NBA and Soccer scores
1. Set up a data science project structure in a new git repository in your GitHub account
2. Pick one of the game data sets depending your sports preference
https://github.com/fivethirtyeight/nfl-elo-game
https://github.com/fivethirtyeight/data/tree/master/mlb-elo
https://github.com/fivethirtyeight/data/tree/master/nba-carmelo
https://github.com/fivethirtyeight/data/tree/master/soccer-spi
3. Load the data set into panda data frames
4. Formulate one or two ideas on how feature engineering would help the data set to establish additional value using exploratory data analysis
5. Build one or more regression models to determine the scores for each team using the other columns as features
6. Document your process and results
7. Commit your notebook, source code, visualizations and other supporting files to the git repository in GitHub


# Data Description
## We are using Major League Baseball dataset from:
- https://github.com/fivethirtyeight/data/tree/master/mlb-elo

Column | Description
-----| ---------
date | Date of game
season | Year of season
neutral | Whether game was on a neutral site
playoff | Whether game was in playoffs, and the playoff round if so
team1 | Abbreviation for home team
team2 | Abbreviation for away team
elo1_pre | Home team's Elo rating before the game
elo2_pre | Away team's Elo rating before the game
elo_prob1 | Home team's probability of winning according to Elo ratings
elo_prob2 | Away team's probability of winning according to Elo ratings
elo1_post | Home team's Elo rating after the game
elo2_post | Away team's Elo rating after the game
rating1_pre | Home team's rating before the game
rating2_pre | Away team's rating before the game
pitcher1 | Name of home starting pitcher
pitcher2 | Name of away starting pitcher
pitcher1_rgs | Home starting pitcher's rolling game score before the game
pitcher2_rgs | Away starting pitcher's rolling game score before the game
pitcher1_adj | Home starting pitcher's adjustment to their team's rating
pitcher2_adj | Away starting pitcher's adjustment to their team's rating
rating_prob1 | Home team's probability of winning according to team ratings and starting pitchers
rating_prob2 | Away team's probability of winning according to team ratings and starting pitchers
rating1_post | Home team's rating after the game
rating2_post | Away team's rating after the game
score1 | Home team's score
score2 | Away team's score

## What we want to do?
- Use few Regression models to design a score predictor.
## Analysis of data and Feature Engineering
- We have transformed features, encoded categorical features, dropped unwanted features, treated missing values and removed incorrect data samples
---
## Results of Score Predictor models:
### R2-Score
- The coefficient R^2 is defined as (1 - u/v), where u is the residual sum of squares ((y_true - y_pred) ** 2).sum() and v is the total sum of squares ((y_true - y_true.mean()) ** 2).sum(). The best possible score is 1.0 and it can be negative (because the model can be arbitrarily worse). A constant model that always predicts the expected value of y, disregarding the input features, would get a R^2 score of 0.0.
#### R2 Score of Linear Regression is: 0.4240506279421571
#### R2 Score of Random Forest Regression is: 0.47225396605815206
#### R2 Score of Gradient Boosting Regression is: 0.5133224383841308
#### R2 Score of Multi-layer Perceptron regressor is: -0.9707093295210745

### Mean Squared Error:
- In statistics, the mean squared error (MSE) or mean squared deviation (MSD) of an estimator (of a procedure for estimating an unobserved quantity) measures the average of the squares of the errors—that is, the average squared difference between the estimated values and the actual value.

![](https://github.com/SFLazarus/Score-Predictor/blob/main/reports/mse_comparison.png)

### Mean Absolute Error:
- In statistics, mean absolute error (MAE) is a measure of errors between paired observations expressing the same phenomenon. Examples of Y versus X include comparisons of predicted versus observed, subsequent time versus initial time, and one technique of measurement versus an alternative technique of measurement.

![](https://github.com/SFLazarus/Score-Predictor/blob/main/reports/mae_comparison.png)

---
## Observations:
- We can say that Gradient Boost Regressor performed better than all others
- Although Neural Network(MLP) performed the worst, by tuning parameters we can make neural network to work better than all others. This is clear indication of over-fitting as we have left all parameters to default values.
## Conclusion and Future Developments:
- We could achieve quite good performance even without understanding lot about how these features actually worked.
- If we could understand how all the features affect score in-depth then we could make our models to predict much more accurately.
- we can also work a bit on Neural Network model by tuning parameters to achieve best results.
---

# Project Structure:
### Readme.md
- Project description
### Data
- Contains link to download dataset.
### Notebooks
- Jupyter Notebook for Exploratory data analysis, Visualization, Feature Engineering and Clustering.
### Reports
- plot- Comparing Mean Squared Error for each model -mse_comparison.png
- Plot- Comparing Mean Absolute Error for each model -mae_comparison.png
### Requirements.txt
- Info about Tools, frameworks and libraries required to reproduce the work flow
