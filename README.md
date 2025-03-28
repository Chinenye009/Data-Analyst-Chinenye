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



**Data Wrangling Analysis**

**Figure 4**

This Image Shows the Draw.io Design for the Data Wrangling Analysis of the City of Vancouver

![image](https://github.com/user-attachments/assets/e41a88c9-4404-4fb1-b7db-47f425d59481)

**Project Title**

Data Wrangling Analysis for the City of Vancouver’s Public Trees

**Project Description**

This project is focused on data wrangling, which involves cleaning, transforming, and enriching the City of Vancouver’s public tree dataset to prepare it for further analysis. The goal is to make raw, messy data usable for business intelligence and data science processes using AWS services like S3, Glue, and DataBrew.

**Objective**

    •	To clean and standardize the public trees dataset.
    
    •	To resolve inconsistencies, null values, data type mismatches, and schema errors.
    
    •	To transform the dataset into a ready-to-analyze, high-quality format stored in curated S3 buckets.
    
**Background**

The City of Vancouver’s public tree data contains a wide variety of variables including species name, neighborhood, planting dates, height, and diameter. However, raw datasets often come with inconsistencies—missing fields, incorrect data types, and mixed formats—which can affect downstream analytics and reporting. This wrangling layer ensures the data is clean, consistent, and analysis-ready.

**Dataset**

The dataset includes attributes such as:

    •	treeid, civcnumber, speciesname, genusname, commonname,
    
    •	diameter, height, height range,
    
    •	neighbourhoodname, onstreet, dateplanted, streetidname
    
    •	Stored initially in the streets-raw-per S3 bucket.
    
**Methodology**

**1.	Raw Data Storage**

    o	The dataset is first ingested into streets-raw-per on S3.
    
**2.	Cleaning with Glue DataBrew**

    o	Data profiling and cleaning is done using AWS Glue DataBrew to:
    
        	Handle missing values
        
        	Standardize data formats
        
        	Detect and correct outliers
        
        	Create transformation recipes
        
**3.	Semi-Transformation Job (semi-job-Trf)**

    o	A Glue ETL job applies semi-structured transformation logic and loads cleaned data into streets-trf-per.
    
**4.	Data Summarization**

    o	Summary statistics are generated and stored in PublicTrees-list-Summarization.
    
**5.	Final Curated Data**

    o	Final outputs are stored in streets-cur-per for downstream analytics or business reporting.
    
**Tools and Technologies**

    •	Amazon S3 – Raw, transformed, and curated data layers
    
    •	AWS Glue DataBrew – No-code data cleaning, profiling, and transformations
    
    •	AWS Glue ETL Jobs – Python-based transformation and semi-structured processing
    
    •	AWS Glue Catalog (implied) – Schema registry and metadata management
    
**Deliverables**

    •	Cleaned, transformed dataset in streets-cur-per
    
    •	Glue ETL scripts and DataBrew recipe artifacts
    
    •	Data profiling report showing cleaning actions and statistics
    
    •	Summarized version of the dataset for quick analysis
    
**Timeline**

**Phase     Duration    	Activities**

**Phase 1**	 Week 1	        Ingest and stage raw data in S3

**Phase 2**	 Week 2	        Clean and profile data using Glue DataBrew

**Phase 3**	 Week 3	        Run semi-job-Trf for transformation

**Phase 4**	 Week 4	        Generate summaries and finalize curated dataset


**Data Quality Control and Security Analysis**

**Figure 5**

This Image Shows the Draw.io Design for the Data Quality Control and Security Analysis of the City of Vancouver

![image](https://github.com/user-attachments/assets/9dfab219-1520-4bd9-9c57-a4a7fe55db07)

**Project Title**

Data Quality Control and Security for the City of Vancouver’s Public Trees

**Project Description**

This project implements a comprehensive data quality and security framework to ensure that the public trees dataset of Vancouver is accurate, reliable, and securely managed. It leverages AWS services to monitor, validate, encrypt, and audit data activities across the data lifecycle—from ingestion to querying.

**Objective**

    •	To validate the integrity and accuracy of the public trees data through automated quality checks.
    
    •	To ensure data protection using encryption (KMS keys) and auditing mechanisms (CloudTrail & CloudWatch).
    
    •	To enable secure access and analytics using SQL queries with Amazon Athena.

**Background**

The public dataset of Vancouver’s street trees is used for various public and city planning services. However, with increased use and exposure of this dataset, it becomes essential to ensure:

    •	The data is trustworthy (quality control),
    
    •	Access is secure and traceable (audit),
    
    •	Sensitive fields are encrypted at rest (security),
    
    •	Failures or anomalies are automatically detected (monitoring).

**Scope**

This solution covers:

    •	Data quality verification using AWS Glue and Data Quality jobs
    
    •	Storage encryption using AWS KMS (with a custom key: Strts-Pubtre-Key-Per)
    
    •	Querying and access control via Athena and S3
    
    •	Auditing and monitoring using CloudTrail and CloudWatch

**Methodology**

**1.	Data Validation**

    o	Strts-Pubtre-QC-Per performs data quality checks on the raw and transformed data using AWS Glue Data Quality rules.
    
    o	Results are stored in curated S3 buckets.
    
**2.	Secure Transformation and Cataloging**

    o	AWS Glue jobs handle secure ETL transformations.
    
    o	Metadata is maintained in Streets-data-catalog-per.
    
**3.	Encryption Setup**

    o	AWS KMS with custom key alias Strts-Pubtre-Key-Per is used to encrypt S3 bucket data at rest.
    
**4.	Auditing & Monitoring**

    o	CloudTrail (Strts-Pubtre-tra-Per) tracks API activity.
    
    o	CloudWatch (Strts-Pubtre-MCR-Per) monitors metrics like resource usage and storage size.
    
**5.	Query Interface**

    o	Amazon Athena provides SQL-based access to validated and encrypted data stored in S3.

**Tools and Technologies**

    •	Amazon S3 – Data lake storage (raw, transformed, curated)
    
    •	AWS Glue – ETL, cataloging, and data quality jobs
    
    •	AWS Glue Data Quality – Profile and validate datasets
    
    •	AWS KMS – Encryption key management (custom-managed key)
    
    •	Amazon Athena – Serverless SQL query access
    
    •	AWS CloudTrail – Security audit trail of API activities
    
    •	Amazon CloudWatch – Metric monitoring and alerting

**Deliverables**

    •	Encrypted and validated public trees dataset stored securely
    
    •	Glue data quality reports and data catalog metadata
    
    •	Audit logs (CloudTrail) and metric dashboards (CloudWatch)
    
    •	SQL query access via Athena for secure analysis

**Timeline**

**Phase	    Duration	    Activities**

**Phase 1**  Week 1	        Configure KMS keys and encrypt S3 buckets

**Phase 2**	 Week 2	        Build Glue data quality jobs and validate datasets

**Phase 3**	 Week 3	        Set up CloudTrail & CloudWatch for monitoring and logging

**Phase 4**	 Week 4	        Deploy Athena for secure querying and finalize documentation



