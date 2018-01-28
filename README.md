# Gamer Performance Analysis


### Background

The project is based on the data set [Skill Craft Dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/00272/SkillCraft1_Dataset.csv). I want to analysis what factors are important to a gamer's performance, and figure out how well they can be used to predict a gamer's performance. The column `LeagueIndex` in the dataset indicartes the overall performance of gamers, which is the response variable in our analysis. Additionally, around 20 attributes are included in the dataset which can be used as our explanatory variables. 

### Analysis

##### Step 1: Download data and Clean data

I downloaded the data and deleted the instances associated with the missing data as well as the column `GameID`. 

##### Step 2: EDA 

In order to verify the dataset, I created a scatter plot of league level and player APM. Since player's APMs is positively correlated with player league, this dataset is proved to be reasonable.

#### Step 3: Train Data

I seperated the data into two groups, training data and testing data. I did a cross-validation (k-fold 10) on the training data in order to get the best hyperparameter $\alpha$ for Lasso model. Validation score reaches the peak when $\alpha$ equals to $0.00446684$. Hence, $0.00446684$ was chosen for $alpha$. Then, I trained Lasso model with the $\alpha$ ($0.00446684$) on entire the training data and 12 features are selected.

#### Step 4: Test Data and Result

I applied the trained Lasso model to the untouched testing data and compared training score and testing score. The testing score (0.5055) is close to training score (0.5426).

### Conclusion

After doing the analysis, I can conclude that using the gamers' behavioural data to predict the gamers' performance is effective and reasonable. 



