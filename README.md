# Netflix Dataset Data Cleaning

This project involved cleaning and preprocessing the Netflix movies and TV shows dataset to prepare it for analysis.

## Files
- `unclean_Netflix_movies_and_tv_shows.csv` - Original dataset with data quality issues
- `cleaned_Netflix_movies_and_tv_shows.csv` - Cleaned and processed dataset
- `dataCleaning.ipynb` - Jupyter notebook containing the cleaning process

## Dataset Overview
- **Total Records**: 7,787 entries
- **Columns**: 12 (show_id, type, title, director, cast, country, date_added, release_year, rating, duration, listed_in, description)
- **Content Types**: Movies and TV Shows

## Data Quality Issues Identified

### Missing Values
- **Director**: 2,389 missing values (30.7%)
- **Cast**: 718 missing values (9.2%)
- **Country**: 507 missing values (6.5%)
- **Date Added**: 10 missing values (0.1%)
- **Rating**: 7 missing values (0.1%)

### Data Inconsistencies
- Date format inconsistency (e.g., "August 14, 2020" vs standardized format)
- Country name variations (e.g., "USA", "United States Of America")
- Rating format inconsistencies (e.g., "Tv-Ma", "Nr")
- Leading/trailing whitespace in text fields

## Cleaning Process

### 1. Missing Value Treatment
- **Director**: Filled with "Unknown"
- **Cast**: Filled with "Unknown"
- **Country**: Filled with "Unknown"
- **Rating**: Filled with "Not Rated"
- **Date Added**: Filled with "01-01-2020" and converted to DD-MM-YYYY format

### 2. Data Standardization
- **Column Names**: Converted to lowercase with underscores (e.g., "date_added")
- **Date Format**: Standardized to DD-MM-YYYY format
- **Text Fields**: Removed leading/trailing spaces
- **Type**: Standardized to title case ("Movie", "TV Show")
- **Country**: Standardized to title case
- **Rating**: Standardized to uppercase

### 3. Data Consistency
- **Country Mapping**:
  - "United States Of America" → "United States"
  - "Usa" → "United States"
  - "Uk" → "United Kingdom"
- **Rating Mapping**:
  - "Tv-Ma" → "TV-MA"
  - "Tv14" → "TV-14"
  - "Pg " → "PG"
  - "Nr" → "Not Rated"

### 4. Duplicate Removal
- Checked for and removed duplicates (none found in this dataset)

## Results
- **Clean Dataset**: 7,787 records with no missing values
- **Standardized Formats**: Consistent date, country, and rating formats
- **Data Quality**: Improved data consistency and reliability for analysis

## Usage
The cleaned dataset (`cleaned_Netflix_movies_and_tv_shows.csv`) is ready for:
- Exploratory data analysis
- Statistical analysis
- Machine learning applications
- Data visualization
- Business intelligence reporting