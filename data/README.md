# Dataset

This folder contains the datasets used in the analysis of internet usage, Human Development Index (HDI), and regional GDP per capita across Indonesian provinces from 2017 to 2019.

## Dataset Files

| File | Description |
|---|---|
| `Proporsi Individu Yang Menggunakan Internet Menurut Provinsi, 2017.csv` | Provincial internet usage data for 2017 |
| `Proporsi Individu Yang Menggunakan Internet Menurut Provinsi, 2018.csv` | Provincial internet usage data for 2018 |
| `Proporsi Individu Yang Menggunakan Internet Menurut Provinsi, 2019.csv` | Provincial internet usage data for 2019 |
| `Indeks Pembangunan Manusia di Indonesia.csv` | Human Development Index (HDI) data |
| `produk_dmstk_regional_bruto_pdrb_per_kapita.csv` | Regional GDP per capita data |

## Main Variables

The datasets contain information related to the following variables:

- `nama_provinsi` — Province name
- `tahun` — Observation year
- `persentase_internet` — Percentage of individuals using the internet
- `ipm` — Human Development Index
- `pdrb_perkapita_dalam_ribu_rupiah` — Regional GDP per capita in thousand rupiah

## Data Sources

The datasets were obtained from the following sources:

- **Badan Pusat Statistik (BPS)** — Internet usage by province
- **Global Data Lab** — Subnational Human Development Index
- **Open Data Jabar** — Regional GDP per capita by province

## Data Preparation

Before analysis, the datasets were processed to ensure that they could be integrated consistently.

The preparation process included:

1. Cleaning unnecessary rows and columns.
2. Standardizing province names.
3. Converting variables into appropriate data types.
4. Preparing year information for integration.
5. Combining the datasets using province and year as matching keys.
6. Checking missing values and inconsistent records before statistical analysis.

## Data Usage

The datasets were used to examine the relationship between:

- Internet usage and HDI.
- Regional GDP per capita and HDI.
- Internet usage and regional GDP per capita simultaneously in a multiple linear regression model.

The analysis covers provincial-level observations for the period **2017–2019**.

## Notes

The datasets in this folder are the source data used for the academic analysis documented in the main project README and notebook.
