Of course. Here is a professional `README.md` file that summarizes your work for Week 1. You can copy and paste this into the `README.md` file in your GitHub repository.

---

# EdgeFlex AI: Smart Household Energy Optimization

This repository documents the development of an AI system to forecast household energy consumption and optimize appliance scheduling. This `README` covers the progress made in Week 1.

---
## Week 1: Data Preprocessing and Exploratory Data Analysis

The primary goal of Week 1 was to load, clean, and prepare the project's datasets to make them suitable for machine learning. This foundational stage involved handling missing values, standardizing formats, and engineering new features.

### Key Activities Completed
* **Data Loading & Inspection**: Loaded the REFIT (household energy) and Solar Power (solar generation and weather) datasets and performed an initial inspection to understand their structure, data types, and basic statistics.
* **Data Cleaning**: Standardized column names and converted raw timestamp columns (Unix and string-based) into a proper `DatetimeIndex` for both datasets.
* **Resampling & Alignment**: Resampled the high-frequency (8-second) energy data to an hourly frequency to align with the hourly solar and weather data.
* **Feature Engineering**: Created new time-based features from the `DatetimeIndex` (e.g., hour, day of week, month) to provide the model with cyclical patterns.
* **Data Splitting**: Split the final energy dataset into chronological training (70%), validation (15%), and testing (15%) sets, preserving the time-series order.

### Key Findings & Decisions
A critical finding during the merging step was that the **REFIT energy dataset (2013-2015) and the solar dataset (2017) do not have overlapping time periods**.

**Decision**: Instead of merging the data, we will proceed by building two separate, high-quality forecasting models:
1.  An energy consumption forecasting model using the prepared REFIT data.
2.  A solar generation forecasting model using the solar and weather data.

These two models will be used in conjunction during the final optimization stage.

### Files
* `EdgeFlex_AI.ipynb`: The main Jupyter Notebook containing all the code and analysis for Week 1.
* `Datasets/`: Folder containing the raw data (tracked using Git LFS).

### Next Steps
With the data fully prepared, Week 2 will focus on building, training, and evaluating our first machine learning models to forecast energy consumption.
