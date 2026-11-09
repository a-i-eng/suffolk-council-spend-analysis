# Suffolk County Council Spend Analysis (Mar-Aug 2026)

An Excel data analytics project using Suffolk County Council's published spending over £250. It covers data cleaning with Power Query, formulas, pivot tables, a slicer-driven dashboard and a simple forecast.



## Key findings
- Net spend over six months: **£666.8M** across **186,859** invoice lines.
- Adult Social Care is the largest directorate (33.1% of spend), followed by CYP (29.9%).
- Credits and refunds total £45.9M, 6.4% of payments. Adult Social Care's credits are 15.1% of its payments.
- 525 lines of £100,000 or more (0.28% of lines) make up 37.7% of net spend.
- The top 10 suppliers are only 22.2% of supplier spend, so spend is fragmented.

## A data-quality problem I caught
My first totals showed £1,165M. A sanity check on the top supplier (EDF Energy, £261.6M) looked far too high. The cause: the `Inv Amount` column holds the whole invoice total on every line of that invoice, so summing it counted each invoice many times. I switched to the line-level `Sub Amount`, and net spend fell to £666.8M (EDF's real line spend: £2.07M). Full details are in the Notes sheet.

## What is in the workbook
| Sheet | Contents |
|---|---|
| Cover | Overview and links |
| Raw_Data | Untouched sample of the source file |
| Clean_Data | Power Query output (table `tblSpend`) |
| Lookups / Analysis | SUMIFS, COUNTIFS, INDEX/MATCH, RANK, LARGE |
| Pivots | Pivot tables with slicers |
| Dashboard | KPI cards and four charts |
| Forecast | Moving average, trend line, FORECAST.LINEAR, R² |
| Notes | Cleaning log, findings, assumptions, limitations |

## Skills shown
Power Query cleaning, advanced formulas, pivot tables and slicers, dashboard design, basic statistics and forecasting, data-quality checking.

## Data source
Suffolk County Council, [Expenditure exceeding £250](https://www.suffolk.gov.uk/council-and-democracy/open-data-suffolk/council-data-and-transparency/council-expenditure-and-contracts/expenditure-exceeding-250), monthly CSV files for March to August 2026. Published under the Open Government Licence v3.0. The raw CSVs are not included in this repository.

## Limitations
- Six months is too little data for a reliable forecast (R² = 0.22), so the forecast is indicative only.
- About [£XX.XM] is paid under "REDACTED PERSONAL DATA" and is excluded from supplier rankings.
- The council page publishes no column definitions, so the invoice-total behaviour is my own finding from the data.
- The Power Query connection points to a folder on my computer (`D:\Suffolk_Data`). To refresh it, download the six CSVs and repoint the query.

## Author
[Alka], [http://www.linkedin.com/in/alka-i-833083278]
