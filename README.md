# Norwegian Salmon Lice Data Book #

Salmon lice (Lepeophtheirus salmonis) remain one of the most significant challenges facing the Norwegian salmon industry, with annual costs estimated at around 5 billion NOK. Although lice are not typically a direct cause of mortality, they pose serious welfare concerns for farmed fish and create substantial operational and economic pressure for producers.

This document serves as a comprehensive guide to the dataset and the analytical framework developed to study salmon lice levels in Norwegian aquaculture. Using a range of Python-based analytical tools, the project transforms raw data into structured, meaningful, and actionable insights for researchers, students, and industry professionals. The overarching aim is to support more informed, data-driven decision-making across the sector.

The work is organized into three parts. The first part outlines the rationale behind the analysis and provides a brief overview of the dataset used.

## Rationale and Objective ##

Salmon lice represent one of the most significant biological and economic challenges to the sustainable growth of the global salmon farming industry, particularly in major producing nations like Norway. High infestation levels can compromise fish welfare, increase production costs, and potentially impact wild salmonid populations. The primary objective of this data book is to provide a detailed, data-driven exploration of lice levels across Norwegian salmon farms. By analyzing a decade of weekly data (2015-2025), this study aims to:

1. Characterize the spatial and temporal patterns of sea lice infestation.

2. Identify key factors and environmental conditions associated with high lice counts.

3. Evaluate the effectiveness of management zones and lice limit thresholds.

4. Serve as a foundational resource for predictive modeling and informed decision-making.

## About the Data ##

The dataset used in this analysis is a rich, longitudinal record of salmon lice counts and environmental conditions from individual farm sites across Norway. It is provided in the file Weekly_Count_Salmon_Lice_2015_2025.csv and contains 316,719 observations (rows) and 13 variables (columns), covering the period from early 2015 through late 2025.

The data includes the following key information for each weekly observation per farm:

1. Identifiers: Week, Year, Locality_Number, Locality_Name

2. Lice Counts: Adult_Female_Lice, Mobile_Lice, Attached_Lice (average per fish)

3. Location & Environment: County, Latitude, Longitude, Sea_Temperature

4. Regulatory & Management: Above_Lice_Limit (a binary flag indicating if the action threshold was exceeded), Production_Area

This granular level of data enables a multi-faceted investigation into the dynamics of sea lice infestations.

## Applications ##
The insights derived from this data book can be applied in several important ways:

Research: Provides a baseline for academic studies on parasite epidemiology, climate impacts, and ecological dynamics in marine aquaculture systems.

Industry Management: Offers a data-driven perspective for farm operators to benchmark their performance, understand regional risk factors, and optimize treatment strategies.

Policy Development: Informs policymakers and regulators about the long-term trends and effectiveness of current lice management zones and intervention thresholds (the 0.5 adult female lice threshold).

## Acknowledgements
I gratefully acknowledge the public data sources that made this work possible. The primary data originates from BarentsWatch (www.barentswatch.no), a collaborative platform that provides open access to Norwegian aquaculture data. I also thank the Norwegian Directorate of Fisheries (www.fiskedir.no) and Statistics Norway (SSB) for their foundational work in collecting, maintaining, and disseminating this valuable public information. Their commitment to transparency and open data is essential for advancing knowledge and sustainable practices in the aquaculture industry.

# Predictive Modeling of Sea Lice Outbreaks in Norwegian Salmon Farms (2015-2025)

## Overview
This project presents a comprehensive seven-step analytical framework for predicting sea lice (Lepeophtheirus salmonis) outbreaks in Norwegian salmon aquaculture. Sea lice infestations cost Norway's salmon industry approximately five billion NOK annually, making predictive analytics crucial for sustainable aquaculture management. By analyzing a decade of weekly monitoring data (2015-2025), this study identifies recurrence patterns, temperature dependencies, latitudinal variations, and builds machine learning models to forecast future outbreaks with actionable management calendars.

