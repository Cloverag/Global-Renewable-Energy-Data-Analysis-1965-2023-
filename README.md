# Global Renewable Energy Data Analysis (1965–2023)

A Power BI analysis of global renewable energy adoption, broken down by country and by
generation technology (solar, wind, hydroelectric).

## Main artifact

**`renewable-energy-analysis.pbix`** — the Power BI report. Open it in Power BI Desktop.

The report models renewable generation and share-of-total-energy by country/entity over time,
with per-technology breakdowns for solar, wind and hydroelectric, and regional roll-ups. The
source dataset is embedded in the report's data model, so the `.pbix` is self-contained — you
do not need to load any CSV to open and explore it.

Views included:

- Renewable share of total energy consumption, by country and over time
- Per-technology comparison (solar vs wind vs hydroelectric) and each one's growth trajectory
- Regional roll-ups for cross-region comparison
- Country-level drilldown

## Web mockups

`powerbi.html` / `powerbi.css` and `stream.html` / `stream.css` are static presentation pages
built around the report.

## Also in this repo (unrelated practice work)

These files are from separate exercises and are **not** part of the renewable energy analysis.
They are kept here only because this repo was used as a general coursework scratch space:

- **`streamlit_app.py`** — a Streamlit dashboard over the
  [PJM Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)
  dataset (US regional grid *load* in megawatts). Charts daily, monthly and annual
  consumption trends with year/month/weekday filters. Expects `data/AEP_hourly.csv`.
- **`data.zip`** — contains the PJM hourly CSVs used by the Streamlit app above, plus
  `data.csv`, which is a vehicle-specifications dataset (make/model/engine/MSRP) from a
  different exercise.

## Running the Streamlit app

```bash
pip install pandas streamlit
unzip data.zip -d data
streamlit run streamlit_app.py
```

## Stack

Power BI · Python · Pandas · Streamlit
