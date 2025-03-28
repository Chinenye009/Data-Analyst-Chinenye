# Data-Analyst-Chinenye

**PROJECT 1 (CITY OF VANCOUVER)**

**Exploratory Data Analysis**

**Figure 1**

This Image Shows the Draw.io Design for the Exploratory Data Analysis for the City of Vancouver

![image](https://github.com/user-attachments/assets/6228ad27-f9d5-464b-870c-5bc052cb03ef)

**Project Title**

Public Tree Exploratory Data Analysis for Vancouver City

**Project Description**

This project employs cloud-native architecture to examine, utilizing public trees in the City of Vancouver, their distribution, traits and planting history. Details, including tree species, genus, planting date, neighborhood, street name, and physical characteristics (height, diameter), abound in the dataset. Raw municipal data will be turned into orderly insights for city planners, academics, and environmental advocates.

**Objective**

To build and implement a cloud-based pipeline that:

    • swallows and safely keeps raw tree records.

    • Fields, including species name, common name, height, diameter, and neighborhood name, are cleansed and standardized.

    • enriches and catalogs the information for searching.

    • Summarizes knowledge that helps urban forestry management, tree health assessment, and neighborhood biodiversity planning.

**Dataset**

The Public Trees dataset of the City of Vancouver is the dataset used and has the following important columns:

    • treeid: Unique tree identifier
  
    • civicnumber, stdstreet, onstreet, onstreetblock, streetidname: Location references

    • genusname, speciesname, commonname: Tree classification

    • neighbourhoodname: Neighborhood location

    • height, heightrange, diameter: Physical measurements

    • dateplanted: Planting year of the tree

**Methodology**

  **1. Raw Ingestion**
 
      o Raw data is kept on Amazon S3 (streets-raw-per).

  **2. Data Cleaning & Preparation**

      o AWS Glue DataBrew is used to handle missing variables and inconsistencies like blank species or invalid dates, and it also standardizes units of measurement.

      o The transformed datasets are stored streets-trf-per.

**3. Data Cataloging**
   
      o AWS Glue Data Catalogue (streets-data-catalog-per) is where the structured dataset is registered which allows SQL searches via Athena.

**4. Summarization**
   
      o Aggregation scripts (e.g., tree counts by neighborhood, average height by species) are run, and the results are stored in PublicTrees-list-Summarization.

**5. Output Storage**
   
      o Amazon S3 (streets-cur-per) is where the final outputs and well-chosen datasets are saved for long-term preservation and analysis.

**Tools and Technologies**

    • Amazon S3 – Storage for raw, transformed, and curated data
    
    • AWS Glue – Serverless ETL and metadata cataloging
    
    • AWS Glue DataBrew – Visual data cleaning and transformation
    
**Deliverables**

    • Cleaned and well-documented public tree dataset, partitioned by neighborhood or planting year.
    
    • Aggregated metrics including:
    
          o Total trees by neighborhoodname
      
          o Average height and diameter by speciesname
      
          o Tree distribution over planting decades
      
    • Architecture diagrams documenting the data flow and processing logic


**Descriptive Data Analysis**

**Figure 2**

The Attached Image Depicts the Draw.io Design for Descriptive Data Analysis for Vancouver City

![image](https://github.com/user-attachments/assets/18beae49-5236-4fd6-9378-3f2716017246)

**Project Title**

Descriptive Data Analysis of the Public Trees in the City of Vancouver

**Project Description**

The main focus of this project is creating a scalable data pipeline that allows the City of Vancouver to examine public tree data both past and present. Descriptive insights based on tree species, planting site, height, diameter, and planting dates are sought to address "what happened." These revelations enable urban forestry stakeholders to make data-based decisions about resource allocation, biodiversity, and tree upkeep.

**Objective**

To create infographics and succinct descriptions reflecting:

    •	The way different neighborhoods' tree species and genera are distributed.
    
    •	Trends in planting across time.
    
    •	Physical traits which include typical tree height and diameter.
    
    •	Typical tree species seen in several districts.
    
**Dataset**

The Public Trees dataset of Vancouver City is the one used; fields like these exist:

    •	treeid, civicnumber, neighbourhoodname, onstreet, stdstreet, onstreetblock, streetidname
    
    •	genusname, speciesname, commonname
    
    •	height, heightrange, diameter
    
    •	dateplanted
    
**Methodology**

**1.	Data Ingestion**
    
        o	The raw tree dataset is first housed in the streets-raw-per S3 bucket.
        
**2.	Data Preparation and Transformation**

        o	Using AWS Glue and Glue DataBrew, the publictrees-list-Trf job cleans and prepares the dataset standardizing missing or inconsistent entries.
        
**3.	Data Transformation Layer**
    
        o	Data that has been cleaned is transferred for structured storage and additional processing to the streets-trf-per bucket.
        
**4.	Metadata Management**
    
        o	The Glue Data Catalog registers the dataset using streets-data-catalog-per, so allowing smooth querying with Athena.
        
**5.	Descriptive Analysis & Summarization**
    
        o	PublicTrees-list-Summarization generates and stores summary outputs, that is, average height by species, most frequent trees by neighborhood, planting frequency by year).
        
**6.	Curated Data Layer**
    
        o	For use by dashboards, analysts, and stakeholders, final outputs are kept in the streets-cur-per bucket.
        
**Tools and Technologies**

    •	Amazon S3 – For multi-layered data storage (raw, transformed, curated)

    •	AWS Glue – ETL jobs and Glue Catalog for metadata

    •	AWS Glue DataBrew – Visual data preparation

**Deliverables**

    •	Three S3 phases of cleaned, converted, and curated tree datasets

    •	GLue's SQL-queryable data catalog

    •	Descriptive measures and condensed analysis of ideas:

        o	Typical tree height and width by genus and species.

        o	Tree count in a neighborhood

        o	Trend of tree planting throughout the years

    •	AWS infrastructure map showing the whole pipeline

**Diagnostic Data Analysis**

**Figure 3**

The Attached Image Depicts the Draw.io Design for Diagnostic Data Analysis for Vancouver City

![image](https://github.com/user-attachments/assets/2f6871c8-25b4-4919-b0d2-e5df45c2fb20)

**Project Title**

Diagnostic Data Analysis for Public Trees of Vancouver City

**Project Description**

This project aims to do a public tree diagnostic data analysis for Vancouver. It seeks to go beyond "what happened" to investigate the causes behind changes in biodiversity across the city, planting trends, and tree health patterns. The project creates a strong and safe data pipeline using AWS cloud services to assist in the identification of the causes behind some data trends and anomalies noted in the urban forestry records of the city.

**Objective**

    •	To investigate underlying causes of observable trends in tree characteristics and distribution.

    •	To explain why certain neighborhoods have fewer or more trees, species loss, or abnormal planting frequencies.

    •	To help the city make better ecological, maintenance, and urban planning decisions.
    
**Background**

The City of Vancouver maintains a comprehensive record of its public trees, but actionable insights into why specific tree trends exist are limited. Previous descriptive analyses show what has happened, but the need to explain the "why" (e.g., why certain species thrive or fail, or why planting frequency varies) is crucial for planning. Diagnostic analytics fills this gap.

**Dataset**

From the City of Vancouver’s public trees open dataset (used in earlier analyses), key fields include:

    •	treeid, speciesname, commonname, genusname

    •	diameter, height, heightrange

    •	onstreet, neighbourhoodname, dateplanted, streetidname

    •	Observations enriched with summarization and transformation layers

**Methodology**

**1.	Data Ingestion**

    o	Raw data ingested to streets-raw-per via S3.
    
**2.	Data Cleaning and Transformation**

    o	Cleaning via Glue DataBrew and Glue ETL jobs stored in publictrees-list-Trf.
    
    o	Outputs are stored in streets-trf-per.
    
**3.	Metadata Registration**

    o	Metadata cataloged in streets-data-catalog-per for SQL-based querying.
    
**4.	Diagnostic Analysis**

    o	Queries using AWS Athena identify:
    
            	Outlier tree measurements

            	Sudden planting gaps

            	Specific areas lacking diversity

            	Correlations between tree health metrics and neighborhoods

**5.	Summarization**

    o	Aggregated diagnostics saved in PublicTrees-list-Summarization
    
    o	Final curated results go to streets-cur-per
    
**Tools and Technologies**

    •	Amazon S3 – Staging (raw, transformed, curated data)
    
    •	AWS Glue – Data transformation and ETL
    
    •	Glue DataBrew – Data profiling and cleaning
    
    •	AWS Glue Catalog – Centralized metadata store
    
**Deliverables**

    •	Full diagnostic report explaining trends (e.g., why certain species dominate or fail)

    •	Dashboards and summary insights of tree planting causes, health, and anomalies

    •	S3-structured data layers: raw, transformed, summarized, and curated

    •	Glue job scripts and DataBrew profiles

**Timeline**

**Phase**	**Duration**	**Activities**

**Phase 1**	     Week 1	        Ingest public tree dataset into S3 (raw)

**Phase 2**	     Week 2	        Clean and transform using Glue & DataBrew

**Phase 3**	     Week 3	        Register in Glue Catalog & run Athena queries

**Phase 4**      Week 4	        Perform diagnostic analytics & summarize insights

**Phase 5**	     Week 5	        Validate, secure, log, and finalize reporting