## STEP 1: Recurrence Pattern Analysis
### Rationale:
To determine whether sea lice outbreaks follow predictable annual cycles at specific locations and identify farms with consistent outbreak timing year after year.

### Methodology:

- Analyzed weekly outbreak patterns across 1,024 localities

- Calculated recurrence ratios for each calendar week across multiple years

- Developed a predictability score combining recurrence frequency and temperature consistency

- Applied statistical significance testing (p<0.05 threshold)

### Tools Used:

1. Pandas for data aggregation

2. Custom recurrence scoring algorithms

3. Folium for interactive mapping

### Key Results:

- 1,024 localities analyzed with mean predictability score of 0.23

- 65% of localities exhibit statistically significant recurrence patterns

- Peak outbreak window identified: Weeks 15-25 (April-June)

- Southern zones show higher predictability than northern regions

- Most predictable locality: Sauaneset I; Least predictable: Aga Ø

## STEP 2: Temperature Pattern Analysis
### Rationale:
To analyze temperature consistency, trends, and thermal ranges across localities and understand how temperature variations influence lice populations.

### Methodology:

- Calculated temperature consistency scores using coefficient of variation

- Performed linear regression to identify warming/cooling trends

- Analyzed temperature ranges during exceedance events

- Examined weekly temperature patterns across years

### Tools Used:

1. SciPy for statistical testing

2. Matplotlib/Seaborn for visualization

3. Time series decomposition

### Key Results:

- Average warming trend: 0.15°C per decade

- Significant trends detected in 287 localities

- Mean exceedance temperature: 9.2°C (range: 6.5°C - 12.8°C)

- Southern zones: warmest (mean 10.5°C); Arctic zones: coldest (mean 7.2°C)

- Temperature consistency highest in mid-Norway zones

## STEP 3: Temperature-Lice Synchrony Analysis
### Rationale:
To identify localities where outbreaks recur with remarkably consistent temperatures, indicating temperature-triggered biological processes.

### Methodology:

- Identified recurrent weeks with temperature variation < 1°C

- Calculated synchrony ratios (synchronized weeks / total recurrent weeks)

- Developed synchrony score combining temperature consistency and predictability

- Analyzed best synchronized weeks for each locality

### Tools Used:

1. Custom synchrony detection algorithms

2. Correlation analysis

3. Multi-criteria scoring systems

### Key Results:

- 843 localities show temperature-synchronized outbreaks

- Average synchrony ratio: 0.47

- Most common synchronized weeks: Weeks 18-22 (early May to late May)

- Synchronized outbreak temperature range: 8.5°C - 10.2°C

- Western zones (60-63°N) show highest synchrony scores

## STEP 4: Latitudinal Zonation Analysis
### Rationale:
To segment the Norwegian coast into biologically meaningful latitudinal zones and characterize zone-specific outbreak dynamics for regional management strategies.

### Methodology:

- Defined five latitudinal zones based on 3-degree increments

- Calculated photoperiod variations for each zone

- Analyzed zone-specific outbreak patterns, temperatures, and seasonality

- Developed composite risk rankings for each zone

### Tools Used:

1. Geographic segmentation algorithms

2. Photoperiod calculation from latitude

3. Composite scoring systems

### Key Results:

Zone	            Latitude	      Exceedance Rate    	Mean Temp	      Predictability	         Photoperiod Variation
Zone 1 (Southern)	58-60°N	         28.5%	             10.5°C	            0.31	                 8.2 hours
Zone 2 (Western)	60-63°N	         24.2%	              9.8°C	            0.28	                 10.5 hours
Zone 3 (Mid)	    63-66°N	         19.7%	              8.9°C	            0.22	                 13.1 hours
Zone 4 (Northern)	66-69°N	         15.3%	              8.0°C	            0.18	                 16.4 hours
Zone 5 (Arctic)	  69-71°N	         11.8%	              7.2°C	            0.12	                 20.8 hours

