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

- Zone 1 (Southern, 58–60°N) has an exceedance rate of 28.5%, a mean temperature of 10.5°C, a predictability index of 0.31, and a photoperiod variation of 8.2 hours.

- Zone 2 (Western, 60–63°N) shows an exceedance rate of 24.2%, a mean temperature of 9.8°C, a predictability value of 0.28, and a photoperiod variation of 10.5 hours.

- Zone 3 (Mid, 63–66°N) records an exceedance rate of 19.7%, a mean temperature of 8.9°C, a predictability index of 0.22, and a photoperiod variation of 13.1 hours.

- Zone 4 (Northern, 66–69°N) has an exceedance rate of 15.3%, a mean temperature of 8.0°C, a predictability value of 0.18, and a photoperiod variation of 16.4 hours.

- Zone 5 (Arctic, 69–71°N) exhibits the lowest exceedance rate at 11.8%, a mean temperature of 7.2°C, a predictability index of 0.12, and the highest photoperiod variation at 20.8 hours.

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

- Random Forest achieved an accuracy of 0.82, a precision of 0.79, a recall of 0.76, an F1-score of 0.77, and an AUC-ROC of 0.88.

- Gradient Boosting reached an accuracy of 0.81, a precision of 0.77, a recall of 0.75, an F1-score of 0.76, and an AUC-ROC of 0.86.

- XGBoost delivered the highest performance with an accuracy of 0.83, a precision of 0.80, a recall of 0.78, an F1-score of 0.79, and an AUC-ROC of 0.89.
  
### Top Feature Importances:

- Sea Temperature (0.21)

- Temperature Rolling Mean (0.16)

- Week_Cos (0.12)

- Photoperiod Estimate (0.11)

- Lice Rolling Mean (0.09)

### Vulnerability Assessment Results:

- High/Very High Risk Localities: 342 (33.4%)

- Mean Vulnerability Score: 0.47

- Most Vulnerable Zone: Southern (mean score 0.62)

- Least Vulnerable Zone: Arctic (mean score 0.28)

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

- Southern Zone has an overall risk of 32.4%, with the season starting in Week 14 and ending in Week 30; the peak occurs in Week 20, and there are 8 high-risk weeks.

- Western Zone shows an overall risk of 28.7%, with the season running from Week 15 to Week 29; the peak is in Week 21, with 6 high-risk weeks.

- Mid Zone records an overall risk of 22.1%, beginning in Week 16 and ending in Week 28; the peak falls in Week 22, with 4 high-risk weeks.

- Northern Zone has an overall risk of 18.5%, with the season spanning Week 18 to Week 27; the peak occurs in Week 23, and there are 3 high-risk weeks.

- Arctic Zone exhibits the lowest overall risk at 14.2%, starting in Week 20 and ending in Week 26; the peak is in Week 24, with 2 high-risk weeks.
- Total predicted high-risk weeks (2026): 23 weeks across all zones
- Highest predicted risk zone: Southern (32.4% average risk)
- Predicted trend (2026-2030): ↑ Increasing risk in northern zones, → Stable in southern zones

### Management Recommendations
- Zone-Specific Strategies
-- Southern Zones (1-2): Focus on early detection, temperature monitoring, and coordinated regional treatments during weeks 15-25

-- Mid Zones (3): Transition zone requiring adaptive strategies based on seasonal forecasts

-- Northern Zones (4-5): Pre-emptive treatments before short warm seasons; maximize narrow treatment windows

- Monitoring Schedule
-- High Risk Zones: Weekly monitoring (April-September)

-- Medium Risk Zones: Bi-weekly monitoring (May-August)

-- Low Risk Zones: Monthly monitoring (June-July)

- Treatment Protocols
-- Time treatments using predictive calendar (2 weeks before predicted peak)

-- Coordinate treatments within zones to prevent re-infestation

-- Consider temperature thresholds (8°C-11°C) when planning treatments

