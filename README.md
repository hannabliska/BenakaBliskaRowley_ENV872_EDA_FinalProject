# <BenakaBliskaRowley_ENV872_EDA_FinalProject>

## Summary

This purpose of this repository is to store project files for our final project in Environmental Data Analytics (ENV872). The final project was created by Isaac Benaka, Hanna Bliska, and Caroline Rowley and was conducted at the conclusion of our course in November and December of 2022. The final project focuses on mangrove conservation in the Florida Everglades. 

The repository contains raw, processed, and spatial data utilized for the final project's analysis. The repository also contains the code written for data exploration, wrangling, and analysis, as well as our final project RMarkdown file. 

The objective of the analysis was to determine areas within the Everglades National Park that should be conserved due to risk to mangrove habitats. The analysis focuses on identifying changes in mangrove health, nutrient availability, and mangrove-associated species. 

## Investigators

Isaac Benaka, Nicholas School of the Environment, 
isaac.benaka@duke.edu, Principal Investigator

Hanna Bliska, Nicholas School of the Environment, 
hanna.bliska@duke.edu, Principal Investigator

Caroline Rowley, Nicholas School of the Environment, 
caroline.rowley@duke.edu, Principal Investigator

## Keywords

mangroves, biomass, mangrove distribution, conservation, nutrient availability, everglades, native species

## Database Information

### Florida Coastal Everglades LTER Data Sets
Data were collected from the Environmental Data Initiative Data Portal (https://portal.edirepository.org/nis/home.jsp). From the Advanced Search, the following search was made: 
*Sites: selected Florida Coastal Everglades

We then selected the following data sets:
1. Water Quality Data (Grab Samples) from the Shark River Slough, Everglades National Park (FCE LTER), May 2001 - ongoing
2. Mangrove Forest Growth from the Shark River Slough, Everglades National Park (FCE), South Florida, USA, January 1995 - ongoing

csv files were saved as `FCE_LTER_Nutrients` and `FCE_LTER_Mangroves`, respectively.

Data on site coordinated were collected from the Florida Coastal Everglades LTER webpage (https://fce-lter.fiu.edu/research/sites/coordinates/). The csv file was saved as `FCE_LTER_site_coordinates.csv`

Data were accessed on 2022-11-15.

### Mangrove Distribution Data

<describe the origin of all data in the repository, including data collected from outside sources and new data generated by the investigator(s). If data was accessed from an outside database, the date(s) of data access should also be included.>

### iNaturalist Data

<describe the origin of all data in the repository, including data collected from outside sources and new data generated by the investigator(s). If data was accessed from an outside database, the date(s) of data access should also be included.>

## Folder structure, file formats, and naming conventions 

### Folder Structure
1. Code: Contains the RMarkdown files for our data exploration, analysis, and wranging code. All of the final code was then merged into our final project code, saved as `Benaka_Bliska_Rowley_Final_Project.rmd`
2. Data: Contains the raw, processed, and spatial data for our final project.

| Folder Name | Folder Contents      | File Format |
| ----------- | -------------------- | ----------- |
| Raw         | Raw data files       | .csv        |
| Processed   | Processed data files | .csv        |
| Spatial     | Spatial data files   | .shp        |

3. Output: Contains final visualizations from analysis (.jpg format)

### Naming Conventions and File Formats
Files are named according to the following naming convention: `databaseinfo_datatype.format`, where: 

**databaseinfo** describes the database where the data were obtained from 

**datatype** notes the main type of data in the file (e.g., nutrient data)

**format** indicates the format of the file (e.g., .csv, .txt, .shp, .Rmd)

## Metadata
**Hanna to add class for each data**
1. FCE_LTER_Mangroves.csv

2. FCE_LTER_Nutrients.csv
| Column Name | Column Description          | Format                |
| ----------- | --------------------------- | --------------------- |
| SITE_NAME   | Name of LTER site           | text                  |
| DATE        | Date of collection          | YYYY-MM-DD            |
| TIME        | Time of collection          | hh:mm                 |
| Salinity    | Composite salinity          | PSU                   |
| TN          | Composite total nitrogen    | micro moles per liter |
| TP          | Composite total phosphorus  | micro moles per liter |
| TOC         | Total organic carbon        | micro moles per liter |
| NH4         | Ammonium                    | micro moles per liter |
| NandN       | Nitrate and nitrite         | micro moles per liter |
| NO2         | Nitrite                     | micro moles per liter |
| SRP         | Soluble reactive phosphorus | micro moles per liter |
| DOC         | Dissolved organic carbon    | micro moles per liter |
| NO3         | Nitrate                     | micro moles per liter |

3. FCE_LTER_site_coordinates.csv
| Column Name                  | Column Description | Format           |
| ---------------------------- | ------------------ | ---------------- |
| SITE                         | Name of LTER site  | text             |
| LATITUDE (Decimal degrees)   | Latitude of site   | Decimal degrees  |
| LONGITUDE (Decimal degrees)  | Longitude of site  | Decimal degrees  |
| LATITUDE (Degrees, minutes)  | Latitude of site   | Degrees, minutes |
| LONGITUDE (Degrees, minutes) | Longitude of site  | Degrees, minutes |
| NORTHING (UTM)               | Northing of site   | UTM              |
| EASTING (UTM)                | Easting of site    | UTM              |

4. **others**

<For each data file in the repository, describe the data contained in each column. Include the column name, a description of the information, the class of data, and any units associated with the data. Create a list or table for each data file.> 

## Scripts and code

Code is saved in the code folder of the repository. The following files are detailed:

| Code Name           | Code Contents        | File Format |
| ------------------- | -------------------- | ----------- |
| DataAnalysis.Rmd    | Data analysis        | Rmd         |
| DataExploration.Rmd | Data exploration     | Rmd         |
| DataWrangling.Rmd   | Data wrangling       | Rmd         |

## Quality assurance/quality control

To ensure basic quality control, we underwent the following procedures:

1. Instrument-collected data: The nitrogen and phosphorus concentrations measured in the `FCE_LTER_Nutrients.csv` data set were collected via ISCO autosamplers, a water quality measurement instrument. It is best practice to ensure that instrument-collected data is reasonable given the instrument and within range (DataONE, 2022). Therefore, nitrogen and phosphorus concentrations were checked to ensure there were no values below zero and that there were no outliers surpassing the expected range of the values.
2. Dates and times: Several data sets (e.g., `FCE_LTER_Nutrients.csv`, ``FCE_LTER_Mangroves.csv`) included dates and times of observations. To ensure quality control, we implemented the best practice to ensure dates and times observed were accurate and logical (DataONE, 2022).
3. Geographic coordinates: We obtained geographic coordinates (`FCE_LTER_site_coordinates.csv`) for the mangrove long-term monitoring sites. To ensure quality control, we plotted the site coordiantes using MapViewer to ensure the coordinates did not include errors (DataONE, 2022).
4. **Isaac and Caroline to look at the observations suggestions to include

##References
DataONE. (2022). Ensure basic quality control. Accessed online: https://dataoneorg.github.io/Education/bestpractices/ensure-basic-quality. 
