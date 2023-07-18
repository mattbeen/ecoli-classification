# ecoli-classification

In this project, we are applying data mining techniques to real-world situation. A dataset contains expression data and functional data of 1500 genes of E. coli, a bacterium that found in lower intestine of warm-blooded organisms is used.

The dataset is constructed of 3 nominal features and 103 numerical features with missing values. Binary class label in “Target” column indicate whether gene has the function “Cell communication”.

A classifier with good generalization is trained to differentiate whether a given gene has the function “Cell communication”.
To achieve the ojectives, we have to perform data pre-processing, train-test split, model selection, hyperparameter tuning and model evaluation.

For data pre-processing, normalization, handling missing data and outlier detection will be performed to numerical features. For nominal feature, only imputation will be performed.

For handling the missing value, imputation by feature’s class-specific values will be applied. With numerical features, average values of feature’s class will replace the missing values while mode of feature’s class will replace the missing value of nominal features.

For outlier detection, density-based technique will be used to detect the anomalies in each numerical feature after imputation. Isolation-based technique will also be used to detect outliers in the dataset.

For normalization, no normalization, min-max normalization and standization will be used to evalute the best normalization method for this dataset.

To find the best combination of pre-processing technique, cross validation with default setting of decision tree of sklearn as learner. 10-fold cross validation will be performed and the average accuracy will be used to evaluate the combination for training the best model for classifer and hyperparameter tuning.

Combinations (Outlier Detection & Normalization):
Density-based Only
Density-based + Min-max
Density-based + Standardization
Isolation-based Only
Isolation-based + Min-max
Isolation-based + Standardization
Min-max Only
Standardization Only
No outlier detection + No normalization


With the best combination of pre-processing, we will perform train-test split on the pre-processed dataset. This is used to evaluate the performance of the classifer. The train-test split ratio is 80/20 where 80% to training and 20% to testing. The training set will be used to train and validate the classifer while test set will be used to test the generalization power of the classifer.

After splitting the data, we will move to model selection. Standalone Decision tree, random forest, k-NN and Naïve Bayes classifer will be trained with 10-folded cross-validation and the scores,accuracy precision,recall and F1 score, of each cross validation run will be averaged to evaluate which classifer has the best performance. Emsemble classifer with k-NNN, Naïve Bayes and decision tree will also be trained with 10-fold-cross validation to evalute the result. Majority voting is applied to the emsemble method.

With the best combination of pre-processing and the best classifer, we will fine tune the hyperparameters of the classifer selected with 10-fold-cross validation which helps to prevent from overfitting or underfitting. Hyperparameters to be fine tuned can be the value of k nearest neighbour, the purity function and the pruning of the decision tree and the number of trees in random forest.
