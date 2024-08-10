# SQL_DataCleaning_NashvilleHousingData
# Housing Data Transformation with SQL Server

## Project Overview

This project focuses on cleaning raw housing data using SQL Server to make it more understandable and suitable for analysis. The goal is to prepare the data by removing inconsistencies and formatting it properly, which will facilitate better insights into housing trends and other metrics.

## Data Source

The raw housing data used in this project is contained in a single Excel file:

- **NashvilleHousing.xlsx** - Contains the initial raw data with housing information.

## How to Use

To work with this project, follow these steps:

1. **Set Up SQL Server**:
   - Install SQL Server if it’s not already installed on your computer.
   - Create a new database named `HousingData`.
   - Import the `NashvilleHousingData.xlsx` file into the database.

2. **Run the SQL Query**:
   - Use the provided SQL query file to clean and transform the data. This may involve:
     - Removing inconsistencies.
     - Standardizing data formats.

3. **Analyze the Cleaned Data**:
   - Once the data is cleaned, you can run additional SQL queries to generate insights and better understand the housing data.

## SQL Query File

The project includes one SQL query file for data cleaning:

- **NashvilleHousingData.sql** - Contains SQL queries for cleaning and preparing the data.

### Example SQL Transformation

Here is an example SQL query for standardizing date formats:

```sql
-- Verify Existing Date Conversion
SELECT SaleDateConverted, CONVERT(Date, SaleDate)
FROM PortfolioProject..NashvilleHousing;

-- Add a New Column for Standardized Dates
ALTER TABLE NashvilleHousing
ADD SaleDateConverted DATE;

-- Update the New Column with Converted Dates
UPDATE NashvilleHousing
SET SaleDateConverted = CONVERT(DATE, SaleDate);
