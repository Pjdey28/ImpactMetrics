# Air Quality Analytics and Monitoring Network Assessment

## Overview

This project presents a comprehensive analytical framework for studying air pollution patterns, pollutant interactions, emission source attribution, and monitoring station reliability across Indian cities using Python and Power BI.

The workflow integrates data preprocessing, statistical analysis, machine learning techniques, dimensionality reduction, clustering, and interactive dashboard development to generate actionable insights for environmental monitoring and policy interpretation.

The project was designed to move beyond simple AQI reporting by identifying:
- Temporal and spatial pollution trends
- Dominant emission signatures
- Pollutant relationships
- Monitoring infrastructure weaknesses
- Reliability and consistency of air quality stations



# Problem Statement

Air quality datasets often contain:
- Missing observations
- Inconsistent reporting
- Sensor anomalies
- Multi-dimensional pollutant relationships
- Regional variation in pollution sources

Traditional AQI analysis measures pollution severity but does not explain:
- Why pollution occurs
- Which pollutants dominate
- Whether monitoring data is reliable
- How pollution patterns differ structurally across cities

This project addresses these challenges using a data-driven analytical pipeline.



# Objectives

The primary objectives of this project are:

- Analyze long-term air pollution trends across Indian cities
- Study pollutant correlations and co-emission behavior
- Reduce dimensional complexity using PCA
- Cluster cities based on pollutant signatures
- Perform pollution source attribution
- Evaluate station-level reliability and data quality
- Build interactive dashboards for environmental analysis
- Generate policy-oriented insights



# Dataset Description

The project uses cleaned city-level and station-level air quality datasets containing:
- PM2.5
- PM10
- NO2
- SO2
- O3
- CO
- NH3
- AQI
- Date and location information

Datasets processed:
- `city_day_clean.csv`
- `station_day_clean.csv`
- `station_hour_clean.csv`



# Technologies Used

## Programming and Analytics
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## Visualization and Dashboarding
- Power BI

## Machine Learning and Statistical Methods
- Principal Component Analysis (PCA)
- K-Means Clustering
- Silhouette Score Optimization
- Correlation Analysis
- Z-Score Outlier Detection



# Project Workflow

## 1. Data Preprocessing

The preprocessing stage focused on improving data consistency and usability.

Tasks performed:
- Removed invalid pollutant values
- Standardized timestamps
- Cleaned inconsistent column names
- Handled missing observations
- Applied interpolation for short gaps
- Generated cleaned station-level and city-level datasets

Outputs:
- `city_day_clean.csv`
- `station_day_clean.csv`
- `station_hour_clean.csv`



# 2. Exploratory Data Analysis

Exploratory analysis was performed to understand pollutant distributions and interdependencies.

### Correlation Analysis
Both Pearson and Spearman correlations were computed to identify:
- Linear relationships
- Monotonic relationships
- Co-emission patterns

Generated outputs:
- Pearson correlation heatmap
- Spearman correlation heatmap

### Trend Analysis
Analyzed:
- City-level AQI trends
- Seasonal pollution variation
- Pollutant concentration patterns



# 3. Principal Component Analysis (PCA)

Air quality data contains multiple correlated pollutants.

PCA was applied to:
- Reduce dimensionality
- Remove redundancy
- Capture major pollution variation patterns

### PCA Workflow
- Standardized pollutant features using `StandardScaler`
- Computed principal components
- Evaluated explained variance
- Generated scree plots
- Visualized cities in reduced-dimensional PCA space

Generated outputs:
- PCA scores
- PCA loadings
- PCA scatter plots
- Scree plot



# 4. Clustering and Source Attribution

K-Means clustering was used to group cities with similar pollution characteristics.

### Cluster Optimization
The optimal number of clusters was selected using:
- Silhouette Score

### Cluster Interpretation
Clusters were labeled using pollutant dominance heuristics:

| Dominant Pollutant Pattern | Emission Type |
|---|---|
| High NO2 and CO | Vehicular |
| High SO2 | Industrial |
| High PM2.5 and PM10 | Biomass / Crop Burning |
| High PM10 dominance | Dust / Construction |

### Cluster Confidence
A cluster confidence score was computed to quantify:
- Strength of dominant pollutant contribution
- Reliability of source attribution

Generated outputs:
- Cluster summaries
- Cluster center profiles
- Emission category maps
- PCA cluster visualizations



# 5. Station Reliability and Data Quality Audit

A dedicated station audit framework was developed to assess monitoring reliability.

## Reliability Metrics

### Data Completeness
Measured percentage of available observations.

### Coverage Gap Analysis
Detected:
- Reporting interruptions
- Long downtime periods
- Operational gaps

### Variability Analysis
Measured daily pollutant variability to detect:
- Frozen sensors
- Repeated measurements
- Unusual stability

### Outlier Detection
Used rolling z-score analysis to identify:
- Extreme spikes
- Sensor anomalies
- Abnormal fluctuations

### Stuck Sensor Detection
Hourly data was analyzed to identify prolonged sequences of identical readings.

### Inter-Station Consistency
Compared stations within the same city using:
- Mean absolute PM2.5 disagreement

### Composite Reliability Score
A weighted reliability score was computed using:
- Completeness
- Uptime
- Variability
- Outlier frequency

Generated outputs:
- Station audit summary
- Outlier summary
- Stuck sensor summary
- Inter-station consistency report



# Dashboard Development

Interactive Power BI dashboards were created to visualize:
- AQI trends
- Pollutant heatmaps
- PCA cluster distributions
- Emission source attribution
- Reliability score analysis
- Coverage gaps
- Inter-station disagreement
- Monitoring infrastructure quality

Dashboard features include:
- Geospatial analysis
- Cluster-based filtering
- Interactive drill-downs
- Comparative station analysis



# Key Insights

- Strong correlations exist between PM2.5 and PM10 across multiple cities.
- Vehicular and industrial signatures dominate major urban regions.
- Certain stations exhibit prolonged downtime and low reporting consistency.
- Inter-station disagreement highlights calibration and placement variability.
- PCA effectively separates pollution structures into interpretable clusters.


