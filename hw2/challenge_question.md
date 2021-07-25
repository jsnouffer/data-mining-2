## 2. challenge question

> What are some of the various methods sensitivity analysis?

### Permutation feature importance
This approach directly measures feature importance by observing how random re-shuffling of each predictor influences model performance. This approach is reliable and applicable to any model. However, this approach overestimates the importance of correlated predictors.

### Drop column feature importance
This approach examines feature importance by comparing a model with all features versus a model with a specific feature dropped for training. This approach is the most accurate, but can be computationally expensive due to the amount retraining required.

### Gini importance or Mean Decrease in Impurity (MDI)
Calculates each feature importance as the number of splits across all trees that include the feature, proportionally to the number of samples it splits. This biggest advantage of this method is the speed of computation, because all needed values are computed during the Radom Forest training. A drawback is its tendency to prefer numerical features and categorical features with high cardinality. In the case of correlated features, it can select one of those features and not the other.

### Boruta
An R package that randomly permutes variables (similar to Permutation feature importance), but on all variables at the same time. Then count the number of times a variable performs better than the best noise and calculate the confidence towards it being better than noise or not.

### Feature Importance Measure in Gradient Boosting Models
Provides a score that indicates how useful or valuable each feature was in the construction of the boosted decision trees within the model. This importance is calculated explicitly for each attribute in the dataset, allowing attributes to be ranked and compared to each other.