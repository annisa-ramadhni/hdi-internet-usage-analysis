# HDI, Internet Usage, and Regional GDP Analysis in Indonesia

An academic group project that examines the relationship between internet usage, Human Development Index (HDI), and regional GDP per capita across Indonesian provinces from 2017 to 2019.

## Project Overview

This project analyzes whether differences in internet usage and regional economic conditions are associated with differences in HDI across Indonesian provinces.

Three datasets were combined for the analysis: internet usage data, subnational HDI data, and regional GDP per capita data. The datasets came in different formats and required data cleaning, standardization, integration, and exploratory analysis before statistical modeling.

The analysis was carried out using Python in Google Colab.

## Objectives

- Clean and standardize data from multiple sources.
- Integrate internet usage, HDI, and regional GDP per capita data by province and year.
- Explore patterns and relationships between the variables.
- Handle missing values using KNN Imputation.
- Detect potential outliers using the IQR approach.
- Compare simple and multiple linear regression models.
- Interpret the statistical results and identify relevant findings.

## Dataset

The analysis uses provincial-level data for 2017–2019.

### Variables

| Variable | Description |
|---|---|
| `nama_provinsi` | Province name |
| `tahun` | Observation year |
| `persentase_internet` | Percentage of individuals using the internet |
| `ipm` | Subnational Human Development Index |
| `pdrb_perkapita_dalam_ribu_rupiah` | Regional GDP per capita in thousand rupiah |

### Data Sources

- [Badan Pusat Statistik (BPS) – Internet Usage by Province](https://www.bps.go.id/id/statistics-table/2/MTIyNSMy/proporsi-individu-yang-menggunakan-internet-menurut-provinsi.html)
- [Global Data Lab – Subnational HDI](https://globaldatalab.org/shdi/table/shdi/IDN/)
- [Open Data Jabar – Regional GDP per Capita by Province](https://opendata.jabarprov.go.id/id/dataset/produk-domestik-regional-bruto-pdrb-per-kapita--atas-dasar-harga-berlaku-berdasarkan-provinsi-di-indonesia)

## Methodology

The project follows these main stages:

1. **Data Collection**  
   The original datasets were downloaded and loaded into Google Colab using Python.

2. **Data Cleaning and Formatting**  
   Each dataset was cleaned separately. This included removing unnecessary rows and columns, standardizing province names, converting data types, and preparing the data for integration.

3. **Data Integration**  
   The internet usage, HDI, and regional GDP datasets were merged using province name and year as the matching keys.

4. **Data Investigation**  
   Missing values, irrelevant records, and inconsistent values were identified before further analysis.

5. **Exploratory Data Analysis**  
   Descriptive statistics, histograms, scatter plots, trend analysis, and correlation analysis were used to understand the dataset.

6. **Missing Value Imputation**  
   KNN Imputer with `k=10` was applied to estimate missing numerical values based on similarities between observations.

7. **Outlier Detection**  
   Boxplots and the IQR method were used to identify potential outliers in the main numerical variables.

8. **Linear Regression Modeling**  
   Three regression models were developed:
   - Model 1: Internet usage → HDI
   - Model 2: Regional GDP per capita → HDI
   - Model 3: Internet usage + Regional GDP per capita → HDI

## Results

The analysis produced the following regression results:

| Model | R² | Main finding |
|---|---:|---|
| Internet → HDI | 0.437 | Positive and statistically significant relationship |
| GDP per capita → HDI | 0.310 | Positive and statistically significant relationship |
| Internet + GDP per capita → HDI | 0.467 | Highest explanatory power among the three models |

The multiple linear regression model produced the highest R² at **0.467**. Both internet usage and regional GDP per capita had positive coefficients and were statistically significant in the model.

These results indicate that provinces with higher internet usage and higher regional GDP per capita tended to have higher HDI values during the period studied.

## My Contributions

This project was completed as a group assignment with **Tamaela Nurandyapasa** and **Annisa Ramadhani**.

My contributions included:

- Cleaning and formatting the HDI dataset.
- Investigating the integrated dataset.
- Conducting data exploration.
- Detecting and identifying outliers using the IQR approach.
- Calculating and visualizing correlations between variables.
- Building linear regression models.
- Interpreting the results of Models 1, 2, and 3.
- Contributing to the final project report.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Statsmodels
- Google Colab

## Project Files

```text
hdi-internet-usage-analysis/
│
├── README.md
├── hdi_internet_usage_analysis.ipynb
└── .gitignore
