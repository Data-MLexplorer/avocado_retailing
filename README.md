

## Project summary
This project analyzes avocado sales data to deliver both predictive and prescriptive insights for suppliers and distributors. Using historical sales and price data we will forecast future demand for a selected product in three markets, and prescribe the optimal sourcing strategy (domestic, imported or combined) for each market.

## Data sources
- Kaggle — Avocado prices and sales volume (2015–2023): https://www.kaggle.com/datasets/vakhariapujan/avocado-prices-and-sales-volume-2015-2023  
- Kaggle — Avocado augmented dataset: https://www.kaggle.com/datasets/mathurinache/avocado-augmented

(We will evaluate both datasets and select the one(s) with the highest data quality for the chosen markets + product.)

#plu4046
small/medium Hass Avocados (~3-5 oz)

#plu4225
large Hass Avocados (~8-10 oz)

#plu4770
extra large Hass Avocados (~10-15 oz)

## Objectives
1. Predictive analytics
   - Forecast avocado sales (units / volume) for one selected product in three chosen markets (cities) for the next year.
   - Select the product and markets based on data completeness and quality.
   - Produce probabilistic forecasts (intervals) and point forecasts.

2. Prescriptive analytics
   - From the perspective of an avocado supplier/distributor, determine the optimal supplier strategy — domestic, imported, or a combined approach — for each chosen market.
   - Optimize for business objectives such as minimizing total cost, maximizing service level, or balancing risk and availability.

## Scope and assumptions
- We focus on one avocado product variant (e.g., Hass) and three markets with reliable historical data.
- Forecasts target a 12-month horizon (monthly or weekly granularity depending on data).
- Supplier optimization will consider common cost components (procurement, transportation, tariffs, spoilage) and constraints (lead time, capacity).
- We will document assumptions clearly and run sensitivity analyses where appropriate.

## Proposed approach / Methodology
1. Data ingestion & validation
   - Download and version the selected dataset(s) from Kaggle.
   - Validate fields, handle missing values, and harmonize formats (dates, geography, product naming).

2. Exploratory data analysis (EDA)
   - Time series visualization, seasonality decomposition, outlier detection , Identify key regions
     

3. Feature engineering
   - Create calendar features (month, week, holidays), lag features, rolling aggregates, price and promotion indicators, weather or macro indicators if available.

4. Modeling (predictive)
   - Baseline: naive and seasonal naive models.
   - Classical: Auto Regressive Model to predict avocado volume for next 1 year.
   - Modern: Prophet, TBATS (if complex seasonality), and tree-based models or gradient boosting on engineered features.
   - Deep learning (optional): LSTM/GRU models for series with complex patterns.
   - Model selection by backtesting (rolling origin), cross-validation on time series, and holdout sets.

5. Evaluation
   - Use appropriate time-series metrics: MAE(Mean Absolute Error),MSE(Mean Squared Error), RMSE(RootMeanSquaredError), MAPE(MeanAbsolutePercentError).
   - Present visual diagnostics and forecast uncertainty.

6. Prescriptive analysis
   - Minimize the Shipping Costs for Hass Avocados
   - Formulate an optimization (e.g., linear programming or integer programming) to choose supplier mix subject to demand forecasts and constraints.
   - Use Forecasted Data to estimate Market's Demand

7. Deliverables
   - Cleaned dataset and reproducible data pipeline.
   - Jupyter notebooks / scripts with EDA, modeling, and evaluation.
   - Forecasts and an interactive dashboard or visual reports.
   - Prescriptive optimization Excel File.
