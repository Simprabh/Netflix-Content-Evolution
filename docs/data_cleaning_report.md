# Data Cleaning Report

## Project: The Evolution of Netflix Content

**Dataset:** Netflix Movies and TV Shows (`netflix_titles.csv`)

### Cleaning Performed
- Inspected missing values and duplicate records.
- Replaced missing descriptive values with `Unknown`.
- Corrected rating and duration inconsistencies.
- Converted `date_added` into datetime format.
- Created a new column, `year_added`.
- Standardized text and comma-separated values.

### Final Validation
- Total records: 8,807
- Total columns: 13
- Duplicate rows: 0
- Duplicate IDs: 0
- Missing dates: 10

### Output
The cleaned dataset is saved as `data/netflix_titles_cleaned.csv` and is ready for exploratory data analysis.
