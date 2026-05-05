# Milestone 02: Air Quality and Asthma Analysis

## Setup Instructions

This project uses a virtual environment so that the required Python packages are installed cleanly and do not conflict with other projects.

### 1. Create a virtual environment

On Windows PowerShell, run:

```powershell
py -m venv .venv

## Research Question

Is there a relationship between county-level PM2.5 air pollution and adult asthma prevalence in the United States?

This project uses Python to retrieve public data, clean and merge datasets, conduct exploratory analysis, and create visualizations. The goal is not to prove causation, but to examine whether counties with higher measured PM2.5 concentrations also tend to report higher estimated adult asthma prevalence.

## Data Sources

### CDC PLACES
The CDC PLACES dataset provides county-level estimates for health outcomes, including current asthma among adults. The notebook retrieves the dataset from the CDC Socrata open data API.

Source used in notebook:
`https://data.cdc.gov/resource/swc5-untb.csv?$limit=500000`

### EPA AirData
The EPA AirData annual concentration file provides monitor-level air quality measurements. The notebook uses the 2023 annual concentration file and filters for PM2.5 FRM/FEM Mass using parameter code `88101`.

Source used in notebook:
`https://aqs.epa.gov/aqsweb/airdata/annual_conc_by_monitor_2023.zip`

## Project Files

- `air_quality_asthma_analysis.ipynb`: Main Jupyter Notebook containing the analysis.
- `requirements.txt`: Python packages needed to run the notebook.
- `data/`: Folder where cleaned CSV outputs are saved.
- `outputs/`: Folder where visualizations are saved.

## Methods

1. Load county-level asthma estimates from CDC PLACES.
2. Load EPA monitor-level annual PM2.5 data.
3. Clean both datasets and create 5-digit county FIPS codes.
4. Aggregate EPA monitor-level PM2.5 data to the county level.
5. Merge the CDC and EPA datasets using county FIPS codes.
6. Calculate descriptive statistics and a correlation coefficient.
7. Create visualizations showing the relationship between PM2.5 and asthma prevalence.

## Expected Outputs

The notebook produces:

- `data/cdc_asthma_county_clean.csv`
- `data/epa_pm25_county_clean.csv`
- `data/merged_air_quality_asthma.csv`
- `outputs/pm25_vs_asthma_scatter.png`
- `outputs/top_pm25_counties.png`
- `outputs/state_average_pm25.png`

## Limitations

This analysis is exploratory and should not be interpreted as causal. Asthma prevalence is influenced by many factors beyond air quality, including smoking rates, housing quality, occupational exposure, healthcare access, and demographics. EPA monitor coverage also varies by county, meaning some counties do not have monitor-level PM2.5 data available in the EPA file.

## How to Run

1. Clone or download this repository.
2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Open the notebook:

```bash
jupyter notebook air_quality_asthma_analysis.ipynb
```

4. Run all cells from top to bottom.

## Summary

This project demonstrates Python skills including web data retrieval, dataframe cleaning, filtering, grouping, merging, summary statistics, and visualization with matplotlib.
