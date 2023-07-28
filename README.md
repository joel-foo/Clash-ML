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
  - Logistic regression achieved a 63.9% test accuracy and 63.8% train accuracy. There is no overfitting, and bias is fairly low (better than a guess).
  - We use the 60% accuracy benchmark from literature: https://harrychengz.medium.com/how-data-science-can-help-you-play-clash-royale-better-517fb840168d
  - XGBoost and MLP performed the best on the test set with a test accuracy of 67.7% and a train accuracy of 73.6% and 74.6% respectively.
	- There is clearly some overfitting - regularization is worth looking into (rather than feature reduction)
	- Tuning the MLP shows that 67.7% is about as good the model can perform on the test set. Further tuning beyond that leads to a decrease in test accuracy.  
    - Based on the deck composition and card levels alone and without knowing the skill / experience of the player, 67.7% is a largely decent figure. More meaningful features / feature engineering may be needed to see an improvement in accuracy. 
	
