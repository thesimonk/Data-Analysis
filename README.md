# Nairobi Healthcare Accessibility Analysis

## Overview
This project analyzes healthcare accessibility in Nairobi, Kenya, across its sub-counties, using data from the 2019 Kenya Population and Housing Census and a dataset of 287 primary healthcare facilities. The analysis aligns with Sustainable Development Goal 3 (Good Health and Well-Being) by identifying disparities in healthcare access, measured by facilities per 100,000 people and per km², population per facility, and access gaps relative to the WHO threshold (~10 facilities per 100,000). The results are visualized using Seaborn barplots and exported to a CSV file for sharing.

## Objectives
- Merge population, household size, land area, and facility data for Nairobi sub-counties.
- Calculate accessibility metrics (facilities per 100,000 people, per km², population per facility).
- Identify underserved sub-counties (e.g., Mathare, Kasarani) for targeted interventions.
- Provide visualizations and recommendations to support policy decisions.

## Data Sources
- **Population and Sex Distribution**: [2019 Census, Population by Sex and Sub-County](https://open.africa/dataset/9b94fe50-9d75-4b92-be00-6354c6e6cc88/resource/ddddbe91-b5fa-4449-a50d-846401e701c4/download/distribution-of-population-by-sex-and-sub-county-2019-census-volume-ii.csv)
- **Household Size**: [2019 Census, Average Household Size by Sub-County](https://open.africa/dataset/9b94fe50-9d75-4b92-be00-6354c6e6cc88/resource/27107613-0f4b-481b-88ea-8c83165130d2/download/kenya-average-household-size-by-sub-county.csv)
- **Land Area and Population Density**: [2019 Census, Population by Land Area and Density](https://open.africa/dataset/9b94fe50-9d75-4b92-be00-6354c6e6cc88/resource/4f04a378-0887-498c-b559-7ba000df35a0/download/distribution-of-population-by-land-area-density-and-sub-county-2019-census-volume-ii.csv)
- **Health Facilities**: Dataset with 287 primary healthcare facilities in Nairobi, including `District` (sub-county) and other attributes (e.g., `Facility Name`, `Type`).

## Notebook Structure
The analysis is implemented in a Jupyter Notebook (`Nairobi_Healthcare_Analysis.ipynb`) with the following cells:

1. **Cell 2**: Loads the health facilities dataset, confirms 287 facilities in Nairobi, and displays sample data (e.g., `Facility Name`, `District`).
2. **Cell 3**: Loads and merges population, household size, and land area/density data for Nairobi sub-counties, cleaning sub-county names for consistency.
3. **Cell 4**: Calculates accessibility metrics using actual facility counts from `District`, including facilities per 100,000 people and per km², with Seaborn barplots.
4. **Cell 5**: Adds `Population_Per_Facility` and `Access_Gap` (based on WHO threshold of 10 facilities per 100,000), with a sorted barplot highlighting underserved areas.
5. **Cell 6**: Summarizes key metrics (e.g., average facilities per 100,000), exports results to `nairobi_healthcare_access.csv`, and provides a conclusion.
6. **Summary Markdown**: Highlights findings (e.g., Mathare and Kasarani underserved, Langata’s low spatial coverage), recommendations (e.g., expand facilities, mobile clinics), and next steps (e.g., geospatial analysis).

## Key Findings
- **Adequate Access**: Kasarani (10.62 per 100,000), Langata (29.13), Starehe (10.43), and Westlands (14.50) meet or exceed the WHO threshold.
- **Underserved Areas**: Mathare (8.83 per 100,000, 11,324 people per facility), Kamukunji (9.33, 10,722), and Makadara (9.74, 10,262) fall below the threshold, indicating access gaps.
- **Spatial Disparities**: Mathare’s high density (68,855/km²) yields high facilities per km² (6.08), while Langata’s large area (217 km²) results in low spatial coverage (0.27 per km²).

## Recommendations
- Expand facilities in Mathare and Kamukunji to address high population-to-facility ratios.
- Deploy mobile clinics or improve transport in Langata to mitigate distance-related barriers.
- Validate facility counts and collect capacity data (e.g., beds, staff) for deeper analysis.

## Dependencies
- Python 3.8+
- Libraries: `pandas`, `matplotlib`, `seaborn`
- Install via pip:
  ```bash
  pip install pandas matplotlib seaborn