# Analysing Clash Royale Matches with Machine Learning

- **Data Collection**
   - Seed player IDs from each arena were gathered and used to perform a BFS to gather Ladder matches from that particular arena, ensuring a roughly even number of matches from each arena
   - Bootstrapping process uses an asynchronous BFS to speed things up (nonetheless subject to rate limits)
   - About 640k ladder matches were collected in total

+ **ML Techniques**
   - Logisitic regression
   - Random forest
   - XGBoost
   - Multilayer perceptron (MLP)

- **Results**
  - XGBoost and MLP performed the best on the test set with a test accuracy of 67.7%
	- Tuning the MLP proves it is hard to beat the current result given the current data. More training improves the train accuracy but decreases the test accuracy beyond 67.7%, a clear indication of overfitting.
	- Based on the deck composition and card levels alone and without knowing the skill / experience of the player, 67.7% is a largely decent figure. More meaningful features / feature engineering may be needed to see an improvement in accuracy. 
	
