# EdgeFlex AI: Smart Household Energy Optimization

This repository documents the development of an AI system to forecast household energy consumption and optimize appliance scheduling. The project is divided into a data preparation phase (Week 1) and a modeling phase (Week 2).

---
## Week 1: Data Preprocessing and Exploration

The primary goal of Week 1 was to load, clean, and prepare the project's datasets to make them suitable for machine learning. This foundational stage involved handling missing values, standardizing formats, and engineering new features.

### Key Activities Completed
* **Data Loading & Inspection**: Loaded the REFIT (household energy) and Solar Power (solar generation and weather) datasets and performed an initial inspection.
* **Data Cleaning**: Standardized column names and converted raw timestamp columns into a proper `DatetimeIndex`.
* **Resampling & Alignment**: Resampled the high-frequency energy data to an hourly frequency to align with the hourly solar and weather data.
* **Feature Engineering**: Created new time-based features (e.g., hour, day of week) to provide the model with cyclical patterns.
* **Data Splitting**: Split the datasets into chronological training, validation, and testing sets.

### Key Findings & Decisions
A critical finding was that the **REFIT energy dataset (2013-2015) and the solar dataset (2017) do not have overlapping time periods**.

**Decision**: We proceeded by building two separate forecasting models—one for energy consumption and one for solar generation—which will be used together in the final optimization stage.

---
## Week 2: Predictive Modeling and Scheduling

The goal of Week 2 was to build and evaluate predictive models for both energy consumption and solar generation, and then use those forecasts to create an optimized appliance schedule.

### Key Activities Completed
* **Model Building & Comparison**: Systematically trained and evaluated multiple models for energy forecasting, including a Naive Baseline, Ridge Regression, Random Forest, and XGBoost.
* **Champion Model Selection**: Identified **XGBoost** as the champion model for energy forecasting, achieving the best performance on the validation set with an **RMSE of 309.21** and an **MAE of 264.47** on the final, unseen test set.
* **Solar Forecast Model**: Successfully trained a separate XGBoost model to predict solar power generation based on weather features.
* **Appliance Scheduling Logic**: Designed and implemented a rule-based scheduling algorithm that uses the outputs from both forecasting models.
* **End-to-End Simulation**: Ran a final simulation that demonstrated the system's ability to generate an optimized schedule for household appliances, successfully maximizing the use of forecasted solar energy.

### Files
* `EdgeFlex_AI.ipynb`: The main Jupyter Notebook containing all the code and analysis for the project.
* `Datasets/`: Folder containing the raw data (tracked using Git LFS).
