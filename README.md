# Future Income Growth of Russell 1000
Nithin Pingili, Andrew Tan, Zhaokun Xue and Yunhao Yang

Estimated the net income growth rate of Russell 1000 companies for next quarter.

Data: The dataset we use is from ​QuickFS​. In all, there are 904101 records with 192 features.

The six machine learning models are:

**Support Vector Regression (SVR)**: SVR uses the same principles as the SVM for classification, with some minor differences to handle continuous data (label). We perform cross-validation using GridSearchCV to determine the best ‘kernel’ and ‘degree’ for SVR. The parameters differed by industry. According to our results, this model had a relatively higher accuracy among these six models.

**Radius Neighbor Regression (RNR)**: RNR is based on neighbors within a fixed radius. The labels are determined by the labels of the nearest neighbors in the training set. The radius we used is 5.

**Linear Regression**: This is a linear approach to modeling the relationship between a dependent variable and one or more independent variables. We initially tried simple linear regression. However, it turns out that there is no correlation between any single feature and the label. So we used the multiple linear regression model in order to predict the labels. The regression model finds the most optimal coefficients for all the features. We used the coefficients to determine which features had the greatest impact on the predicted net income growth rate and how the various features are related to each other.

**Lasso Regression**: This is a type of linear regression where the data values are shrunk towards a central point. The advantage of using this regression over simple linear regression is that it reduces model complexity and prevents overfitting. To do so, lasso does ignore some features depending on the hyperparameter alpha. The higher the alpha, the more features are ignored. In order to have at least one feature with a nonzero coefficient for each industry, we tried different alpha a range from 0.1 to 0.9 with an increment of 0.1. The majority of the industries had 0.8 as the best alpha parameter.

**Multi-layer Perceptron Regressor**: This model optimizes the squared-loss using a stochastic gradient descent. Hyperparameters for this model include the size of the hidden layers and the activation function of the neurons. We used grid search and cross-validation to determine the best combination of the parameters that minimize the MSE.

**Random Sample Consensus Regressor**: ​Random Sample Consensus is an iterative method to estimate the parameters of the regression model from a set of inliers of the data set, under the assumption that the outliers are to be accorded no influence on the result of the estimates. It is non-deterministic in the sense that it produces a reasonable result with a certain probability. One could increase this probability of plausible outcome by increasing the number of iterations.

More details in Final_Report.pdf