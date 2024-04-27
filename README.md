Munjarin Rahman's Data Science Projects
Welcome to my professional portfolio on GitHub. This repository contains various projects showcasing my skills and expertise in business analytics and data science, particularly in the realm of predictive modeling and decision analysis. Below is a detailed description of one of my key projects, "Business Challenge II".

About Me
I am a seasoned business analyst with a strong background in strategic management and data analytics. My educational credentials include a Master of Science in Business Analytics from Hult International Business School. I have applied my skills in various real-world scenarios, including product sourcing and manufacturing process management, to drive profitability and efficiency improvements.

LinkedIn: munjarin



Passion Project : Bridge and Torch Text Adventure
Background
"Bridge and Torch Text Adventure" is a text-based simulation game that challenges players to solve puzzles and make strategic decisions under time constraints. The project was inspired by classic adventure games and puzzles, and it leverages Python's interactive capabilities to engage users in a narrative-driven experience.

Objective
The main goal of this project was to create an engaging text adventure game that combines elements of storytelling, puzzle-solving, and strategic planning. The game is designed to be both entertaining and intellectually stimulating, providing players with a series of challenges that test their problem-solving skills and decision-making abilities.

Game Design and Development
Conceptualization
The game's concept revolves around a scenario where players must safely guide a group of characters across a bridge at night. The catch is that the bridge can only support two people at a time and they have a single torch that must be carried back and forth. The time taken to cross the bridge varies for each character, adding complexity to the task of crossing everyone within a limited time.

Implementation
The game was developed in Python, utilizing basic console input and output to interact with the player. Python's simplicity and flexibility made it an ideal choice for rapidly prototyping and testing game mechanics.

Code Snippet for Game Mechanics

def calculate_time(group):
    """Calculate the crossing time based on the slowest member of the group."""
    return max(group)

def play_round():
    """Play a round of the game where players choose who crosses the bridge."""
    print("Choose two characters to cross the bridge.")
    choice = input("Enter your choice: ").split()
    time_taken = calculate_time(choice)
    update_game_state(time_taken)

def update_game_state(time):
    """Update the game state based on the time taken for the round."""
    global remaining_time
    remaining_time -= time
    check_game_end()

def check_game_end():
    """Check if the game has ended based on remaining time and characters left."""
    if remaining_time <= 0:
        print("You have run out of time!")
    elif not characters_left:
        print("Congratulations! All characters have crossed the bridge.")



Project Overview: Regression Analysis - Decision Tree Optimization
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
