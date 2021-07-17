## 2. challenge question

> What other options are there for randomly splitting test/train data?

### Stratified K-Folds
A variation of KFold that returns stratified folds. The folds are selected so that the mean response value is approximately equal in all the partitions. Stratification seeks to ensure that each fold is representative of all **strata** of the data. Generally this is done in a supervised way for classification and aims to ensure each class is equally represented across each test fold.

### Stratified ShuffleSplit
A combination of stratefied K-Folds and ShuffleSplit, which returns stratified randomized folds. Like the ShuffleSplit strategy, and unlike K-Folds, stratified random splits do not guarantee that all folds will be different, although this is still very likely for sizeable datasets.

### Repeated K-Folds
Provides a way to improve the estimated performance of a machine learning model. Repeats K-Fold n times with different randomization in each repetition and reporting the mean result across all folds from all runs.

The mean result is expected to be a more accurate estimate of the true mean performance of the model on the dataset, as calculated using the standard error. Although, some disagree on the usefulness of this strategy.

### Group K-Folds
K-folds variant with non-overlapping groups. The same group will not appear in two different folds. The folds are approximately balanced in the sense that the number of distinct groups is approximately the same in each fold. Group K-Folds is recommended when you have groups you don't want split across the training and test sets.