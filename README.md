# HDI, Internet Usage, and Regional GDP Analysis in Indonesia

An academic data analysis project examining the relationship between internet usage, Human Development Index (HDI), and regional GDP per capita across Indonesian provinces from 2017 to 2019.

The project focuses on data wrangling, exploratory data analysis, statistical analysis, and linear regression modeling to investigate whether differences in internet usage and regional economic conditions are associated with differences in HDI.

---

## Project Overview

Internet access and regional economic conditions are two factors that may be associated with differences in human development across regions.

This project combines provincial-level data on:

- Internet usage
- Subnational Human Development Index (HDI)
- Regional GDP per capita

The original datasets were obtained from different sources and had different structures and formats. Therefore, the analysis involved several data preparation stages, including data cleaning, standardization, integration, missing-value handling, exploratory analysis, outlier detection, correlation analysis, and statistical modeling.

The analysis was conducted using Python in Google Colab.

The final analysis uses linear regression models to examine the statistical association between:

1. Internet usage and HDI.
2. Regional GDP per capita and HDI.
3. Internet usage and regional GDP per capita simultaneously as predictors of HDI.

> **Note:** The analysis identifies statistical associations within the observed data and does not establish causal relationships.

---

## Objectives

The main objectives of this project are to:

- Clean and standardize datasets obtained from multiple sources.
- Integrate internet usage, HDI, and regional GDP per capita data by province and year.
- Investigate the structure and characteristics of the integrated dataset.
- Explore patterns and relationships between the main variables.
- Handle missing numerical values using KNN Imputation.
- Identify potential outliers using the Interquartile Range (IQR) method.
- Calculate and visualize correlations between variables.
- Develop and compare linear regression models.
- Apply heteroscedasticity-robust standard errors (HC3) to the final multiple regression model.
- Interpret the statistical results within the context of the observed provincial data.

---

## Dataset

The analysis uses provincial-level observations covering the period **2017–2019**.

### Main Variables

| Variable | Description |
|---|---|
| `nama_provinsi` | Province name |
| `tahun` | Observation year |
| `persentase_internet` | Percentage of individuals using the internet |
| `ipm` | Subnational Human Development Index |
| `pdrb_perkapita_dalam_ribu_rupiah` | Regional GDP per capita in thousand rupiah |

### Data Sources

The datasets used in this project were obtained from:

- **Badan Pusat Statistik (BPS)** — Internet usage by province
- **Global Data Lab** — Subnational Human Development Index (SHDI)
- **Open Data Jabar** — Regional GDP per capita by province

The original source references are also documented in the analysis notebook.

---

## Data Preparation

Because the datasets originated from different sources, the data required several preparation steps before analysis.

The preparation process included:

1. Loading the original datasets.
2. Inspecting the structure and contents of each dataset.
3. Removing unnecessary rows and columns.
4. Standardizing province names.
5. Converting variables into appropriate data types.
6. Preparing year information for integration.
7. Merging the datasets using province and year as matching keys.
8. Investigating missing and inconsistent values.
9. Preparing the integrated dataset for exploratory analysis and statistical modeling.

The processed source datasets are included in the `data/` directory of this repository.

---

## Methodology

The project follows a data analysis workflow consisting of the following stages.

### 1. Data Collection

The original datasets were collected from BPS, Global Data Lab, and Open Data Jabar.

The datasets contain information related to internet usage, HDI, and regional GDP per capita across Indonesian provinces.

### 2. Data Cleaning and Formatting

Each dataset was inspected and cleaned individually.

The process included:

- Removing unnecessary rows and columns.
- Standardizing province names.
- Converting variables into appropriate data types.
- Preparing year information.
- Checking the consistency of the data structure.

### 3. Data Integration

The cleaned datasets were integrated using:

- Province name
- Observation year

This produced an integrated dataset containing internet usage, HDI, and regional GDP per capita variables.

### 4. Data Investigation

The integrated dataset was investigated to identify:

- Missing values
- Irrelevant records
- Inconsistent values
- Data structure and variable characteristics

### 5. Exploratory Data Analysis

Exploratory analysis was conducted to understand the characteristics and relationships within the data.

The analysis included:

- Descriptive statistics
- Histograms
- Scatter plots
- Trend analysis
- Correlation analysis

