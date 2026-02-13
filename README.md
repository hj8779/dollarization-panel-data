[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18629367.svg)](https://doi.org/10.5281/zenodo.18629367)

# dollarization-panel-data

# Global Deposit Dollarization Dataset (1980–2019)

## Overview

A panel dataset of **deposit dollarization ratios** (Foreign Currency Deposits / Total Deposits) covering **128 countries** from **1980 to 2019**, with **2,646 observations**. Data were collected from central bank publications, IMF Staff Reports, and CEIC.

This dataset was constructed as part of the master's thesis:

> **Jang, H. (2021). "Dollarization: Trends and its Determinants." Master's Thesis, Graduate School of Commerce, Waseda University. Advisor: Prof. Koichi Takase.**

## Citation

If you use this dataset, please cite:

```
Jang, Hyungju (2021). Dollarization: Trends and its Determinants.
Master's Thesis, Waseda University. Dataset available at: [DOI]
```

## Files

| File | Description |
|------|-------------|
| `dollarization_panel.csv` | Main panel dataset in tidy format |
| `dollarization_sources.csv` | Central bank source URLs for each country |
| `Data_dolrat_raw.xlsx` | Original raw data file |

## Variable Definitions

### dollarization_panel.csv

| Variable | Description |
|----------|-------------|
| `country` | Country name |
| `iso3` | ISO 3166-1 alpha-3 country code |
| `year` | Year (1980–2019) |
| `fcd_td_ratio` | Deposit dollarization ratio: Foreign Currency Deposits ÷ Total Deposits |

### dollarization_sources.csv

| Variable | Description |
|----------|-------------|
| `country` | Country name |
| `iso3` | ISO 3166-1 alpha-3 country code |
| `source_url` | URL of the central bank or data source |

## Methodology

### Definition

The dollarization ratio is defined as:

$$\text{Dollarization Ratio} = \frac{\text{Foreign Currency Deposits (FCD)}}{\text{Total Deposits (TD)}}$$

Following Mwase and Kumah (2015), Total Deposits is used as the denominator instead of Broad Money (the older convention from Baliño et al., 1999), so that the measure captures residents' preference for holding deposits in foreign currency more precisely.

Countries where the ratio exceeds **30%** are classified as **Highly Dollarized Economies (HDE)**; those between **10–30%** as **Moderately Dollarized Economies (MDE)**.

### Data Construction

- Primary sources: central bank statistical bulletins, annual reports, and databases
- Secondary sources: IMF Staff Reports, CEIC (for China)
- Historical data (pre-2000) for some countries: Baliño et al. (1999)
- Each country's data was sourced as uniformly as possible from a single source to avoid inconsistencies across reporting standards

### Coverage

- **128 countries** with at least one observation
- Temporal coverage varies by country (see Appendix in thesis)
- Most countries have data from **2000 onward**; some extend back to **1980**
- Coverage increases over time: 4 countries in 1980 → 125 countries in 2014

## Important Notes

### Fully Dollarized Economies (not in dataset)

The following countries adopted a foreign currency as legal tender and are **excluded** from the deposit dollarization ratio, as the measure is not applicable:

| Country | Currency | Year Adopted |
|---------|----------|-------------|
| Panama | USD | 1904 |
| Ecuador | USD | 2000 |
| El Salvador | USD | 2001 |
| Zimbabwe | Multiple | 2009 |

Additionally, CFA franc zone countries (WAEMU/CEMAC) and Eurozone members are treated as formally dollarized. Some Eurozone accession countries appear in the dataset with a sharp drop in ratio upon euro adoption (e.g., Estonia 2011, Latvia 2014, Lithuania 2015).

### Euro Effect

Countries that adopted the euro show a **structural break** in their dollarization ratio at the time of adoption, as euro-denominated deposits are reclassified from foreign to domestic. Regional averages for Europe and Central Asia should be interpreted with this in mind.

### Known Limitations

- Some countries report only FCD/Broad Money rather than FCD/Total Deposits
- Venezuela's reported ratios prior to 2019 may not reflect actual dollarization levels due to suspected statistical irregularities
- Language barriers affected data collection for some countries (e.g., Mauritania)
- Cash-based foreign currency usage (payment dollarization) is not captured
- Several high-income countries (Australia, France, Italy, Ireland, Portugal, New Zealand) do not report resident FCD statistics

## Data Quality Flags

Users should exercise caution with:
- **Pre-1995 data**: limited to fewer than 40 countries
- **Iran**: fiscal year vs. calendar year discrepancies in some sources
- **Argentina**: administrative restrictions on FCD affected reported ratios in multiple periods
- **Venezuela**: data reliability concerns (see thesis Section 2.3.2)

## License

## License

This dataset is released under the MIT License.  
You are free to share and adapt the data, provided appropriate credit is given.

For full license text, see the [MIT License](https://opensource.org/licenses/MIT).

## Related Literature

- Baliño, T., Bennett, A., & Borensztein, E. (1999). "Monetary Policy in Dollarized Economies." IMF Occasional Paper 171.
- Levy-Yeyati, E. (2006). "Financial Dollarization: Evaluating its Consequences." *Economic Policy*, 21(45), 61–118.
- Mwase, N. & Kumah, Y. (2015). "Revisiting the Concept of Dollarization." IMF Working Paper WP/15/12.

## Contact

Hyungju Jang — https://github.com/hj8779
