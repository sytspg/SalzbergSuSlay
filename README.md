# SalzbergSuSlay

ENV 872 Course Project for J. Salzberg, Y.E. Su, and S. Slay December 10, 2025

# Climate vulnerability and economic stability in North Carolina

## Summary

The primary goal of this analysis is to find the correlation between **household income** and specific **climate vulnerability indicators** across counties in North Carolina. A common assumption that low-income household are often situated in areas with higher environmental vulnerability. The study investigates the correlation between household income and indicators like **flood risk** and **extreme heat exposure**, and also considers the factor of **walkability**. And our findings turn out to be contrary to the original assumption and show that walkability and high heat index days/yr increase slightly but statistically signficantly with average household income. We hope the findings will better inform policy initiatives, aiming to identify specific counties where vulnerable populations are disproportionately at risk.

## Investigators

Josh Salzberg, Yitong Eric Su, and Sarah Slay; Duke University Nicholas School of the Environment.

## Keywords

Climate vulnerability, Household Income, North Carolina, Economic Inequality.

## Database Information

1.  The main database is from the NC Data Portal (<https://ncdataportal.org/>), a platform that gathers social and environmental data related to North Carolina from government entities. Our specific dataset includes data from ACS estimates 2019-2023 (household income and population), EPA 2020 (flood index), EPA 2021 (walkability index), and CDC 2020-22 (Heat Index).

2.  Census USA counties shapefile (cb_2018_us_county_20m.shp): this dataset provides mapping information for US counties and is filtered for to isolate the NC counties (FIPS: 37).

## Folder structure and file formats

.

├── Code

│ ├── ExploratoryVisualization.Rmd

│ ├── Project_Template.Rmd

│ ├── Project_Template.html

│ ├── RawDataImport.Rmd

│ ├── Spatial.Rmd

│ └── Timeseries.Rmd

├── Data

│ ├── Metadata

│ │ └── NorthCarolinaAssessment.pdf

│ ├── Processed

│ │ └── NCDataClean.csv

│ ├── Raw

│ │ ├── NCDataPortal-RAW.csv

│ │ ├── NCDataPortal-RAW.xlsx

│ │ └── NOAA_NCweather_19952024.csv

│ └── Spatial

│ ├── Cartographic Boundary Files - Shapefile.URL

│ ├── DurhamElev.tfw

│ ├── DurhamElev.tif

│ ├── Manufactured_Gas_Plant_Sites.geojson

│ ├── NCHUC8.dbf

│ ├── NCHUC8.prj

│ ├── NCHUC8.shp

│ ├── NCHUC8.shx

│ ├── NorthCarolina_county.csv

│ ├── PowerPlantData.json

│ ├── TriangleElev.tfw

│ ├── TriangleElev.tif

│ ├── Wind_Energy.csv

│ ├── cb_2018_us_county_20m.cpg

│ ├── cb_2018_us_county_20m.dbf

│ ├── cb_2018_us_county_20m.prj

│ ├── cb_2018_us_county_20m.shp

│ ├── cb_2018_us_county_20m.shp.ea.iso.xml

│ ├── cb_2018_us_county_20m.shp.iso.xml

│ └── cb_2018_us_county_20m.shx

├── Output

│ └── Report_final.html

├── README.md

└── SalzbergSuSlay.Rproj

*Table 1: File Formats*

| Folder          | Purpose                                                                                                                                                | File Types  |
|----------------|----------------------------------------|----------------|
| Code/           | Analysis and Reporting Scripts. Contains R Markdown files that execute data processing, visualization, and reporting, compiling into output documents. | .rmd        |
| Data/           | Data storage parent directory, organized by processing stage and type.                                                                                 |             |
| Data/Metadata/  | Documentation.                                                                                                                                         |             |
| Data/Processed/ | Cleaned data.                                                                                                                                          |             |
| Data/Raw/       | Original Input Data.                                                                                                                                   | .csv, .xlsx |
| Data/Spatial/   | Spatial Data for NC counties.                                                                                                                          | .shp        |
| Output/         | Final Deliverable.                                                                                                                                     | .html       |

## Metadata

We obtained data from the NC Data Portal (<https://ncdataportal.org/>), a platform that gathers social and environmental data related to North Carolina from government entities. By selecting specific parameters, we built a custom dataset.

Our custom dataset describes household income and population for all 100 counties in NC using ACS estimates from 2019-2023. Data for the flood hazard area was sourced from the EPA based on 2020 measurements. Each indicator has its own column for a total of 14 columns (Table 2).

More information can be found in the folder Data-\>Metadata for the official metadata document.

*Table 2: Summary of Data*

|                   Variable Name | Variable Description                                                                 |
|------------------------:|:----------------------------------------------|
|                        `County` | Name of North Carolina county                                                        |
|              `Total.Population` | Count of county population                                                           |
|               `TotalHouseholds` | Count of county households                                                           |
|                      `AvgHHinc` | County average household income                                                      |
|                      `MedHHinc` | County median household income                                                       |
|                `WalkIndexScore` | County walkability score (based on EPA Walkability Index)                            |
|                     `LeastWalk` | Percent of population residing in area considered least walkable                     |
|                  `BelowAvgWalk` | Percent of population residing in area considered below average walkable             |
|                  `AboveAvgWalk` | Percent of population residing in area considered above average walkable             |
|                      `MostWalk` | Percent of population residing in area considered most walkable                      |
|                      `PopInFHA` | Count of county population residing in Flood Hazard Area                             |
|               `PercentPopInFHA` | Percent of county population residing in Flood Hazard Area                           |
| `DailyMaxHeatIndex95Percentile` | Count of days per year maximum daily temperature exceeded 95th percentile, 2022-2024 |

## Scripts and code

| Script/Code Filename         | Description                                                                                                                                                                                                                           |
|--------------|----------------------------------------------------------|
| RawDataImport.Rmd            | Script responsible for importing raw data from its source, performing initial data cleaning, and preparing the dataset for analysis.                                                                                                  |
| ExploratoryVisualization.Rmd | Contains code for conducting Exploratory Data Analysis (EDA). This script generates preliminary statistics, summary tables, and visualizations to understand the data's distribution, identify relationships, and check for outliers. |
| Spatial.Rmd                  | Script dedicated to spatial analysis. This likely involves working with geographic data, generating maps, analyzing geographic relationships between variables.                                                                       |
| Timeseries.Rmd               | Script used for time series analysis. This file would contain code to analyze data collected over time, looking for trends and seasonality.                                                                                           |
| Project_Template.Rmd         | Script used for compiling the final report based on the template.                                                                                                                                                                     |
