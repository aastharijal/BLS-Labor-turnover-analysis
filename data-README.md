# Data

This analysis uses monthly JOLTS rates (hires, quits, layoffs, job openings) for the following 10 industries, January 2009 – December 2024:

1. Construction
2. Durable Goods Manufacturing
3. Non-Durable Goods Manufacturing
4. Retail Trade
5. Transportation, Warehousing, and Utilities
6. Information
7. Financial Activities
8. Professional and Business Services
9. Healthcare and Social Assistance
10. State and Local Government

Source: [BLS JOLTS](https://www.bls.gov/jlt/) — each series must be downloaded individually per industry and rate type, then merged.

Place the combined file here as `main_data.csv` with columns: `sector, Year, month, hires, quits, layoffs, openings`.

`main_data.csv` is not included in this repo — add your own copy locally (or re-download from BLS) before knitting `analysis.Rmd`.
