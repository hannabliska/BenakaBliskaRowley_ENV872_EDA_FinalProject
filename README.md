# <BenakaBliskaRowley_ENV872_EDA_FinalProject>

## Summary

The purpose of this repository is to store project files for our final project in Environmental Data Analytics (ENV872). The final project was created by Isaac Benaka, Hanna Bliska, and Caroline Rowley and was conducted at the conclusion of our course in November and December of 2022. The final project focuses on mangrove conservation in the Florida Everglades. 

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

Data on site coordinates were collected from the Florida Coastal Everglades LTER webpage (https://fce-lter.fiu.edu/research/sites/coordinates/). The csv file was saved as `FCE_LTER_site_coordinates.csv`

Data were accessed on 2022-11-15.

### Above Ground Biomass Calculations
The BIOMASS r package was used to find wood density values and calculate above ground biomass for mangrove species sampled in the Florida Coastal Everglades LTER Data Set. The generated data can be found in `treeAGB.csv` in the Processed data folder. Details on the r BIOMASS package can be found here: https://cran.r-project.org/web/packages/BIOMASS/index.html.

### Mangrove Distribution Data
Mangrove habitat spatial data was collected from the Florida Fish and Wildlife Conservation Commission GIS & Mapping Data website (https://geodata.myfwc.com/datasets/myfwc::mangrove-habitat-in-florida-1/about). The shapefile data were saved as `Mangrove_Habitat_in_Florida` under the Spatial data folder.

National Park boundary data was collected from the National Park Service DataStore (https://irma.nps.gov/DataStore/Reference/Profile/2224545?lnv=True). The Administrative Boundaries of the National Park System shapefile was saved as `nps_boundary` under the Spatial data folder.

Data were accessed on 2022-11-18.

### iNaturalist Data
iNaturalist data was collected from inaturalist.org/observations/export using the export tool. Three datasets were created using a query, selecting for research grade only observations of reptiles, mammals, and birds within the boundaries of Everglades National Park, US, FL. 

We then selected the columns included in the data set: id, observed_on_string, observed_on, time_observed_at, latitude, longitude, scientific_name, common_name, iconic_taxon_name, taxon_id, taxon_order_name, and taxon_genus_name.

The csv files were saved as `inaturalist_reptiles2`, `inaturalist_mammals`, and `inaturalist_birds` in the raw data folder.

Data were accessed on 2022-11-28.

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

1. FCE_LTER_Mangroves.csv

| Column Name   | Column Description          | Class    | Format/Units         |
| ------------- | --------------------------- | -------- | -------------------- |
| SITE          | Name of LTER site           | factor   | text                 |
| DATE          | Date of collection          | date     | YYYY-MM-DD           |
| Plot_ID       | ID number of plot           | factor   | numeric              |
| Tree_TagNumber| Tag number                  | factor   | numeric              |
| Species.Tree  | Species of tree             | factor   | Species abbreviation |
| Tree_DBH      | Diameter at breast height   | numeric  | centimeters          |
| Tree_Height   | Height of tree              | factor   | meters               |

2. FCE_LTER_Nutrients.csv

| Column Name | Column Description          | Class    | Format/Units         |
| ----------- | --------------------------- | -------- |--------------------- |
| SITE_NAME   | Name of LTER site           | factor   | text                 |
| DATE        | Date of collection          | date     | YYYY-MM-DD           |
| TIME        | Time of collection          | factor   | hh:mm                |
| Salinity    | Composite salinity          | factor   | PSU                  |
| TN          | Composite total nitrogen    | numeric  | micro moles per liter |
| TP          | Composite total phosphorus  | numeric  | micro moles per liter |
| TOC         | Total organic carbon        | factor   | micro moles per liter |
| NH4         | Ammonium                    | factor   | micro moles per liter |
| NandN       | Nitrate and nitrite         | factor   | micro moles per liter |
| NO2         | Nitrite                     | factor   | micro moles per liter |
| SRP         | Soluble reactive phosphorus | factor   | micro moles per liter |
| DOC         | Dissolved organic carbon    | factor   | micro moles per liter |
| NO3         | Nitrate                     | factor   | micro moles per liter |

3. FCE_LTER_site_coordinates.csv

| Column Name                  | Column Description | Class     | Format/Units     |
| ---------------------------- | ------------------ | --------- | ---------------- |
| SITE                         | Name of LTER site  | factor    | text             |
| LATITUDE (Decimal degrees)   | Latitude of site   | character | Decimal degrees  |
| LONGITUDE (Decimal degrees)  | Longitude of site  | character | Decimal degrees  |
| LATITUDE (Degrees, minutes)  | Latitude of site   | character | Degrees, minutes |
| LONGITUDE (Degrees, minutes) | Longitude of site  | character | Degrees, minutes |
| NORTHING (UTM)               | Northing of site   | character | UTM              |
| EASTING (UTM)                | Easting of site    | character | UTM              |

4. Mangrove_Habitat_in_Florida.shp

| Column Name                  | Column Description | Class     | Format/Units     |
| ---------------------------- | ------------------ | --------- | ---------------- |
| OBJECTID                     | ID of polygon      | numeric   | Number           |
| DESCRIPT                     | Type of habitat    | character | Mangrove Swamp   |
| METADATA                     | Origin of data     | character | origin_owner_year|
| last_edite                   | Last edit date     | date      | YYYY-MM-DD       |
| Shape_Area                   | Area of polygon    | numeric   | Subject to coordinate system |
| geometry                     | Coordinate pair    | list      | (Longitude, Latitude)        |

5. nps_boundary.shp

| Column Name                  | Column Description | Class     | Format/Units     |
| ---------------------------- | ------------------ | --------- | ---------------- |
| OBJECTID                     | ID of polygon      | numeric   | Number           |
| UNIT_CODE                    | Park Code          | character | Mangrove Swamp   |
| GIS_Notes                    | Origin of data     | character | origin_owner_year|
| UNIT_NAME                    | Park Name          | character | _ National Park  |
| DATE_EDIT                    | Last edit date     | date      | YYYYMMDD         |
| STATE                        | States within park | character | State abbrev.    |
| REGION                       | Region of US       | character | Region abbrev.   |
| GNIS_ID                      | National Map ID    | numeric   | Number           |
| UNIT_TYPE                    | Type of park       | character | Park designation |
| CREATED_BY                   | Creator of data    | character | Department       |
| METADATA                     | Link to metadata   | character | URL              |
| PARKNAME                     | Name of the park   | character | Short name       |
| CreationDa                   | Date created       | numeric   | YYYYMMDD         |
| Creator                      | Polygon creator    | character | Service_Department_Office|
| EditDate                     | Date edited        | numeric   | YYYYMMDD         |
| Editor                       | Polygon editor     | character | Service_Department_Office|
| Global_ID                    | ID Number          | character | ID code          |
| Shape_Leng                   | Length of polygon  | numeric   | Subject to coordinate system |
| Shape_Area                   | Area of polygon    | numeric   | Subject to coordinate system |
| geometry                     | Coordinate pair    | list      | (Longitude, Latitude)        |

6.inaturalist_reptiles2.csv

| Column Name         | Column Description          | Class    | Format/Units           |
| ------------------- | --------------------------- | -------- | ---------------------- |
| id                  | Unique id of observation    | int      | numeric                |
| observed_on_string  | Date as input by observer   | factor   | numeric and characters |
| observed_on         | Normalized date             | date     | YYYY-MM-DD             |
| time_observed_at    | Normalized datetime         | factor   | YYYY-MM-DD hh:mm:ss    |
| latitude            | Publically shared latitude  | numeric  | degrees, latitude      |
| longitude           | Publically shared longitude | numeric  | degrees, longitude     |
| scientific_name     | Latin Genus species         | factor   | Genus species          |
| common_name         | Common name or vernacular   | factor   | Common Name            |
| iconic_taxon_name   | Higher level taxonomic id   | factor   | Class (Linnaeus)       |
| taxon_id            | Unique identity # for taxon | int      | numeric                |
| taxon_order_name    | Latin Order of taxon        | factor   | Order (Linnaeus)       |
| taxon_genus_name    | Latin Genus of taxon        | factor   | Genus  (Linnaeus)      | 

6.inaturalist_mammals.csv

| Column Name         | Column Description          | Class    | Format/Units           |
| ------------------- | --------------------------- | -------- | ---------------------- |
| id                  | Unique id of observation    | int      | numeric                |
| observed_on_string  | Date as input by observer   | factor   | numeric and characters |
| observed_on         | Normalized date             | date     | YYYY-MM-DD             |
| time_observed_at    | Normalized datetime         | factor   | YYYY-MM-DD hh:mm:ss    |
| latitude            | Publically shared latitude  | numeric  | degrees, latitude      |
| longitude           | Publically shared longitude | numeric  | degrees, longitude     |
| scientific_name     | Latin Genus species         | factor   | Genus species          |
| common_name         | Common name or vernacular   | factor   | Common Name            |
| iconic_taxon_name   | Higher level taxonomic id   | factor   | Class (Linnaeus)       |
| taxon_id            | Unique identity # for taxon | int      | numeric                |
| taxon_order_name    | Latin Order of taxon        | factor   | Order (Linnaeus)       |
| taxon_genus_name    | Latin Genus of taxon        | factor   | Genus  (Linnaeus)      | 

6.inaturalist_birds.csv

| Column Name         | Column Description          | Class    | Format/Units           |
| ------------------- | --------------------------- | -------- | ---------------------- |
| id                  | Unique id of observation    | int      | numeric                |
| observed_on_string  | Date as input by observer   | factor   | numeric and characters |
| observed_on         | Normalized date             | date     | YYYY-MM-DD             |
| time_observed_at    | Normalized datetime         | factor   | YYYY-MM-DD hh:mm:ss    |
| latitude            | Publically shared latitude  | numeric  | degrees, latitude      |
| longitude           | Publically shared longitude | numeric  | degrees, longitude     |
| scientific_name     | Latin Genus species         | factor   | Genus species          |
| common_name         | Common name or vernacular   | factor   | Common Name            |
| iconic_taxon_name   | Higher level taxonomic id   | factor   | Class (Linnaeus)       |
| taxon_id            | Unique identity # for taxon | int      | numeric                |
| taxon_order_name    | Latin Order of taxon        | factor   | Order (Linnaeus)       |
| taxon_genus_name    | Latin Genus of taxon        | factor   | Genus  (Linnaeus)      | 

## Scripts and code

Code is saved in the code folder of the repository. The following files are detailed:

| Code Name                              | Code Contents        | File Format |
| -------------------------------------- | -------------------- | ----------- |
| Benaka_Bliska_Rowley_Final_Project.Rmd | All project code     | Rmd         |
| DataAnalysis.Rmd                       | Data analysis        | Rmd         |
| DataExploration.Rmd                    | Data exploration     | Rmd         |
| DataWrangling.Rmd                      | Data wrangling       | Rmd         |

## Quality assurance/quality control

To ensure basic quality control, we underwent the following procedures:

1. Instrument-collected data: The nitrogen and phosphorus concentrations measured in the `FCE_LTER_Nutrients.csv` data set were collected via ISCO autosamplers, a water quality measurement instrument. It is best practice to ensure that instrument-collected data is reasonable given the instrument and within range (DataONE, 2022). Therefore, nitrogen and phosphorus concentrations were checked to ensure there were no values below zero and that there were no outliers surpassing the expected range of the values.
2. Dates and times: Several data sets (e.g., `FCE_LTER_Nutrients.csv`, ``FCE_LTER_Mangroves.csv`) included dates and times of observations. To ensure quality control, we implemented the best practice to ensure dates and times observed were accurate and logical (DataONE, 2022).
3. Geographic coordinates: We obtained geographic coordinates (`FCE_LTER_site_coordinates.csv`) for the mangrove long-term monitoring sites. To ensure quality control, we plotted the site coordinates using MapViewer to ensure the coordinates did not include errors (DataONE, 2022).
4. iNaturalist data: only research grade observations were accepted into the data set. Limitations of this data set are discussed in the Summary and Conclusions section of the report.
5. Ensured that classes in dataframes were consistent with the type of data contained in columns.

##References
DataONE. (2022). Ensure basic quality control. Accessed online: https://dataoneorg.github.io/Education/bestpractices/ensure-basic-quality. 
