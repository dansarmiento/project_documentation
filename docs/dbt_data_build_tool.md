# dbt_data_build_tool: Data Modeling with dbt

## Overview

This project demonstrates the benefits of using dbt (data build tool) for building and managing data models.  It translates a traditional SQL view (`vw_patient_profile_consolidated`) into a series of modular dbt models, improving maintainability, scalability, and data governance. This approach leverages dbt's features for modularity, testing, version control, and automated documentation generation, resulting in a more robust and manageable analytics pipeline.

## Key Features

* **Modular Data Modeling:**  Breaks down complex transformations into smaller, reusable dbt models.
* **Automated Testing:** Implements data quality checks using dbt's testing framework.
* **Version Control:** Manages models as `.sql` files within Git for collaboration and tracking changes.
* **Automated Documentation:** Generates a searchable data dictionary using `dbt docs generate`.
* **Environment Management:** Supports deployment across multiple environments (Dev, Staging, Prod).
* **Performance Optimization:** Allows for flexible materialization strategies (view, table, incremental).
* **Clear Data Lineage:** Provides a visual DAG (Directed Acyclic Graph) illustrating model dependencies.


## Project Structure

The project is organized as follows:

* **`LICENSE`:**  The project's open-source license.
* **`README.md`:** This documentation file.
* **`dbt_patient_profile`:** The core dbt project directory.
    * **`dbt_project.yml`:** The dbt project configuration file.
    * **`models`:** Contains all dbt models, organized into subfolders:
        * **`staging`:**  Initial data transformation models (e.g., `stg_visits.sql`, `stg_visit_scheduled.sql`).
        * **`intermediate`:** Intermediate transformation models (e.g., `int_demographics.sql`, `int_dept_counts.sql`, `int_visit_agg.sql`, `int_visit_total.sql`).
        * **`marts`:** Final, consolidated fact tables (e.g., `fct_patient_profile_consolidated.sql`).
* **`rpt_patient_profile.sql`:** (Likely a legacy SQL view that the dbt models replace).


## Getting Started

This project requires dbt to be installed.  Follow the instructions on the [dbt website](https://www.getdbt.com/) for installation.  Once installed:

1. **Clone the repository:** `git clone <repository_url>`
2. **Navigate to the project directory:** `cd dbt_data_build_tool/dbt_patient_profile`
3. **Configure your dbt profile:**  You'll need to create a `profiles.yml` file (see dbt documentation for details) pointing to your data warehouse.
4. **Run dbt:**
   * To compile the models: `dbt run`
   * To test the models: `dbt test`
   * To generate documentation: `dbt docs generate`


This will build the dbt models, run any associated tests, and (optionally) generate documentation based on your configured profile.  The specific SQL used for each model is defined in the `.sql` files within the `models` directory. Examine `fct_patient_profile_consolidated.sql` for an example of how the final consolidated model incorporates the intermediate models.  Remember to consult the dbt documentation for more advanced usage and configuration options.