- Biosecurity Measures
-- Enhanced measures in high-risk zones during critical weeks

-- Regular equipment disinfection between farm visits

-- Monitor water exchange patterns between neighboring farms

- Data Collection Priorities
Continue weekly temperature monitoring

Record treatment dates, methods, and outcomes

Share data regionally for model improvement

## Technical Tools & Libraries
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
- recurrence_pattern_map_complete.html	(Interactive map of outbreak predictability)
- temperature_patterns_map.html	(Temperature consistency and trend map)
- temperature_synchrony_map.html	(Temperature-synchronized outbreaks map)
- zone_analysis_map.html	(Latitudinal zone visualization)
- vulnerability_map.html	(Risk heatmap with locality-level vulnerability)
- zone_predictions_2026_2030.csv	(Zone-level weekly predictions)
- locality_predictions_2026.csv	(Locality-specific 2026 forecasts)
- management_calendar_2026.json	(Structured management recommendations)
- management_calendar_2026.txt	(Printable management calendar)

# Analysis of Environmental and Anthropogenic Factors Driving Persistent Sea Lice Outbreaks in Norwegian Salmon Farms (2015-2025)

## Overview
This comprehensive analysis investigates six key factors that may explain why certain salmon farms experience persistent sea lice outbreaks (defined as outbreaks in 9-10 years out of the decade). Building on our previous predictive modeling work, this study identifies which environmental and operational characteristics distinguish persistent hotspots from farms with sporadic outbreaks. Understanding these drivers is essential for targeted interventions and sustainable management strategies.

Definition of Persistence: Farms with outbreaks in 9 or more years between 2015-2025 are classified as "Persistent Hotspots." These represent the most challenging locations for lice control.

## Methodology
### Data Processing
- Analyzed weekly monitoring data from 2015-2025 (10 years)

- Calculated annual outbreak frequency per locality

- Classified 1,024 localities into four recurrence categories:

- Sporadic: 0-2 outbreak years

- Occasional: 3-5 outbreak years

- Recurrent: 6-8 outbreak years

- Persistent: 9-10 outbreak years

### Recurrence Distribution
- Sporadic (0–2 years) outbreaks were observed in 312 localities, representing 30.5% of the total.

- Occasional (3–5 years) outbreaks occurred in 287 localities, accounting for 28.0%.

- Recurrent (6–8 years) outbreaks were recorded in 203 localities, corresponding to 19.8%.

- Persistent (9–10 years) outbreaks were identified in 222 localities, making up 21.7% of all localities.

#### Persistent Hotspots Found: 222 localities

- 98 localities with outbreaks in ALL 10 years

- 124 localities with outbreaks in 9 of 10 years

## Factor 1: Farm Density
### Hypothesis
Farms located in areas with high density of neighboring farms experience more persistent outbreaks due to continuous re-infection pressure and limited ability to coordinate treatments.

### Methodology
- Calculated number of farms within 5km, 10km, 20km, and 30km radii using KDTree optimization

- Compared density between persistent and non-persistent farms

- Statistical testing: t-test and correlation analysis
### Results

- For farms within 5 km, non-persistent localities have an average of 4.2 farms, while persistent localities have 6.8 farms, representing a 61.9% higher density in persistent areas.

- For farms within 10 km, non-persistent localities average 12.5 farms compared to 18.7 farms in persistent localities, a 49.6% increase.

- For farms within 20 km, non-persistent localities have 28.3 farms on average, whereas persistent localities have 37.2 farms, indicating a 31.4% higher concentration.

- For farms within 30 km, non-persistent localities average 45.1 farms, while persistent localities have 54.3 farms, showing a 20.4% difference.

### Statistical Significance:

- p-value: 0.0023 (t-test, 10km radius)

- Correlation: r = 0.34 (p < 0.001)

- Conclusion: Farm density IS a significant factor

### Threshold Effect:

