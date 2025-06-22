# clarity_omop: OMOP Database Creation from Clarity Data

## Overview

This project provides SQL scripts and ETL processes for constructing an Observational Medical Outcomes Partnership (OMOP) compliant database from a Clarity data source.  The scripts handle the extraction, transformation, and loading (ETL) of data, meticulously following the specified insertion and deletion order to maintain data integrity within the complex OMOP schema.  The README details crucial dependencies between OMOP tables, emphasizing the importance of a sequential approach for both data insertion and deletion to avoid inconsistencies.

## Key Features

* **Comprehensive ETL Processes:**  A complete set of SQL scripts for extracting and transforming data from a Clarity source into an OMOP CDM.
* **Strict Order of Operations:**  Scripts adhere to a defined insertion and deletion order to maintain referential integrity within the OMOP database.
* **Modular Design:** The SQL scripts are organized into individual files, allowing for flexibility and maintainability.
* **Support for Multiple Data Sources:** The scripts appear to handle various data types including ambulatory (AMB), inpatient (HSP), and anesthesiology (ANES) data.
* **OMOP CDM Compliance:** The database structure and data transformation procedures aim for compliance with the OMOP Common Data Model.

## Project Structure

The project is structured primarily with SQL files organized by OMOP table and data source.  Key directories and files include:

* **SQL Scripts:**  Numerous `.sql` files containing the ETL processes for various OMOP tables (e.g., `person.sql`, `visit_occurrence.sql`, `condition_occurrence.sql`, etc.).  These are further categorized by data source (e.g., AMB, HSP, ANES) and data type (e.g.,  ICD, SNOMED, CPT).  `pull_*.sql` files likely represent the extraction step, while `app_*.sql` files appear to handle data application and transformation.
* **README.md:** This file provides critical information on the insertion and deletion order for the OMOP tables.

## Getting Started

This project requires a database system (e.g., PostgreSQL, MySQL) capable of executing SQL scripts.  The exact steps for running these scripts will depend on your chosen database and the Clarity data source connection details.  However, a general workflow would be:

1. **Database Setup:** Create a new database and user with appropriate permissions.
2. **Data Source Connection:** Configure access to your Clarity data source. This typically involves defining connection strings or environment variables.
3. **Sequential Execution:** The SQL scripts must be executed in the order specified by the `README.md`.  Begin with the tables at the beginning of the insertion order (`location.sql`, `care_site.sql`, etc.) and proceed sequentially to the tables at the end of the insertion order.
4. **Error Handling:** Implement robust error handling mechanisms to manage potential issues during script execution.

**Example (Illustrative):** Assuming you're using `psql` with a Postgres database:

```bash
psql -d my_omop_database -U my_user -f location.sql
psql -d my_omop_database -U my_user -f care_site.sql
...and so on, following the Insertion Order detailed in the README.
```

Remember to replace `my_omop_database` and `my_user` with your database name and user credentials, respectively.  Consult your database system's documentation for specific instructions on running SQL scripts.  Thorough testing is crucial after database population.  The deletion order, also specified in the README, will be necessary for database updates or complete data refreshes.
