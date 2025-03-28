# Data-Analyst-Chinenye
PROJECT 1 (CITY OF VANCOUVER)
Figure 1
This Image Shows the Draw.io Design for the Exploratory Data Analysis for the City of Vancouver
![image](https://github.com/user-attachments/assets/6228ad27-f9d5-464b-870c-5bc052cb03ef)

Project Title
Public Tree Exploratory Data Analysis for Vancouver City
Project Description
This project employs cloud-native architecture to examine, utilizing public trees in the City of Vancouver, their distribution, traits and planting history. Details, including tree species, genus, planting date, neighborhood, street name, and physical characteristics (height, diameter), abound in the dataset. Raw municipal data will be turned into orderly insights for city planners, academics, and environmental advocates.
Objective
To build and implement a cloud-based pipeline that:
• swallows and safely keeps raw tree records.
• Fields, including species name, common name, height, diameter, and neighborhood name, are cleansed and standardized.
• enriches and catalogs the information for searching.
• Summarizes knowledge that helps urban forestry management, tree health assessment, and neighborhood biodiversity planning.
Dataset
The Public Trees dataset of the City of Vancouver is the dataset used and has the following important columns:
• treeid: Unique tree identifier
• civicnumber, stdstreet, onstreet, onstreetblock, streetidname: Location references
• genusname, speciesname, commonname: Tree classification
• neighbourhoodname: Neighborhood location
• height, heightrange, diameter: Physical measurements
• dateplanted: Planting year of the tree
Methodology
1. Raw Ingestion
o Raw data is kept on Amazon S3 (streets-raw-per).
2. Data Cleaning & Preparation
o AWS Glue DataBrew is used to handle missing variables and inconsistencies like blank species or invalid dates, and it also standardizes units of measurement.
o The transformed datasets are stored streets-trf-per.
3. Data Cataloging
o AWS Glue Data Catalogue (streets-data-catalog-per) is where the structured dataset is registered which allows SQL searches via Athena.
4. Summarization
o Aggregation scripts (e.g., tree counts by neighborhood, average height by species) are run, and the results are stored in PublicTrees-list-Summarization.
5. Output Storage
o Amazon S3 (streets-cur-per) is where the final outputs and well-chosen datasets are saved for long-term preservation and analysis.
Tools and Technologies
• Amazon S3 – Storage for raw, transformed, and curated data
• AWS Glue – Serverless ETL and metadata cataloging
• AWS Glue DataBrew – Visual data cleaning and transformation
Deliverables
• Cleaned and well-documented public tree dataset, partitioned by neighborhood or planting year.
• Aggregated metrics including:
o Total trees by neighborhoodname
o Average height and diameter by speciesname
o Tree distribution over planting decades
• Architecture diagrams documenting the data flow and processing logic