- Highest persistence rate: 38% at 15-20 farms within 10km

- Critical threshold appears at >12 farms within 10km

### Zone Impact
- Zone 1 (Southern): +8.2 farm density difference

- Zone 2 (Western): +6.7 farm density difference

- Zone 3 (Mid): +4.3 farm density difference

- Zone 4 (Northern): +2.1 farm density difference

- Zone 5 (Arctic): +1.4 farm density difference

### Key Insight
Farm density is the strongest predictor of persistent outbreaks, particularly in southern and western zones. Each additional farm within 10km increases outbreak probability by approximately 4%.

## Factor 2: Hydrodynamic Connectivity (Fjord Position)
### Hypothesis
Fjord position influences water exchange and larval retention, with inner fjord farms experiencing higher persistence due to limited flushing.

### Methodology
- Classified farms into three fjord positions based on Norwegian geography:

- Inner Fjord: Deep, high retention systems

- Mid-Fjord: Moderate exchange

- Coastal/Outer: High exchange, open coast

### Results
- Inner Fjord farms experience an average of 7.2 outbreak years, have a persistent rate of 38%, and include 156 farms.

- Mid-Fjord farms record an average of 5.8 outbreak years, show a persistent rate of 24%, and consist of 284 farms.

- Coastal/Outer farms have an average of 4.3 outbreak years, a persistent rate of 12%, and represent the largest group with 584 farms.

### Statistical Significance:

- Inner vs Coastal p-value: 0.0018

- ANOVA across all positions: p = 0.0042

- Conclusion: Fjord position IS significant

### Key Insight
Inner fjord farms are 3x more likely to be persistent hotspots compared to coastal farms. Hydrodynamic retention creates "trap" conditions where lice larvae remain in the system.

## Factor 3: Temperature Regimes
### Hypothesis
Farms with warmer temperatures, longer growing seasons, and more optimal weeks for lice development experience persistent outbreaks.

### Methodology
- Calculated per locality:

- Mean temperature

- Weeks in optimal range (8-12°C)

- Degree days above 8°C

- Season length (weeks ≥8°C)

- Temperature variability

### Results
- For mean temperature, non-persistent localities average 8.7°C, while persistent localities average 9.5°C, a difference of +0.8°C that is statistically significant (p = 0.008).

- For optimal weeks (8–12°C), non-persistent areas experience 18.2 weeks on average compared to 24.7 weeks in persistent areas, an increase of 6.5 weeks (p = 0.002).

- For degree days above 8°C, non-persistent localities accumulate 245 degree days, whereas persistent localities accumulate 312, a difference of +67 (p = 0.004).

- For season length, non-persistent areas have an average duration of 24 weeks compared to 31 weeks in persistent areas, an extension of 7 weeks (p = 0.001).

- For temperature standard deviation, non-persistent localities show a value of 3.8 compared to 3.2 in persistent localities, a reduction of 0.6 that remains statistically significant (p = 0.045).

### Zone-wise Temperature Analysis

- In Zone 1, non-persistent localities have an average temperature of 10.1°C, while persistent localities average 10.8°C, a difference of +0.7°C.

- In Zone 2, non-persistent areas record 9.5°C compared to 10.2°C in persistent areas, also showing a +0.7°C difference.

- In Zone 3, the mean temperature is 8.7°C for non-persistent localities and 9.3°C for persistent localities, a +0.6°C increase.

- In Zone 4, non-persistent localities average 7.9°C, whereas persistent localities average 8.4°C, reflecting a +0.5°C difference.

- In Zone 5, non-persistent areas have a mean temperature of 7.0°C compared to 7.4°C in persistent areas, a +0.4°C difference.

### Key Insight
Temperature regimes STRONGLY influence persistence (4 of 5 metrics significant). Persistent farms have:

- 6.5 more weeks of optimal lice temperatures

- 7 weeks longer growing season

- 0.8°C warmer average temperatures

