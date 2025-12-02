# Homework 1 – Data Validation & Cleaning  
**Dataset:** The Metropolitan Museum of Art — *Open Access* (MetObjects.csv)

## Overview  
This project examines, validates, and cleans the Metropolitan Museum of Art Open Access dataset. The work moves from exploratory analysis to rule-based quality checks, anomaly detection, and construction of standardized variables, with the aim of producing a more reliable dataset for further research.

## Dataset Description  
The **MetObjects.csv** file provides object-level metadata for artworks in The Met’s collection. Typical fields include:

- **Identifiers:** `ObjectID`, `Object Number`  
- **Textual metadata:** `Title`, `Artist Display Name`, `Culture`, `Medium`, `Credit Line`  
- **Dates:** `Object Begin Date`, `Object End Date`  
- **Dimensions:** raw `Dimensions` text plus parsed values (`Height_cm`, `Width_cm`, `Depth_cm`)  
- **Classification & geography:** `Department`, `Object Name`, `Country`, `City`

The data contains inconsistencies, missing values, mixed formats, and ambiguous strings, making systematic cleaning necessary.

## Work Completed

### 1. Initial Exploration  
- Loaded the dataset and reviewed structure, variable types, and representative rows.  
- Identified fields with irregular formats, missing values, and inconsistent units.

### 2. Parsing & Standardizing Dimensions  
- Extracted numeric measurements from free-text dimension strings.  
- Normalized units into centimeters.  
- Added standardized fields: `Height_cm`, `Width_cm`, `Depth_cm`.

### 3. Data Validation Rules  
Several plausibility checks were applied:

- **Absolute checks:** Confirmed that height, width, and depth fall within reasonable physical bounds and are positive.  
- **Relative checks:** Flagged objects exhibiting improbable dimensional relationships or extreme aspect ratios.  
- Generated boolean indicators such as `dimension_outlier`.

### 4. Outlier Detection  
- Used distributional summaries to identify and list objects with suspicious dimension values.  
- Produced a structured outlier report for further review.

### 5. Missing-Value Assessment  
- Quantified missingness across key fields.  
- Evaluated patterns in incomplete geographic and temporal metadata.  
- Considered how these gaps affect downstream analyses.

### 6. Consistency Checks on Dates  
- Compared `Object Begin Date` and `Object End Date` to verify chronological order.  
- Flagged cases where the end date precedes the begin date or spans implausible periods.

### 7. Cleaning Workflow  
- Worked on a dedicated copy of the dataset to preserve reproducibility.  
- Added new cleaned features and validation flags step by step.  
- Generated summaries at each stage to assess the effect of the cleaning operations.

### 8. Conclusions  
The project highlights challenges typical of large-scale cultural heritage datasets—irregular metadata, free-text fields with embedded units, ambiguous historical information, and structural inconsistencies. The cleaned dataset is substantially more usable, though several flagged records require manual review or expert input.
