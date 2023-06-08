# Hasura Output Port Template

---

Use this template to create an Output Port based on a Hasura Enterprise instance.

## Using this Template

---

### Prerequisites

A Data Product should already exist in order to attach new components to it.

---

### Component Basic Information

This section includes the basic information that any component of Witboost must have -

- Name: Required name used for display purposes on your Data Product.


- Fully Qualified Name: Workload fully qualified name, this is optional as will be generated by the system if not given by you.


- Description: A short description to help others understand what this Workload is for.


- Domain: The Domain of the Data Product this Workload belongs to. Be sure to choose it correctly as is a fundamental part of the Workload and cannot be changed afterwards.


- Data Product: The Data Product this Workload belongs to, be sure to choose the right one.


- Identifier: Unique ID for this new entity inside the domain. Don't worry to fill this field, it will be automatically filled for you.


- Development Group: Development group of this Data Product. Don't worry to fill this field, it will be automatically filled for you.


- Depends On: If you want your workload to depend on other components from the Data Product, you can choose this option.

*Example:*

| Field name              | Example value                                                                                          |
|:------------------------|:-------------------------------------------------------------------------------------------------------|
| **Name**                | Hasura Vaccinations Output Port                                                                        |
| **Description**         | Offers insight in the COVID-19 Vaccinations data                                                       |
| **Domain**              | domain:healthcare                                                                                      |
| **Data Product**        | system:healthcare.vaccinationsdp.0                                                                     |
| ***Identifier***        | Will look something like this: *marketing.healthcare.0.snowflake-vaccinations-output-port*             |
| ***Development Group*** | Might look something like this: *group:datameshplatform* Depends on the Data Product development group |

---

### GraphQL Queries

This section will provide custom graphql information to track the tables in Hasura

- customTableName(Optional): Name used for display purposes. If not provided, default name would be placed which takes the form `<DOMAIN_NAME>_<DP_NAME>_<MAJOR_VERSION>_<USER_CUSTOM_NAME_OR_DEFAULT>`.
- select(Optional): select. If nothing is provided, it derives its name from the above table name.
- select by pk(Optional): select by pk. If nothing is provided, it derives its name from the above table name appended with `_by_pk`.
- select aggregate(Optional): select aggregate. If nothing is provided, it derives its name from the above table name appended with `_aggregate`.
- select stream(Optional): select stream. If nothing is provided, it derives its name from the above table name appended with `_stream`.

| Field name           | Example value                                  |
|:---------------------|:-----------------------------------------------|
| **customTableName**  | HEALTHCARE_VACCINATIONSDBT_0_VACCINE           |
| **select**           | HEALTHCARE_VACCINATIONSDBT_0_VACCINE           |
| **select by pk**     | HEALTHCARE_VACCINATIONSDBT_0_VACCINE_pk        |
| **select aggregate** | HEALTHCARE_VACCINATIONSDBT_0_VACCINE_aggregate |
| **select stream**    | HEALTHCARE_VACCINATIONSDBT_0_VACCINE_stream    |


After this the system will show you the summary of the template, and you can go back and edit or go ahead and create the Component.

After clicking on "Create" the registering of the Component will start. If no errors occurred it will go through the 3 phases (Fetching, Publishing and Registering) and will give you the links to the newly created Repository and the component in the Catalog.