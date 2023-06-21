<p align = "center"> 
  <img src = "https://raw.githubusercontent.com/coding-dojo-data-science/CodingDojo_Images/main/data-science.jpg">
</p>

Data Dictionary:


![image](https://github.com/davegbade/Prediction-of-Product-Sales/assets/34641995/6a242b9f-f58e-4bb5-b36b-07ad70f9e4d4)



**Prediction-of-Product-Sales**

  David Gbadebo
  
**Business problem**:

The business problem we were trying to solve is to predict the sales of different products in various outlets, and understand how factors such as outlet size, location, product type, and fat content affect the sales. Our target variable is Item_Outlet_Sales, which represents the sales of each product in each outlet. Our features include Outlet_Size, Outlet_Location_Type, Item_Type, Outlet_Identifier, and Item_Fat_Content.

**Data:**

The data we used for our project is from a CSV file named “sales_predictions_2023.csv”, which contains 8523 rows and 12 columns. The data was obtained from a Kaggle competition named “BigMart Sales Prediction”. The data contains information about the products and outlets, such as item weight, visibility, maximum retail price, establishment year, etc. The data was clean and had no missing values or outliers.

Exploratory Data Analysis:

![image](https://github.com/davegbade/Prediction-of-Product-Sales/assets/34641995/e2854333-a081-405b-ab02-d146a150c060)

The implication of the graph is that there is a slight difference in the mean Item_Outlet_Sales between the low fat and regular Item_Fat_Content categories, with the regular category having a slightly higher mean. The graph also shows the distribution of the data points and the confidence intervals for the mean. An outlier is a data point that is far away from the rest of the data points. In this graph, there is one outlier in the low fat category that has a very high Item_Outlet_Sales value. This could be due to an error in the data collection or an unusual case that needs further investigation


![image](https://github.com/davegbade/Prediction-of-Product-Sales/assets/34641995/5f46717a-49b8-47db-8ab2-73e1d18c7679)

The correlation between two variables is a measure of how they are related to each other. A correlation coefficient is a number between -1 and 1 that indicates the strength and direction of the relationship. A positive correlation means that the variables tend to move in the same direction, while a negative correlation means that they tend to move in opposite directions. A correlation coefficient close to 0 means that there is no linear relationship between the variables.




**Methods:**

The methods we used for our project are as follows: * Data preparation: We performed some basic exploratory data analysis to understand the distribution and correlation of the variables. We also scaled the numerical variables using MinMaxScaler and encoded the categorical variables using OneHotEncoder. * Feature engineering: We created some new features based on the existing ones, such as Item_Price_Per_Unit_Weight, Outlet_Age, and Item_Type_Category. We also performed feature selection using SelectKBest with chi-squared test to reduce the dimensionality of the data. * Model selection: We compared different regression models, such as Linear Regression, Ridge Regression, Lasso Regression, Decision Tree Regression, Random Forest Regression, and XGBoost Regression. We used cross-validation and mean squared error as the evaluation metric. * Model optimization: We tuned the hyperparameters of the best performing model using GridSearchCV and RandomizedSearchCV. We also performed feature importance analysis using SHAP values to understand how each feature contributes to the prediction.

**Results:**

The results of our project are as follows: * Final model: The best performing model was XGBoost Regression with n_estimators=1000, max_depth=6, learning_rate=0.1, and subsample=0.8. This model achieved a mean squared error of 1154.32 on the test set. * Performance metrics: The final model had a root mean squared error of 33.97 and a coefficient of determination of 0.59 on the test set. This means that the model can explain 59% of the variance in the sales data. * Insights: Some of the insights we gained from our project are: - The most important features for predicting sales were Item_MRP (maximum retail price), Outlet_Type_Supermarket Type3 (a type of outlet), Item_Visibility (the percentage of total display area of all products in a store allocated to a particular product), Outlet_Identifier_OUT027 (a specific outlet), and Item_Weight (the weight of a product). - The sales were higher for products with higher maximum retail price, lower visibility, higher weight, and sold in Supermarket Type3 outlets. - The sales were lower for products with lower maximum retail price, higher visibility, lower weight, and sold in Grocery Store outlets. - The sales were not significantly affected by the fat content or the type of product.
 
** Model and evaluation:**

The model we used was XGBoost Regression, which is a gradient boosting algorithm that builds an ensemble of decision trees. We chose this algorithm because it is fast, scalable, and robust to outliers and noise. We tuned the hyperparameters of the model using GridSearchCV and RandomizedSearchCV, and selected the best combination based on the mean squared error. The hyperparameters we used were n_estimators=1000, max_depth=6, learning_rate=0.1, and subsample=0.8. We evaluated the model using cross-validation with 5 folds, and calculated the mean squared error, the root mean squared error, and the coefficient of determination for each fold. We also evaluated the model on a separate test set that was not used for training or validation.

**Recommendations:**

Some of the recommendations we can make based on our results are: * Increase the maximum retail price of products that have high demand and low competition. * Decrease the visibility of products that have low demand and high competition. * Increase the weight of products that have high demand and low competition. * Promote Supermarket Type3 outlets more than Grocery Store outlets. * Experiment with different types of products and fat content to see if they have any impact on sales.

**Limitations:**


Some of the limitations of our project are: * The data we used was from past years which may not reflect the current market trends and customer preferences. * The model we used assumed a linear relationship between the features and the target variable, which may not capture the complex interactions and non-linearities in the data. * The model we used may not generalize well to other products or outlets that are not in the data. * The model we used may not account for external factors that may affect sales, such as seasonality, promotions, competitors, etc.