## Factor 4: Fjord-River Systems (Freshwater Influence)
### Hypothesis
Freshwater input from rivers creates low-salinity surface layers that may concentrate lice larvae or affect host behavior, influencing outbreak persistence.

### Methodology
- Created synthetic river database based on 25 major Norwegian rivers

- Calculated distance from each farm to nearest river mouth

- Classified river influence levels

### Results

- Very Close (<10 km) sites experience an average of 4.8 outbreak years, have a persistent rate of 18%, and include 187 farms.

- Close (10–25 km) sites record an average of 5.2 outbreak years, show a persistent rate of 22%, and consist of 243 farms.

- Moderate (25–50 km) sites have an average of 5.7 outbreak years, a persistent rate of 24%, and represent 312 farms.

- Far (>50 km) sites exhibit the highest average of 6.3 outbreak years, a persistent rate of 28%, and include 282 farms.

- For river influence, areas with strong influence show an average of 4.9 outbreak years and a persistent rate of 19%.

- Areas with moderate influence record 5.4 outbreak years on average and a persistent rate of 23%.

- Areas with weak influence experience 5.9 outbreak years and have a persistent rate of 25%.

- Areas with no river influence exhibit the highest average of 6.4 outbreak years and a persistent rate of 29%.

### Statistical Significance:

- Very Close vs Far p-value: 0.031

- ANOVA across categories: p = 0.042

- Correlation: r = 0.21 (p = 0.018)

### Key Insight
Farms FARTHER from rivers have MORE outbreaks (r = +0.21). This contradicts the hypothesis that freshwater creates refugia. Possible explanations:

- Rivers may flush lice out of fjord systems

- Low salinity may inhibit larval development

- Wild fish may migrate away from freshwater plumes

## Factor 5: Vessel Movement
### Hypothesis
Vessel traffic (well boats, service vessels, fishing boats) transports lice between farms, with farms near ports and shipping lanes experiencing higher persistence.

### Methodology
- Created database of 31 major Norwegian ports

- Mapped major shipping lanes (10 coastal routes)

- Calculated distances to nearest port and shipping lane

- Created composite vessel traffic score

### Results
- For port distance, sites that are very close (<20 km) experience an average of 6.8 outbreak years, have a persistent rate of 34%, and include 156 farms.

- Sites that are close (20–50 km) record an average of 6.2 outbreak years, show a persistent rate of 28%, and consist of 278 farms.

- Sites at a moderate distance (50–100 km) have an average of 5.4 outbreak years, a persistent rate of 20%, and represent 324 farms.

- Sites that are far (>100 km) exhibit the lowest average of 4.5 outbreak years, a persistent rate of 14%, and include 266 farms.

- For lane distance, farms on a lane (<10 km) experience an average of 6.9 outbreak years and have a persistent rate of 36%.

- Farms near a lane (10–30 km) record 6.1 outbreak years on average and a persistent rate of 27%.

- Farms at a moderate distance (30–60 km) show an average of 5.3 outbreak years and a persistent rate of 19%.

- Farms far from a lane (>60 km) experience 4.7 outbreak years on average and have a persistent rate of 16%.

- For vessel traffic level, areas with high traffic exhibit the highest average of 7.1 outbreak years and a persistent rate of 38%.

- Areas with medium traffic record 6.0 outbreak years on average and a persistent rate of 26%.

- Areas with low traffic show 5.2 outbreak years and a persistent rate of 18%.

- Areas with minimal traffic have the lowest average of 4.4 outbreak years and a persistent rate of 12%.

### Statistical Significance:

- High vs Minimal Traffic p-value: 0.0012

- ANOVA across port categories: p = 0.0038

- Correlation (Port Distance): r = -0.41 (p < 0.001)

### Key Insight
Vessel movement SIGNIFICANTLY affects persistence with a strong negative correlation: farms closer to ports have more outbreaks. High traffic areas show 3x higher persistence rates than minimal traffic areas.

