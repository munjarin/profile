Munjarin Rahman's Data Science Projects
Welcome to my professional portfolio on GitHub. This repository contains various projects showcasing my skills and expertise in business analytics and data science, particularly in the realm of predictive modeling and decision analysis. Below is a detailed description of one of my key projects, "Business Challenge II".

About Me
I am a seasoned business analyst with a strong background in strategic management and data analytics. My educational credentials include a Master of Science in Business Analytics from Hult International Business School. I have applied my skills in various real-world scenarios, including product sourcing and manufacturing process management, to drive profitability and efficiency improvements.

LinkedIn: munjarin

Project Overview: Business Challenge II - Decision Tree Optimization
Background
This project addresses a complex business problem involving prediction of key business outcomes. Using a decision tree model, the project explores the efficacy of various hyperparameters and their impact on the model's predictive accuracy and generalization to new data.

Objective
The primary objective was to optimize a decision tree regressor to ensure the highest level of accuracy while minimizing the risk of overfitting. This involved an extensive exploration of hyperparameters tuning using advanced techniques like RandomizedSearchCV.

Methodology
Data Preparation
The data set comprised various business metrics collected from internal company records. Prior to modeling, the data underwent preprocessing, including normalization, handling missing values, and feature selection to ensure optimal model performance.

Model Building
A DecisionTreeRegressor from Scikit-Learn was employed for this analysis. The choice of a decision tree was motivated by its interpretability and the non-linear nature of the data.

Code Snippet for Model Configuration
python
Copy code
from sklearn.tree import DecisionTreeRegressor
from sklearn.model_selection import RandomizedSearchCV

# Define the parameter grid
param_grid = {
    'criterion': ['squared_error', 'absolute_error'],
    'splitter': ['best', 'random'],
    'max_depth': [None, 10, 20, 30],
    'min_samples_leaf': [1, 2, 4, 6]
}

# Instantiate and configure RandomizedSearchCV
tuned_tree = DecisionTreeRegressor(random_state=219)
tuned_tree_cv = RandomizedSearchCV(estimator=tuned_tree, param_distributions=param_grid, cv=5, n_iter=100, random_state=702)
tuned_tree_cv.fit(x_data, y_data)
Results
The best parameters obtained from RandomizedSearchCV were {criterion: 'squared_error', max_depth: 20, min_samples_leaf: 1, splitter: 'random'}. Applying these parameters, the final model demonstrated significant improvements in predictive accuracy compared to the baseline model.

Key Findings
The optimal depth of the tree indicated a complex model, which was regularized by optimizing the min_samples_leaf parameter to prevent overfitting.
The use of 'squared_error' as a criterion provided the best balance between bias and variance.
Conclusion
The tuned decision tree model showed a robust ability to predict outcomes with high accuracy, underscoring the importance of thorough hyperparameter tuning in building predictive models.

Future Work
Further research will focus on ensemble methods to enhance model stability and performance, and on integrating more complex algorithms like Gradient Boosting and Random Forests.
