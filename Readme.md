# Python project part one - data cleaning

---

## The Project brief
The administration of a well known retail store is interested in using data collected over time from their various branches to understand consumer behaviour in the different regions of the country. Our plan is to create interactive visualisations for them generated from their data which tells a story about their customers.
They’ve provided 10 years worth of data collected from all available branches. The data is inconsistent in terms of format and content as the data collection and storage strategy is decided by the manager of a store branch.
This project is split into two parts, data cleaning and visualisations. This is the data cleaning part.

---

## User stories
- As an administrator, I want to see 5 most and 5 least purchased products by:
    - product 
    - product category
    - per region
    - per city
- As an administrator, I want to see 10 best and 10 worst performing branches:
    - overall  
        - quantity sold
        - monetary value
    - per region
        - quantity sold
        - monetary value
    - per city
        - quantity sold
        - monetary value
- As an administrator, I want to see top 10 performing branches in sales per hour
- As an administrator, I want to see top 10 and bottom 10 profitable branches and show how profitable they are
---
## Used technologies
- Python
- Libraries: pandas, petl, glob
---
## Taken approach

1. Wrote down user stories based on project brief
2. Extract what data fields are going to be needed to achieve customers requirements
3. Grouped CSV and JSON files into two large CSV files 
    a. Grouped each group (csv or json) files into dataframe 
    b. Replaced '-' with '0' as some values in quantity column were not numbers 
    c. Replaced quantity column that was saved in string format with duplicated quantity column that was converted to numbers 
    d. Saved to .csv file
4. Prepare diagrams and schemas for building datasets for final visualisations: 
    a. Required columns:
![Required columns](/schemas/required_columns.JPG)
    b. Diagram to show how data is going to be connected
![Datasets connections](/schemas/data_connections.JPG)
    c. Drafted how is the functionality of final script going to work. See wireframes below
![Data preparation wireframes](/schemas/data_preparation_schemas.jpg)
5. Based on diagrams, I build script that grouped main sales datasets from previous step and then created four separate csv files for making visualisations.

### Diagram of data cleaning process:
![Data cleaning process diagram](/schemas/data_prep_flow.jpg)

---

## Next development
- Based on customer requirements no other development is needed, however I would advise customer to have visualisations per year/month/day as well as from my personal experience, this would provide much better overview of market and customer behaviour.

---
## List of favourite functions
- Grouping data from all files using glob - I had to search internet to find how this can be done and the outcome saves a lot of time in comparison to appending dataframes manually.
---
## Difficulties during development
- Grouping all data - here I did not know how to group all of the data files into one file. I have found a library called glob, that allowed to group all data to one dataframe.
-  Converting etl table to pd dataframe took extremely long time as well as other operations related to manipulation of this large dataframes. 
    -  For this reason I created two separate grouped files, one from CSV files and other one from JSON files
    - In order to understand how much time is required for data operations, I times sample data and calculate approximate times of running half of dataset (only csv files) and full dataset (all csv and json files). Below image shows my notes:
![Timing of runtimes](/schemas/Datasets timing.jpg)
---
## List of known issues
 - no known issues
 
 ---
## Used resources
- Glob article: [Article about glob](https://medium.com/python-pandemonium/how-to-import-data-from-multiple-text-files-in-python-c3956a878fe0)
- video of grouiping all files: [Video about using glob](https://www.youtube.com/watch?v=8MZIcUoNW6Y)