- Highest risk zone: Southern (28.5% exceedance rate)

- Lowest risk zone: Arctic (11.8% exceedance rate)

- Peak timing shift: Later weeks with increasing latitude

## STEP 5: Environmental Drivers Analysis
### Rationale:
To quantify how environmental factors (temperature, photoperiod) interact to drive outbreak dynamics and identify zone-specific environmental thresholds.

### Methodology:

- Calculated optimal temperature ranges for each zone

- Developed temperature sensitivity curves

- Analyzed temperature-photoperiod interactions

- Quantified outbreak intensity metrics by zone

### Tools Used:

1. Quantile analysis for optimal ranges

2. Correlation matrices

3. Sensitivity analysis

### Key Results:

- Optimal temperature range: 8°C - 11°C (varies by zone)

- Temperature-photoperiod correlation: 0.78 in northern zones, 0.32 in southern zones

- Outbreak intensity: Southern zones show higher lice counts but shorter durations

- Environmental interaction: Photoperiod becomes increasingly important at higher latitudes

## STEP 6: Vulnerability Modeling
### Rationale:
To build machine learning models that predict outbreak vulnerability at the locality level, incorporating environmental drivers, historical patterns, and spatial characteristics.

### Methodology:

Engineered features including:

1. Temperature rolling means

2. Photoperiod estimates

3. Lagged outbreak variables

4. Week sin/cos transformations

5. Zone-specific vulnerability scores

6. Trained and compared multiple ML algorithms

7. Generated locality-level vulnerability scores and risk levels

### Tools Used:

1. Scikit-learn (Random Forest, Gradient Boosting)

2. XGBoost for gradient boosting

3. StandardScaler for feature normalization

4. Train-test split (80/20) with stratification

### Model Performance:

Model	Accuracy	Precision	Recall	F1-Score	AUC-ROC
Random Forest	0.82	0.79	0.76	0.77	0.88
Gradient Boosting	0.81	0.77	0.75	0.76	0.86
XGBoost	0.83	0.80	0.78	0.79	0.89
Top Feature Importances:

Sea Temperature (0.21)

Temperature Rolling Mean (0.16)

Week_Cos (0.12)

Photoperiod Estimate (0.11)

Lice Rolling Mean (0.09)

### Vulnerability Assessment Results:

High/Very High Risk Localities: 342 (33.4%)

Mean Vulnerability Score: 0.47

Most Vulnerable Zone: Southern (mean score 0.62)

Least Vulnerable Zone: Arctic (mean score 0.28)

## STEP 7: Predictive Calendar (2026-2030)
### Rationale:
To generate actionable, locality-specific outbreak forecasts and management calendars for the next five years, enabling proactive intervention strategies.

### Methodology:

- Time series forecasting using ensemble methods

- Multi-step ahead predictions with confidence intervals

- Locality-specific adjustments using vulnerability scores

- Generation of management actions based on risk levels

- Export of calendars in multiple formats (CSV, JSON, text)

### Tools Used:

- XGBoost Regressor for time series

- Random Forest Regressor for ensemble

- TimeSeriesSplit for validation

- Plotly for interactive visualizations

### 2026 Predictions Summary:

Zone	     Overall Risk	       Season Start	      Season End	    Peak Week	         High-Risk Weeks
Southern	 32.4%	              Week 14	           Week 30	       Week 20	                8 
Western	   28.7%	              Week 15	           Week 29	       Week 21	                6
Mid	       22.1%	              Week 16	           Week 28	       Week 22	                4
Northern	 18.5%	              Week 18	           Week 27	       Week 23	                3
Arctic	   14.2%	              Week 20	           Week 26	       Week 24	                2
- Total predicted high-risk weeks (2026): 23 weeks across all zones
- Highest predicted risk zone: Southern (32.4% average risk)
- Predicted trend (2026-2030): ↑ Increasing risk in northern zones, → Stable in southern zones

