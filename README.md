# Sales Forecasting to Optimize Retail Supply Chain 

## Project Summary

This project presents a machine learning-based approach to optimize retail supply chain operations by accurately forecasting weekly sales. Leveraging historical sales data enriched with store characteristics, promotional events, and temporal factors, a Random Forest Regressor model is employed to predict `Weekly_Sales`. The insights derived from the model, particularly regarding key sales drivers, facilitate data-driven decision-making for improved inventory management and operational efficiency.

## Business Objective

The primary goal is to enhance supply chain performance by providing reliable weekly sales forecasts for individual retail stores. This predictive capability aims to:

*   **Improve Inventory Management:** Reduce stockouts and overstocking through accurate demand prediction.
*   **Optimize Resource Allocation:** Inform decisions regarding staffing, logistics, and promotional planning.
*   **Identify Sales Drivers:** Understand the relative impact of various factors (e.g., promotions, store type, seasonality, holidays) on sales performance.
*   **Enable Proactive Strategy:** Allow businesses to anticipate market changes and adjust strategies accordingly.

## Methodology

The project follows a structured data science workflow:

1.  **Data Acquisition & Integration:**
    *   Loading of core datasets: `Stores.csv`, `Features.csv`, `Train.csv`, `Test.csv`.
    *   Merging datasets based on common keys (`Store`, `Date`) to create a comprehensive analytical base table.

2.  **Data Preprocessing & Feature Engineering:**
    *   **Handling Missing Data:** Imputation of missing numerical values using the median and categorical values using the mode.
    *   **Temporal Feature Extraction:** Derivation of `Year`, `Month`, `Week`, `Day`, and `DayOfWeek` from the `Date` column to capture seasonality and trends.
    *   **Categorical Variable Encoding:** Transformation of categorical features (e.g., `Store_Type`, `IsHoliday`) into a numerical format using one-hot encoding suitable for machine learning algorithms.

3.  **Predictive Modeling:**
    *   **Algorithm:** Utilization of the `RandomForestRegressor` from `scikit-learn`, known for its robustness and ability to handle complex interactions.
    *   **Training:** The model is trained on the preprocessed historical data (`Train.csv`) with `Weekly_Sales` as the target variable.

4.  **Model Evaluation:**
    *   Performance assessment using standard regression metrics:
        *   **Mean Squared Error (MSE):** Quantifies the average squared prediction error.
        *   **R-squared (R²):** Indicates the proportion of variance in `Weekly_Sales` explained by the model.

5.  **Insight Generation:**
    *   **Feature Importance Analysis:** Identification and ranking of the most influential features driving sales predictions, providing actionable business insights.
    *   **Data Visualization:** Creation of insightful plots using `Plotly` and `Seaborn` to illustrate:
        *   Overall sales trends and seasonality over time.
        *   Sales distribution patterns across different store types.
        *   Relationships between key features and sales.

## Technology Stack

*   **Core Language:** Python (3.x)
*   **Data Manipulation:** Pandas
*   **Numerical Computation:** NumPy
*   **Machine Learning:** Scikit-learn
*   **Data Visualization:** Plotly, Seaborn, Matplotlib

## Setup and Installation

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/rajat4rao/sales-forecast-optimize-supply/
    cd sales-forecast-optimize-supply
    ```

2.  **Install Dependencies:**
    Ensure you have Python 3 installed. Then, install the required libraries using pip:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn plotly
    ```

3.  **Dataset Placement:**
    Place the dataset files (`Features.csv`, `Stores.csv`, `Train.csv`, `Test.csv`) in the designated data directory within the project structure (e.g., a `./data/` folder).

## Usage

To execute the sales forecasting pipeline (including data processing, model training, evaluation, and visualization generation):

```bash
python src/sales_forecasting.py
