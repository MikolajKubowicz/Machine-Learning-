The goal of this machine learning project is to build a predictive model that estimates an NBA player’s 3-point shooting percentage (3P%) based on various performance statistics. This model can help identify players with strong shooting potential or flag over/underperformers based on similar profiles.
The dataset used contains NBA player statistics for the 2021 season. Each row represents a player, and the features include:
Player stats like games played (G), minutes played (MP), field goal attempts (FGA), rebounds (TRB), assists (AST), etc.
The target variable is 3P% — the player's 3-point shooting percentage.
Before modeling, non-numeric and irrelevant columns like Player, Team (Tm), and Position (Pos) were removed.





Data Preprocessing
Dropped Non-Numeric Columns: Only numerical stats were retained for modeling.
Handled Missing Values: All rows containing NaN values were removed to ensure model compatibility.
Feature-Target Separation: The feature matrix X was separated from the target vector y (which was 3P%).
Train/Test Split: The data was split into training and test sets using an 80/20 ratio to evaluate generalization.



Model Training
1. Linear Regression
This model assumes a linear relationship between player stats and 3-point percentage.
It tries to find the best-fitting line that minimizes the squared error between predicted and actual values.

2. Random Forest Regressor
A more complex, non-linear model that builds an ensemble of decision trees.
Better at capturing interactions between features, but more prone to overfitting without tuning.




Model Evaluation
Metrics Used:
Mean Squared Error (MSE): Measures average squared difference between predicted and actual values. Lower is better.
R² Score: Measures how much of the variance in the target variable is explained by the model. Ranges from 0 to 1.



Interpretation:
Linear Regression outperformed Random Forest in both training and test metrics.
This suggests the relationship between features and 3P% is relatively linear, or the Random Forest model needs better hyperparameter tuning.


Visualization
A scatter plot was generated to compare predicted vs. actual values for the training set:
Each blue dot represents a player's predicted vs. actual 3P%.
The red line shows the ideal line where predictions = actual values.
Most predictions are tightly clustered near the line, showing decent accuracy.
A few extreme predictions (e.g., > 0.7 or < 0.1) suggest occasional over/underestimation.


Conclusion
This machine learning pipeline demonstrates:
How player performance stats can be used to predict 3-point shooting ability.
That even simple models like Linear Regression can perform well with clean, structured data.
There’s potential for improvement by using feature engineering or more advanced models like XGBoost with proper tuning.

