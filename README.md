# Transportation Access and Potentially Preventable Emergency Room Visits

## Case Study of the Second Avenue Subway Expansion in New York City

**Zoe Frazer-Klotz | Master's thesis, Columbia University**

This repository contains the final thesis paper and accompanying R Markdown analysis code. The project examines whether the 2017 Second Avenue Subway expansion was associated with changes in potentially preventable emergency department visit (PPV) rates in New York City.

## Paper and Code

- [Read the final paper (PDF)](Frazer-Klotz_Thesis_.docx.pdf)
- [View the analysis code (R Markdown)](Frazer-Klotz_Thesis_Analysis_Code.Rmd)

Both files are preserved as supplied by the author. Raw data, working drafts, saved R sessions, and intermediate outputs are not included.

## Research Design

**Study 1** examines directly affected Upper East Side ZIP codes relative to selected Manhattan controls with comparable pre-treatment PPV rates.

**Study 2** examines the broader Q-line corridor, using demographic matching and analyses of heterogeneity by income and distance.

The analysis combines ZIP code-year panel data, spatial processing, difference-in-differences models, pre-trend assessments, and event studies, including Sun-Abraham estimates. Data sources include SPARCS, the American Community Survey (ACS), MTA subway stations, and NYC modified ZIP code tabulation areas (MODZCTAs).

## Findings and Interpretation

As reported in the final paper, Study 1's estimated post-expansion effect is positive but statistically nonsignificant. Study 2's results are largely null or mixed across specifications and subgroup analyses. Concerns about parallel trends and potential post-treatment bias in matching mean that Study 2 should be interpreted as exploratory rather than causal.

The findings do not provide evidence that the expansion reduced PPV rates; they also do not establish that it increased PPV rates or had no effect. See the paper for the full results and limitations.

## Running the Analysis

Use R and an R Markdown-capable environment, such as RStudio. The code loads these packages:

```r
install.packages(c(
  "dplyr", "ggplot2", "readr", "fixest", "broom", "tidycensus",
  "purrr", "tidyr", "sf", "stringr", "tidyverse", "MatchIt",
  "rmarkdown", "knitr"
))
```

Before running the Rmd:

1. Obtain the source datasets described in the paper. The script expects these local CSV files:
   - `Hospital_Emergency_Department_Discharges_(SPARCS_De-Identified)__Potentially_Preventable_Emergency_Visit_(PPV)_Rates_by_Patient_Zip_Code__Beginning_2011_20260322.csv`
   - `MTA_Subway_Stations_20251109.csv`
   - `Modified_Zip_Code_Tabulation_Areas_(MODZCTA)_20260329.csv`
2. Update the working directory and local CSV paths for your machine. The archived script retains the author's original paths.
3. Configure your own Census API key for the ACS requests. The script contains a placeholder that must be replaced or configured locally before execution. Do not commit a real key to GitHub.
4. Run the chunks in order, or render the document after completing the setup:

```r
rmarkdown::render("Frazer-Klotz_Thesis_Analysis_Code.Rmd")
```

ACS retrieval requires an internet connection and may take time. This repository is an archive of the submitted analysis, not a self-contained replication package: it does not include raw data or a locked R environment. The analysis was not rerun as part of repository preparation.

## Attribution

When referencing this work, credit Zoe Frazer-Klotz and the thesis title above. Consult the paper's references for the original data and methodological sources.
