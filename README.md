# Game Analytics: Day 14 Player Retention/Churn Prediction

We utilized data from the first day to day 7 after game installation to determine whether a player would quit the game by day 14. This predictive classification model relies on measures such as user behavior, in-game metrics (e.g., win rate), and engagement patterns to identify players at risk of churning.

## Predicting which players will play our game by machine learning models

The data was divided into training data for the model to learn and validation/testing data to evaluate the model with unseen data. We experimented with three machine learning algorithms: Logistic Regression, Random Forest, and Gradient Boosting. All algorithms were compared, and the best one was selected as our final model.

 ![Slide5](https://github.com/kk-chaiyapuk/Game_Analytics_D14_Retention_Prediction/assets/82194433/a25436d8-9fc4-4a8d-a560-b458f004e294)

## Using day 7 player data might be too late as we continue to lose player base

As demonstrated in the plot, the longer we wait for players to play and collect data, the better the model can predict whether a player would quit the game. However, we noticed that most players would quit right after playing the game, resulting in a continued loss of the player base as we waited for data. Moving forward, the optimal day for data collection needs to be evaluated, but for now, we used day 7 data as it offered the best-performing models.

Gradient Boosting was chosen as our final model. Based on day 7 testing data, the model accurately predicted 65% of all retention within the top 6% of the total population. The model provided a similar performance to Random Forest but used simpler measures, making it easier to comprehend.

 ![Slide8](https://github.com/kk-chaiyapuk/Game_Analytics_D14_Retention_Prediction/assets/82194433/1c2ee504-3c81-4809-9bac-f75d073dddd2)

 ![Slide16](https://github.com/kk-chaiyapuk/Game_Analytics_D14_Retention_Prediction/assets/82194433/2cd15a08-b35f-4122-9b69-79152d00069a)

 ![Slide15](https://github.com/kk-chaiyapuk/Game_Analytics_D14_Retention_Prediction/assets/82194433/8e31be22-9fa3-4955-b876-4cb9f70a31d9)

## How our classifying models work in detail

We defined day 14 retention as true if players were still playing the game on day 14. Our goal was to predict 6% of total players as retained, based on the average of total players in our data. We evaluated our models using the F1 score, which is an equal combination of Precision and Recall.

 ![Slide7](https://github.com/kk-chaiyapuk/Game_Analytics_D14_Retention_Prediction/assets/82194433/0b965a2d-3749-4745-b57f-29a85c8aa7d7)

First, our models assigned a retention likelihood for every player in our data. Next, we ranked players based on the likelihood, from the most to the least likely to keep playing our game. Finally, we looked at the top 6 percentile to identify the likelihood cutoff (22.6%) and classified players who were more than 22.6% likely as retained.

By not using a 50% cutoff, our models lost some accuracy, as it would overly classify retained players. However, using data from day 0 to day 3, no players had more than a 50% likelihood of being retained (our data is imbalanced, so the model simply placed everyone below 50%). The cutoff needed to be changed for us to classify such a model. This also improved our model performance, enhancing Recall at the cost of less Precision.

 ![Slide6](https://github.com/kk-chaiyapuk/Game_Analytics_D14_Retention_Prediction/assets/82194433/db34c730-7458-4db8-9996-5906a31d544f)





