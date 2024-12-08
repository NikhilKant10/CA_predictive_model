# Wildfire Prediction and Analysis System Documentation

##Introduction

Wildfires are a growing threat to ecosystems, human lives, and infrastructure worldwide. This analysis aims to provide a comprehensive understanding of wildfire behavior across diverse regions, including California, Queensland, and Amazon Brazil. By leveraging historical wildfire and climate data, this system identifies patterns and trends, analyzes contributing environmental factors, and generates actionable insights to improve fire prevention, containment, and mitigation strategies.

The project integrates advanced machine learning techniques and geospatial analysis to explore correlations between wildfire occurrences and factors such as climate conditions, geographic zones, and seasonal patterns. By offering data-driven solutions, the system empowers decision-makers to optimize resource allocation for effective wildfire management.

## Data Overview

### Data Sources
The analysis uses a combination of wildfire, climate, and vegetation datasets for the regions of focus: California, Amazon, and Queensland. The datasets were sourced from NASA's official website.

## Wildfire Data:
Date and time of wildfire ignition and containment.
Geographic coordinates of wildfire origins and affected areas.
Fire Radiative Power (FRP), brightness, and confidence levels.
Fire size and containment status.
## Climate Data:
Atmospheric conditions such as temperature, humidity, precipitation, and wind speed.
Historical and seasonal weather patterns for the regions of interest.
## Geospatial Data:
Latitude and longitude for zone classification.
Regional boundaries for California, Queensland, and Amazon Brazil.
## Key Data Fields
Date/Time: Start and end dates of wildfire events, along with time of ignition.
Location: Latitude and longitude of fire origins.
Fire Metrics: Brightness, FRP, confidence levels, and fire size.
Climatic Factors: Temperature, relative humidity, wind speed, and precipitation.
Zone Classification: Grouped regions such as Coastal, Mountain, and Savanna.
Seasonality: Monthly and seasonal groupings to identify trends.
Analysis Objectives

The project focuses on deriving meaningful insights for wildfire prevention and management. The objectives include:

## Wildfire Trends:
Analyze monthly, seasonal, and yearly trends for wildfire frequency and size.
Identify peak periods for wildfire occurrences in each region.
## Geospatial Risk Assessment:
Classify regions into zones (e.g., Coastal, Mountain, Savanna) based on latitude and longitude.
Identify wildfire hotspots for each region.
## Environmental Correlations:
Evaluate the impact of temperature, humidity, and wind speed on fire occurrences and severity.
## Impact Analysis:
Assess the economic, social, and environmental impact of wildfires.
## Feature Importance:
Use SHAP values to identify key predictors of wildfire behavior.
Methodology

## 1. Data Cleaning and Preprocessing
Handle missing values and outliers.
Encode categorical variables (e.g., Day-Night cycles, Time Periods).
Create additional features for seasonal and zonal classifications.
## 2. Machine Learning Models
Classification:
MultiOutputClassifier for predicting day-night cycles and time periods.
Regression:
Linear Regression for estimating numerical targets like FRP and fire size.
## 3. Zone Classification

##Custom functions for each region:

California: Central Valley, Coastal, and Mountain zones.
Queensland: Coastal, Savanna, Rainforest, Mountain, and Outback zones.
Amazon Brazil: Rainforest, Savanna, and Other zones.
## 4. SHAP Analysis
Generate feature importance and interaction plots to interpret key predictors like Temperature_Max and Relative_Humidity.
## 5. Trend Analysis
Monthly, seasonal, and yearly aggregation of wildfire occurrences and FRP values.
Geospatial grouping for regional insights.
Results

1. Wildfire Trends
California: Increased fire frequency and severity since 2010, with peaks during summer and fall.
Queensland: Coastal regions report higher wildfire density in summer.
Amazon Brazil: Peak wildfire activity observed in the dry season (August–September).
2. Geospatial Analysis
Hotspots: High-risk zones identified based on historical data and environmental conditions.
Fire Spread: Zones with strong winds show faster fire spread.
3. SHAP Insights
Temperature_Max and Relative_Humidity are critical predictors across all regions.
Interaction effects reveal how climatic conditions interplay to influence wildfire behavior.
# Usage

Step 1: Preprocessing
Prepare the dataset using the provided preprocessing script:

python preprocessing.py
Step 2: Model Training
Train classification and regression models:

python train_model.py
Step 3: SHAP Analysis
Analyze feature importance:

python shap_analysis.py
Step 4: Trend Analysis
Run trend analysis:

python trend_analysis.py --region Brazil

#Project Structure

wildfire-analysis/
├── data/
│   ├── california_dataset.csv
│   ├── queensland_dataset.csv
│   ├── brazil_dataset.csv
├── scripts/
│   ├── preprocessing.py
│   ├── train_model.py
│   ├── shap_analysis.py
│   ├── trend_analysis.py
│   ├── zone_classifier.py
├── results/
│   ├── shap_plots/
│   ├── trend_visualizations/
│   ├── fire_reports/
├── README.md
├── requirements.txt
## Conclusion

This analysis provides valuable insights into wildfire behavior across diverse geographic regions. By combining predictive modeling with trend and geospatial analysis, the project equips policymakers, emergency responders, and researchers with the tools needed to combat the growing wildfire crisis.
