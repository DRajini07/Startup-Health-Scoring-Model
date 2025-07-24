# Startup-Health-Scoring-Model

## Aim

This project aims to **predict a composite score** that reflects the overall health of a startup using **key business indicators**. Machine learning models are trained and evaluated to predict this score, which can help investors or stakeholders quickly assess and rank startups.

## Dataset

The dataset used for this analysis is **Startup_Scoring_Dataset.csv**. It includes the following columns:

- 'startup_id': Unique identifier for each startup.
- `team_experience`: Experience level of the startup team.
- `market_size_million_usd`: Size of the target market in millions of USD.
- `monthly_active_users`: Number of active users per month.
- `monthly_burn_rate_inr`: Monthly expenditure of the startup in INR.
- `funds_raised_inr`: Total funds raised by the startup in INR.
- `valuation_inr`: Current valuation of the startup in INR.

## Methodology

1.  **Data Preprocessing and Normalization**:
    *   Loaded the dataset.
    *   Handled the 'monthly_burn_rate_inr' by flipping the values (higher burn rate is less favorable).
    *   Applied Min-Max scaling to all numeric features to bring them to a similar range.

2.  **Custom Scoring Formula**:
    *   Defined weights for each feature based on their perceived importance for startup success.
    *   Calculated a 'composite_score' for each startup using a weighted sum of the normalized features.

3.  **Ranking & Interpretation**:
    *   Ranked the startups based on their 'composite_score'.
    *   Identified and analyzed the top and bottom-ranked startups to understand the factors contributing to their scores.

4.  **Visualization**:
    *   Visualized the distribution of composite scores.
    *   Plotted the composite scores of all startups to see the ranking visually.
    *   Generated a correlation heatmap to understand the relationships between the numeric features.
    *   Visualized feature importance/coefficients from the trained machine learning models.

5.  **Machine Learning Models**:
    *   Split the data into training and testing sets.
    *   Trained several regression models (Linear Regression, Ridge, Lasso, Random Forest Regressor, XGBoost Regressor, and a Neural Network) to predict the 'composite_score'.
    *   Evaluated the models using metrics like Mean Squared Error (MSE), Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and R-squared (R2) score.

## Results

- The Linear Regression, Ridge, and Lasso models performed exceptionally well on this dataset, achieving R2 scores very close to 1. This suggests a strong linear relationship between the features and the composite score, as defined by the custom formula.
- The Random Forest and XGBoost models also showed reasonable performance, with R2 scores around 0.75 and 0.85 respectively.
- The Neural Network model achieved an R2 score of around 0.93, indicating good predictive capability.
- Feature importance analysis from the tree-based models and coefficient analysis from the linear models provide insights into which features contribute most significantly to the composite score.

## Conclusion

The analysis successfully created a scoring system for startups and demonstrated that various regression models can effectively predict this composite score. The linear models showed surprisingly high performance, likely due to the way the composite score was calculated as a linear combination of weighted features. Further analysis could involve refining the weighting system, exploring different feature engineering techniques, or applying more advanced modeling approaches.
