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



