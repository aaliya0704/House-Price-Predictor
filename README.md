# House Price Predictor

A machine learning project that aims to predict median house values in California using Python and Scikit-learn. The project begins with exploratory data analysis (EDA) to understand the dataset, identify patterns, and prepare for model development.

**Current Status:** EDA Completed | Model Development Pending

## Dataset

This project uses the California Housing dataset provided by Scikit-learn.

* **Observations:** 20,640
* **Input Features:** 8
* **Target Variable:** `MedHouseVal`
* **Geographic Coverage:** California, USA
* **Data Format:** Pandas DataFrame

Each observation represents a California census block group rather than an individual house.

### Features

| Feature       | Description                              |
| ------------- | ---------------------------------------- |
| `MedInc`      | Median household income                  |
| `HouseAge`    | Median house age                         |
| `AveRooms`    | Average rooms per household              |
| `AveBedrms`   | Average bedrooms per household           |
| `Population`  | Total district population                |
| `AveOccup`    | Average household occupancy              |
| `Latitude`    | Geographic latitude                      |
| `Longitude`   | Geographic longitude                     |
| `MedHouseVal` | Median house value, in units of $100,000 |

**Important:** The target variable is capped at approximately $500,000, limiting the model's ability to learn actual values above this threshold.

## Exploratory Data Analysis

### Data Inspection and Cleaning

Inspected the dataset's structure, dimensions, column names, data types, missing values, and duplicate records. Examined descriptive statistics to understand feature ranges and variability.

### Feature Distribution Analysis

Used histograms to examine the distributions of numerical features. Several features, including `MedInc`, `AveRooms`, `AveBedrms`, `Population`, and `AveOccup`, exhibit right-skewed distributions or extreme values. House age also shows a concentration at the recorded maximum of 52 years.

### Target Variable Distribution

Analyzed the distribution of `MedHouseVal`. Most districts have recorded median house values around $100,000–$200,000. A prominent accumulation at $500,000 reveals the dataset's upper-value cap.

### Feature-Target Relationships

Used scatter plots to investigate relationships between individual features and median house values. `MedInc` shows a clear positive relationship with the target, while the relationships involving other features are less apparent in the initial visualizations.

### Correlation Analysis

Calculated and visualized the Pearson correlation matrix to examine linear relationships between numerical features.

Key findings:

* `MedInc` has the strongest positive correlation with `MedHouseVal` (**0.688**).
* `AveRooms` and `AveBedrms` are strongly correlated (**0.848**).
* `Latitude` and `Longitude` have a strong negative correlation (**-0.925**).

### Geographic Distribution of Housing Values

Visualized housing values using latitude and longitude coordinates. The plot reveals geographical clusters of higher- and lower-value districts, suggesting that location may provide useful predictive information.

### Outlier Analysis

Used box plots to investigate `AveRooms`, `AveOccup`, and `Population`. The analysis revealed numerous potential outliers, including unusually high average occupancy values. These observations require careful consideration rather than automatic removal.

### Income vs. Median House Value

Examined the relationship between `MedInc` and `MedHouseVal` in greater detail. The scatter plot confirms a strong positive trend, while the horizontal band at $500,000 illustrates the target-value cap.

## Key Findings

* Median income is the strongest linearly correlated feature with median house value.
* Housing values exhibit geographical patterns across California.
* Several features contain skewed distributions and extreme observations.
* Some input features are strongly correlated with one another.
* The $500,000 target cap limits the information available for learning higher house values.

These findings will inform feature preparation and model evaluation.

## Technologies Used

* **Python** — Programming language
* **Pandas** — Data manipulation and analysis
* **NumPy** — Numerical operations
* **Matplotlib** — Data visualization
* **Seaborn** — Correlation heatmaps
* **Scikit-learn** — Dataset loading and machine learning

## Next Steps

* Prepare input features (`X`) and target (`y`).
* Split the dataset into training and testing sets.
* Train a baseline Linear Regression model.
* Evaluate predictions using MAE, RMSE, and R².
* Investigate potential improvements and compare alternative models.

## Project Status

* [x] Dataset inspection and initial cleaning
* [x] Exploratory data analysis and visualizations
* [x] Correlation and geographic analysis
* [x] Outlier investigation
* [ ] Feature and target preparation
* [ ] Model training and evaluation
* [ ] Model improvement and comparison

## Conclusion

The EDA phase established a foundation for predicting California housing values. Median income emerged as a particularly informative feature, while geographic patterns, extreme observations, and the target-value cap were identified as important considerations for model development.