### Management Recommendations
- Zone-Specific Strategies
Southern Zones (1-2): Focus on early detection, temperature monitoring, and coordinated regional treatments during weeks 15-25

Mid Zones (3): Transition zone requiring adaptive strategies based on seasonal forecasts

Northern Zones (4-5): Pre-emptive treatments before short warm seasons; maximize narrow treatment windows

- Monitoring Schedule
High Risk Zones: Weekly monitoring (April-September)

Medium Risk Zones: Bi-weekly monitoring (May-August)

Low Risk Zones: Monthly monitoring (June-July)

- Treatment Protocols
Time treatments using predictive calendar (2 weeks before predicted peak)

Coordinate treatments within zones to prevent re-infestation

Consider temperature thresholds (8°C-11°C) when planning treatments

- Biosecurity Measures
Enhanced measures in high-risk zones during critical weeks

Regular equipment disinfection between farm visits

Monitor water exchange patterns between neighboring farms

- Data Collection Priorities
Continue weekly temperature monitoring

Record treatment dates, methods, and outcomes

Share data regionally for model improvement

### Technical Tools & Libraries
- Category	Tools Used
- Data Processing	Pandas, NumPy
- Visualization	Matplotlib, Seaborn, Plotly, Folium
- Geospatial	Folium, HeatMap, MarkerCluster
- Machine Learning:	Scikit-learn, XGBoost
- Statistical Analysis	SciPy, StatsModels
- Time Series:	TimeSeriesSplit, SARIMAX, ExponentialSmoothing
- Output Formats	CSV, JSON, HTML, PNG, TXT
- Key Findings Summary
- Predictable Cycles: 65% of Norwegian salmon farms show statistically significant recurrent outbreak patterns, primarily during weeks 15-25 (April-June)

- Temperature Threshold: Lice exceedances typically occur at 9.2°C (range: 6.5°C-12.8°C), with remarkable temperature consistency at synchronized farms

- Latitudinal Gradient: Clear north-south gradient in outbreak risk (28.5% in south vs. 11.8% in arctic), timing (later with higher latitude), and predictability (higher in south)

- Machine Learning Performance: XGBoost achieved 0.83 accuracy and 0.89 AUC-ROC in predicting outbreaks, with temperature and seasonality as top predictors

- Vulnerability Hotspots: 342 localities (33.4%) classified as high/very high risk, concentrated in southern and western zones

- 2026 Forecast: Southern zone predicted highest risk (32.4%), with peak outbreak week 20 (mid-May); northern zones show increasing risk trend through 2030

## Conclusion
This seven-step analytical framework successfully demonstrates that sea lice outbreaks in Norwegian salmon aquaculture follow predictable patterns driven by temperature, seasonality, and latitudinal gradients. By integrating recurrence analysis, temperature profiling, synchrony detection, and machine learning, we have created a robust predictive system that identifies vulnerable localities up to five years in advance.

The practical outputs—zone-specific risk assessments, locality-level vulnerability scores, and a week-by-week management calendar for 2026-2030—provide actionable intelligence for the aquaculture industry. Implementation of these predictive insights could significantly reduce chemical treatments, improve fish welfare, and enhance farm profitability while supporting sustainable aquaculture practices in Norway.

The framework transforms 10 years of monitoring data into a proactive management tool, potentially saving the industry hundreds of millions of NOK annually through optimized treatment timing and resource allocation.

## Deliverables
File	Description:
recurrence_pattern_map_complete.html	Interactive map of outbreak predictability
temperature_patterns_map.html	Temperature consistency and trend map
temperature_synchrony_map.html	Temperature-synchronized outbreaks map
zone_analysis_map.html	Latitudinal zone visualization
vulnerability_map.html	Risk heatmap with locality-level vulnerability
zone_predictions_2026_2030.csv	Zone-level weekly predictions
locality_predictions_2026.csv	Locality-specific 2026 forecasts
management_calendar_2026.json	Structured management recommendations
management_calendar_2026.txt	Printable management calendar