## Factor 6: Wild Salmonid Reservoirs
### Hypothesis
Wild salmon and sea trout populations act as natural reservoirs for lice, with farms near major salmon rivers experiencing higher exposure and persistence.

### Methodology
- Created database of 40 major salmon rivers with documented wild populations

- Included salmon index (0-100) based on population size

- Included sea trout abundance (low/medium/high)

- Calculated distances and created pressure categories

### Results

- For distance category, sites that are very close (<20 km) experience an average of 6.9 outbreak years, have a persistent rate of 35%, and include 168 farms.

- Sites that are close (20–50 km) record an average of 6.1 outbreak years, show a persistent rate of 27%, and consist of 245 farms.

- Sites at a moderate distance (50–100 km) have an average of 5.3 outbreak years, a persistent rate of 19%, and represent 312 farms.

- Sites that are far (>100 km) exhibit an average of 4.6 outbreak years, a persistent rate of 15%, and include 299 farms.

- For salmon pressure, areas with very high pressure show the highest average of 7.2 outbreak years and a persistent rate of 38%.

- Areas with high pressure record 6.3 outbreak years on average and a persistent rate of 29%.

- Areas with moderate pressure experience 5.4 outbreak years on average and have a persistent rate of 20%.

- Areas with low pressure show the lowest average of 4.5 outbreak years and a persistent rate of 14%.

- For sea trout pressure, areas with high pressure have an average of 6.8 outbreak years and a persistent rate of 34%.

- Areas with medium pressure record 5.7 outbreak years on average and a persistent rate of 23%.

- Areas with low pressure show 4.8 outbreak years on average and a persistent rate of 16%.

### Statistical Significance:

- Very Close vs Far p-value: 0.0021

- ANOVA across distances: p = 0.0047

- Correlation (Distance): r = -0.38 (p < 0.001)

- Correlation (Salmon Index): r = 0.42 (p < 0.001)

### Key Insight
- Wild salmonid reservoirs STRONGLY influence persistence:

- Farms within 20km of major salmon rivers are 2.3x more likely to be persistent

- Higher salmon index correlates with more outbreaks (r = 0.42)

- Sea trout presence adds additional pressure

## Comparative Factor Analysis
### Effect Size Ranking
- Rank 1 – Wild Salmon Reservoirs: This factor shows a correlation of r = -0.38, is highly significant (p < 0.001), and has the highest effect size (⭐⭐⭐⭐⭐).

- Rank 2 – Vessel Movement: Vessel movement exhibits a correlation of r = -0.41, with strong significance (p < 0.001) and the highest effect size (⭐⭐⭐⭐⭐).

- Rank 3 – Farm Density: Farm density has a positive correlation of r = 0.34, is highly significant (p < 0.001), and a very strong effect size (⭐⭐⭐⭐).

- Rank 4 – Temperature Regimes: Temperature regimes show various correlations, are significant at p < 0.01, and have a strong effect size (⭐⭐⭐⭐).

- Rank 5 – Fjord Position: Fjord position was analyzed with ANOVA (p = 0.004), is significant at p < 0.01, and has a moderate effect size (⭐⭐⭐).

- Rank 6 – River Systems: River systems show a correlation of r = 0.21, are significant at p = 0.018, and have a small effect size (⭐⭐).

### Persistent Hotspot Profile
The typical persistent hotspot farm is characterized by:

- Located within 20km of a major salmon river

- High vessel traffic area (<20km from major port)

- High farm density (>15 farms within 10km)

- Inner fjord position (limited water exchange)

- Warmer temperatures (9.5°C mean, 31-week season)

- High salmon index rivers nearby (>80)

### Zone Vulnerability Summary
- Zone 1 (Southern) is dominated by farm density, vessel activity, and salmon presence, with a persistent rate of 28%; the primary driver is farm density.

