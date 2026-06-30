# NASA-Stardance-26
A repository for all my NASA Stardance Projects, helping me track my progress while keeping everything under one roof

## **FIFA WC 26' Match Prediction Model**

This project focuses on building a match outcome predictor for the upcoming 2026 FIFA World Cup using a comprehensive historical dataset of international football results. The original dataset includes nearly fifty thousand records of men's full international matches played from 1872 up to 2025. To construct a reliable predictive framework, the data was restricted to matches played between 2018 and 2026. This temporal filtering minimizes the impact of long term rule changes and generational shifts in team compositions, ensuring that the historical trends remain highly relevant to modern international football.

The primary focus was placed on major competitive tournaments, including the FIFA World Cup, the UEFA Nations League, and the AFC Asian Cup. By filtering out friendly matches and low stakes competitions, the predictive models are trained specifically on environments where teams perform with maximum competitive intensity. The architecture of the project spans four key computational phases, which include data cleaning, advanced feature engineering, exploratory data analysis, and predictive machine learning modeling.


### Data Engineering and Feature Extraction

The core of the model's predictive power stems from feature engineering, which converts raw match results into dynamic mathematical indicators of team strength. A customized Elo rating system was implemented to dynamically track team qualities over time. Every team began with a baseline rating of 1500, and their points were adjusted after each match based on the actual result compared to their statistical win probability. Calculating these ratings sequentially based on the historical timeline prevents data leakage and ensures that the model only evaluates information available prior to the kickoff of each respective match.

Beyond structural Elo ratings, the pipeline extracts short term and medium term form factors using rolling windows of five and ten matches. These features capture the average points per game alongside a weighted momentum metric, which applies exponentially higher significance to the most recent match outcomes. This dual approach allows the system to evaluate both the foundational strength of a national team and its immediate competitive trajectory heading into a specific tournament fixture.


### Predictive Modeling and Simulations

A multinomial Logistic Regression model was developed to categorize match results directly into three distinct classes, which are home wins, draws, and away wins. To achieve a more granular understanding of match dynamics, a separate Poisson Regression framework was constructed. This approach utilizes generalized linear models to independently calculate the expected goal scoring intensity for both sides, allowing the system to derive exact scoreline probabilities through bivariate poisson distributions.

The pipeline concludes with an interactive deployment script that leverages the optimized Poisson parameters to simulate future match ups. Users can input any two national teams to obtain a detailed predictive report containing individual Elo ratings, calculated outcome percentages, and a breakdown of the most likely exact scorelines. Future iterations of this project will aim to embed these individual match scripts into a comprehensive Monte Carlo simulation framework to map out entire tournament brackets and calculate the statistical qualification probabilities for the various knockout stages of the 2026 World Cup.