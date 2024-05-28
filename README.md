# Equity Return Predictability

This repository contains code and analysis for predicting equity returns using various machine learning and deep learning models, as well as traditional linear regression models. The goal of this project is to establish if more complex algorithms yield superior results compared to simpler linear models in the context of equity return prediction.

## Dataset

The dataset used in this project consists of S&P index returns along with several factors such as dividends, earnings, book-to-market ratio, net issues, treasury bills, long-term yield, corporate bond returns (AAA and BAA), inflation, and stock variance. The dataset features 828 rows and 13 variables.

## Methodology

The methodology employed in this project involves the following steps:

1. **Data Loading and Preprocessing**: The dataset is loaded from an Excel file, and relevant columns are selected. Missing values are handled by dropping rows with missing dates, and the date column is formatted correctly for time series analysis.

2. **Feature Extraction**: Additional features known to have predictive power for stock returns are derived, such as the log dividend-price ratio, log earning-price ratio, dividend payout ratio, term spread, default spread, and default return spread.

3. **Data Splitting**: The data is split into training and testing sets while preserving the time series nature of the data, ensuring that models are trained on past data and tested on future data.

4. **Model Training and Evaluation**: Various models are trained and evaluated using an expanding window approach, where models are re-estimated at each time step, and out-of-sample forecasts are produced. Models evaluated include Ordinary Least Squares (OLS) regressions, penalized linear regressions (Ridge, Lasso, Elastic Net), Principal Component Analysis (PCA), Random Forests, Boosted Regression Trees, Extremely Randomized Trees, and Neural Networks (both shallow and deep).

5. **Performance Metrics**: Model performance is evaluated based on the Mean Squared Prediction Error (MSPE) and out-of-sample R-squared (R²).

6. **Robustness Analysis**: Additional checks are performed to analyze model behavior under different conditions and model specifications, including a case study of the 2007-2008 financial crisis.

## Results

The analysis compares the predictive performance and robustness of different models, highlighting their strengths and weaknesses. Key findings include:

- Penalized regression models (Ridge, Lasso, and ElasticNet) exhibit low deviation in their predictions and demonstrate superior performance in terms of both R-squared and MSPE metrics compared to other methods.
- Ensemble methods like Random Forest and Boosted Regression Trees showcase competitive performance, with Boosted Regression Trees demonstrating efficacy in capturing complex data relationships.
- Extremely Randomized Trees (ERRT) stand out for their resilience during market downturns, maintaining closer alignment with actual values and exhibiting fewer deviations during significant market movements.
- Neural networks, both shallow and deep, perform worse than other machine learning approaches in terms of MSPE and R-squared metrics.

## Usage

To reproduce the analysis and results, follow these steps:

1. Clone the repository
2. Install the required dependencies
3. Run the Jupyter Notebook files in the following order:
   - `project2_final.ipynb`: Contains the main analysis, including data loading, preprocessing, feature extraction, model training, and evaluation.
   - `output_metrics_time.ipynb`: Generates visualizations and additional analysis for model performance and robustness.

The `results` folder contains CSV files with the predictions made by each model, while the `plots` folder stores the generated plots used in the LaTeX document.

## Contributing

Contributions to this project are welcome. If you find any issues or have suggestions for improvement, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License