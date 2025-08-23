Using Machine Learning to Predict Football Player Performance and Position Suitability
Project Background
This project explores the use of machine learning to predict football player performance and identify viable positions (midfield or forward or defender) using the 2024/2025 football season dataset (note: the initial project involved the 2023/2024 season; however, it was adapted and improved for the 2024/2025 season).
The motivation comes from a long-standing passion for football combined with a deep academic interest in AI and data mining. The aim was to build a data-driven tool that scouts, analysts, and enthusiasts could use to assess players beyond traditional statistics.
The project leverages the Random Forest algorithm due to its flexibility in handling regression and classification tasks, its robustness with noisy datasets, and its interpretability through feature importance.

Executive Summary

Dataset: 2500+ players, 200+ attributes, covering the 2024/2025 season.
Goal: Predict player performance (via scoring, passing, and assist efficiency) and classify positional suitability (midfield/forward).
Methodology: Data cleaning and preprocessing, combining raw attributes into efficiency metrics, Random Forest for regression (performance prediction) and classification (position suitability).
Output: Player reports with adjusted performance scores, positional recommendations, and visual comparisons against peers using matplotlib and seaborn.
Outcome: Achieved core objectives and implemented visualizations.

Insights and Deep Dive

Data Cleaning

Removed irrelevant attributes to reduce noise.
Addressed missing values. Players with insufficient data were removed. Players with insufficient data in certain statistics were replaced with the median (such as defenders and scoring attributes).
Handled duplicates and standardized categorical values (player positions mapped to numerical labels).

Combining Attributes

Designed efficiency metrics to better reflect overall player impact:
Scoring Efficiency (goals, shots on target, etc).
Assist Efficiency (assists, passes into penalty area, key passes, etc).
Passing Efficiency (pass completion, progressive passes, etc).
These metrics would reduce the number of attributes we needed to use and help the machine learning model generate more efficient and sophisticated predictions.
Adjusted weightings and added contingencies to balance biases (for example, avoiding defenders topping scoring efficiency due to a few clinical goals).

Machine Learning
Random Forest Classification: Predicted positional suitability (midfield/forward/defender) with strong performance (F1 scores around 0.98 for midfielders).
Random Forest Regression: Predicted scoring, assist, and passing efficiency. Combined into an overall performance score with an age-based multiplier to account for player development or decline.
Models were refined using mean squared error for regression and cross-validation for classification.

Player Reports
Reports were generated per player, forcing the queried player into the test set for fair evaluation.
Each report includes predicted position suitability, adjusted performance score, and comparative visualizations against peers by league, position, or age group.
For example, Erling Haaland’s score was initially undervalued due to passing bias, which was resolved by rebalancing weights to give scoring more emphasis. Different positions have different efficiencies valued more highly.

Recommendations
Use a more consistent dataset to avoid anomalies such as per-90 vs. total values.
Validate whether custom-designed efficiency metrics truly outperform raw attributes or add unnecessary complexity.
Extend the model to estimate player compatibility within squads for a team chemistry option.
Extend the model to work outside the top five European leagues.
Implement full k-fold cross-validation to ensure robustness across all data(current work in progress).
Package the system into a web app or API for practical use by scouts and analysts.

Clarifying Questions and Assumptions
The project focuses only on midfielders and forwards, and defenders. Goalkeepers were excluded for simplicity and due to the completely different attributes in which performance is measured.
Predictions are relatively short-term and don't focus on a player's entire future career.
Younger players are assumed to generally improve with age, hence the use of an age-based performance multiplier.
The system assumes that users will query by player name to generate reports.