### 6. Missing Value Imputation

Missing numerical values were handled using **KNN Imputation** with:

```text
k = 10
```

The method estimates missing values based on similarities between observations.

### 7. Outlier Detection

Potential outliers in the main numerical variables were investigated using:

- Boxplots
- Interquartile Range (IQR)

The analysis was used to identify observations that may require additional attention during interpretation.

### 8. Correlation Analysis

Correlation analysis was conducted to investigate the strength and direction of relationships between the main numerical variables.

The results were visualized to make the relationships between internet usage, HDI, and regional GDP per capita easier to interpret.

### 9. Linear Regression Modeling

Three linear regression models were developed.

#### Model 1 — Internet Usage and HDI

```text
HDI ~ Internet Usage
```

This model examines the relationship between the percentage of individuals using the internet and HDI.

#### Model 2 — Regional GDP per Capita and HDI

```text
HDI ~ Regional GDP per Capita
```

This model examines the relationship between regional GDP per capita and HDI.

#### Model 3 — Multiple Linear Regression

```text
HDI ~ Internet Usage + Regional GDP per Capita
```

This model examines the relationship between HDI and the two predictors simultaneously.

### 10. Robust Standard Errors

The final multiple linear regression model uses **HC3 heteroscedasticity-robust standard errors**.

The robust standard errors were used when interpreting the statistical significance of the regression coefficients.

---

## Results

### Regression Model Comparison

The regression models produced the following R² values:

| Model | R² | Main Finding |
|---|---:|---|
| Internet Usage → HDI | 0.437 | Positive and statistically significant relationship |
| Regional GDP per Capita → HDI | 0.310 | Positive and statistically significant relationship |
| Internet Usage + Regional GDP per Capita → HDI | 0.417 | Positive and statistically significant relationships for both predictors |

The final multiple linear regression model achieved:

- **R²:** 0.417
- **Adjusted R²:** 0.406

### Final Multiple Regression Model

After applying HC3 robust standard errors, both predictors remained statistically significant.

| Predictor | Coefficient | p-value (HC3) |
|---|---:|---:|
| Internet Usage | 0.0007804 | 0.00178 |
| Regional GDP per Capita | 0.0000001276 | 0.00937 |

Based on the fitted model, both internet usage and regional GDP per capita have positive estimated coefficients.

Within the observed data, provinces with higher internet usage tended to have higher HDI values, while provinces with higher regional GDP per capita also tended to have higher HDI values.

However, these findings represent **statistical associations rather than causal effects**. The results should therefore not be interpreted as evidence that increasing internet usage or regional GDP per capita directly causes an increase in HDI.

### Multicollinearity Check

The final analysis also checked multicollinearity using the Variance Inflation Factor (VIF).

The notebook reports that there was no serious multicollinearity based on the VIF analysis.

---

## Key Findings

The analysis provides several observations from the 2017–2019 provincial-level data:

1. Internet usage shows a positive and statistically significant relationship with HDI in the regression analysis.
2. Regional GDP per capita also shows a positive and statistically significant relationship with HDI.
3. The multiple regression model incorporating both internet usage and regional GDP per capita achieved an R² of 0.417.
4. Both predictors remained statistically significant after applying HC3 robust standard errors.
5. The analysis describes relationships observed in the data and does not establish causality.

---

## Project Structure

```text
hdi-internet-usage-analysis/
│
├── data/
│   ├── Indeks Pembangunan Manusia di Indonesia.csv
│   ├── Proporsi Individu Yang Menggunakan Internet Menurut Provinsi, 2017.csv
│   ├── Proporsi Individu Yang Menggunakan Internet Menurut Provinsi, 2018.csv
│   ├── Proporsi Individu Yang Menggunakan Internet Menurut Provinsi, 2019.csv
│   ├── produk_dmstk_regional_bruto_pdrb_per_kapita.csv
│   └── README.md
│
├── hdi_internet_usage_analysis.ipynb
├── README.md
└── .gitignore
```

### File Descriptions

| File / Directory | Description |
|---|---|
| `data/` | Source datasets used in the analysis |
| `data/README.md` | Documentation of the datasets, variables, sources, and data preparation |
| `hdi_internet_usage_analysis.ipynb` | Complete analysis notebook containing data preparation, EDA, statistical analysis, regression modeling, and results |
| `README.md` | Project documentation |
| `.gitignore` | Files and directories excluded from version control |