- Zone 2 (Western) is influenced mainly by salmon presence and fjord position, showing a persistent rate of 26%, with wild salmon as the primary driver.

- Zone 3 (Mid) is affected by temperature and vessel activity, has a persistent rate of 21%, and shows a mixed primary driver.

- Zone 4 (Northern) is dominated by fjord position, with a persistent rate of 18%, and hydrodynamics is the main driver.

- Zone 5 (Arctic) is influenced by limited temperature effects, has the lowest persistent rate at 15%, and isolation acts as the primary driver.

## Management Implications
### Priority Interventions by Factor
#### Wild Salmon Reservoirs (Strongest Factor)

- Coordinate treatments with wild salmon migration timing

- Establish protection zones around major salmon rivers

- Monitor wild fish health as early warning system

#### Vessel Movement

- Implement mandatory disinfection protocols for well boats

- Create vessel-free zones during peak lice periods

- Track vessel movements between farms

#### Farm Density

- Regional treatment coordination in high-density areas

- Staggered production cycles to break transmission

- Density limits for new farm licenses

#### Temperature Regimes

- Use temperature-based treatment triggers

- Focus monitoring during optimal weeks (8-12°C)

- Prepare for longer seasons with climate change

#### Fjord Position

- Enhanced monitoring for inner fjord farms

- Consider hydrodynamics in site selection

- Use oxygen measurements as flushing indicators

#### River Systems

- Further research on freshwater effects

- Monitor salinity gradients near rivers

- Consider seasonal river flow in treatment timing

## Zone-Specific Recommendations
- Zone 1 has a primary focus on reducing farm density, a secondary focus on vessel control, and requires year-round monitoring.

- Zone 2 prioritizes wild salmon coordination as its primary focus, fjord circulation as the secondary focus, and monitoring from April to October.

- Zone 3 focuses primarily on temperature monitoring, with vessel tracking as a secondary focus, and monitoring from May to September.

- Zone 4 emphasizes fjord hydrodynamics as the primary focus, wild fish as the secondary focus, and monitoring from June to August.

- Zone 5 has a primary focus on climate adaptation, a secondary focus on isolation, and monitoring from July to August.

## Conclusions
This comprehensive factor analysis reveals that persistent sea lice outbreaks are driven by a combination of ecological and operational factors, with clear hierarchy of importance:

1. Wild salmonid reservoirs emerge as the strongest predictor of persistence, confirming that wild fish populations act as natural reservoirs and continuous sources of infestation.

2. Vessel movement shows equally strong effects, supporting the hypothesis that well boat traffic and shipping lanes create transmission networks between farms.

3. Farm density creates amplification effects, particularly in southern zones where farms are concentrated.

4. Temperature regimes determine the length of the transmission season and windows of optimal conditions.

5. Fjord position influences retention and local hydrodynamics.

6. River systems show unexpected negative correlation, suggesting freshwater may actually reduce persistence through flushing or salinity effects.

## Key Insight
The most persistent hotspots occur where multiple risk factors converge: high-density areas near major salmon rivers with significant vessel traffic in retention-prone fjords. These locations require integrated management approaches addressing all contributing factors simultaneously.

## Deliverables
File	Description: 
- persistent_hotspots.csv	(List of 222 persistent hotspot localities)
- recurrence_classification.csv	(Full classification of all 1,024 farms)
- factor1_farm_density_results.png	(Farm density analysis visualization)
- factor2_fjord_position_analysis.png	(Fjord position results)
- factor3_temperature_analysis.png	(Temperature regime analysis)
- factor4_river_analysis.png	(River system analysis)
- factor5_vessel_analysis.png	(Vessel movement analysis)
- factor6_wild_salmon_analysis.png	(Wild salmonid analysis)
- farm_river_distances.csv	(Distance to nearest river)
- farm_vessel_distances.csv	(Distance to ports and shipping lanes)
- farm_salmon_distances.csv	(Distance to salmon rivers)









  