---

## Tools and Technologies

The project was developed using Python and the following libraries and tools:

- **Python** — Main programming language
- **Pandas** — Data manipulation and analysis
- **NumPy** — Numerical computation
- **Matplotlib** — Data visualization
- **Seaborn** — Statistical visualization
- **Scikit-learn** — KNN imputation and machine learning utilities
- **Statsmodels** — Statistical modeling and regression analysis
- **Google Colab** — Development environment
- **GitHub** — Project version control and documentation

---

## Notebook

The complete analysis is available in [`hdi_internet_usage_analysis.ipynb`](./hdi_internet_usage_analysis.ipynb).

The notebook contains:

- Dataset loading
- Data inspection
- Data cleaning
- Data integration
- Missing-value handling
- Exploratory data analysis
- Outlier detection
- Correlation analysis
- Linear regression
- HC3 robust standard errors
- Statistical interpretation
- References

---

## Reproducibility

The source datasets used in the analysis are included in the `data/` directory so that the project's data structure and source files can be inspected directly from the repository.

The main analysis is documented in the Jupyter Notebook:

[`hdi_internet_usage_analysis.ipynb`](./hdi_internet_usage_analysis.ipynb)

The notebook was originally developed and executed using Google Colab.

The main Python libraries required for the analysis include:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
```

---

## Project Context

This project was completed as an **academic group assignment** focused on data wrangling and statistical analysis.

The project demonstrates practical experience in:

- Working with datasets from multiple sources.
- Cleaning and standardizing real-world data.
- Integrating datasets with different structures.
- Performing exploratory data analysis.
- Handling missing values.
- Investigating potential outliers.
- Performing correlation analysis.
- Building statistical regression models.
- Applying robust standard errors.
- Interpreting statistical results.
- Documenting an end-to-end data analysis workflow.

---

## My Contributions

This project was completed as a group assignment with **Tamaela Nurandyapasa** and **Annisa Ramadhani**.

As a group member, my contributions included:

- Cleaning and formatting the HDI dataset.
- Investigating the integrated dataset.
- Conducting exploratory data analysis.
- Detecting and identifying potential outliers using the IQR approach.
- Calculating and visualizing correlations between variables.
- Building linear regression models.
- Interpreting the results of Models 1, 2, and 3.
- Contributing to the final project report.

---

## Limitations

Several limitations should be considered when interpreting the results:

- The analysis covers the period **2017–2019**.
- The unit of analysis is the Indonesian province.
- The regression analysis identifies statistical associations and does not establish causality.
- The datasets originate from different sources and therefore required data cleaning and integration before analysis.
- Missing values were handled using KNN imputation, which introduces estimated rather than directly observed values.
- Potential outliers were identified using the IQR approach and were considered during the analysis.

---

## References

The project references the following sources:

1. Gagolewski, M. — *Chapter 430: Group by — Minimalist Data Wrangling with Python*.
2. Google Colab Notebook — Data Wrangling Pertemuan 7.
3. Google Colab Notebook — Data Wrangling Pertemuan 8.
4. Badan Pusat Statistik (BPS) — Proporsi Individu yang Menggunakan Internet Menurut Provinsi.
5. Global Data Lab — Subnational Human Development Index (SHDI), Indonesia.
6. Open Data Jabar — Produk Domestik Regional Bruto (PDRB) per Kapita berdasarkan Provinsi.

The complete source references and access dates are documented in the project notebook.

---

## Author

**Annisa Ramadhani**

Data Science Student

GitHub: [@annisa-ramadhni](https://github.com/annisa-ramadhni)

---

## Acknowledgements

This project was completed as part of an academic group assignment.

Thanks to the data providers and institutions whose datasets were used in this analysis, including:

- Badan Pusat Statistik (BPS)
- Global Data Lab
- Open Data Jabar

---

## Disclaimer

This repository contains an academic data analysis project created for educational and portfolio purposes.

The findings presented in this project are based on the available datasets and analytical methods used during the study period. The statistical relationships reported should not be interpreted as causal conclusions without further research and additional supporting evidence.
