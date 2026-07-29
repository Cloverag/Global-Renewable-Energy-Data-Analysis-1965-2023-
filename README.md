# Global Renewable Energy Data Analysis (1965–2023)

A 9-page Power BI report on global renewable energy adoption, broken down by country, by
generation technology, and over time — covering generation, installed capacity, and renewables
as a share of both electricity and total primary energy.

**▶ [View the live report](https://app.powerbi.com/view?r=eyJrIjoiOTM2OTk1NDMtZTNkNy00OTlhLTljOTQtMjYzNDI3ZmZkZDQ0IiwidCI6IjdjNjRmODJlLWZmODMtNGEzMi1iOThiLWZkZDZlMjFlOWEyYyJ9)** — no Power BI licence needed.

**▶ [Exploratory analysis notebook](https://colab.research.google.com/drive/1ZxK-UVSP3UDvCSw4VzRKBI-EBaoQjafv)** — pandas / Seaborn / Plotly EDA over the source series.

## Credits

A two-person project:

- **Data analysis** — data wrangling, null profiling, per-source aggregation and the
  exploratory analysis in the Colab notebook — Raghav Singh ([@Cloverag](https://github.com/Cloverag))
- **Power BI report** — the 9-page report build and publish — Anurag Nayak

## Report pages

- Global Renewable Energy Overview
- Countries' year-wise growth in renewable electricity
- Global Installed Capacity by Energy Source
- Renewable Energy in Electricity Generation
- Global Solar Energy Consumption over time, and Global Solar Capacity by Year
- Global Wind Energy Consumption trend over time
- Global and regional trends in hydropower consumption
- Hydro and Wind proportion in electricity production and in total renewable generation
- Biofuel and Modern Renewable Production; Hydro Power and Geothermal Energy

## Data model

Eleven [Our World in Data](https://ourworldindata.org/renewable-energy) series, joined on
`Entity` (country) and `Year`, with an `Entity → Country` hierarchy for drilldown:

| Table | Contents |
|---|---|
| `01 renewable-share-energy` | Renewables as % of equivalent primary energy |
| `02 modern-renewable-energy-consumption` | Consumption by modern renewable source |
| `03 modern-renewable-prod` | Production by modern renewable source |
| `04 share-electricity-renewables` | Renewables as % of electricity |
| `05 hydropower-consumption` | Hydro generation (TWh) |
| `08 wind-generation` | Wind generation (TWh) |
| `10 wind-share-energy` | Wind as % of equivalent primary energy |
| `12 solar-energy-consumption` | Solar generation (TWh) |
| `13 installed-solar-PV-capacity` | Installed solar PV capacity |
| `16 biofuel-production` | Biofuels production (TWh) |
| `17 installed-geothermal-capacity` | Installed geothermal capacity |

Measures include `Renewable energy generation`, `Total Renewable Energy Consumption`,
`World Energy Share`, `Renewables (% electricity)`, `Renewables (% equivalent primary energy)`,
and per-technology generation and capacity for solar, wind, hydro, geothermal and bioenergy.

The series begin in 1965 (BP Statistical Review baseline, as republished by Our World in Data).

## Files

| File | What it is |
|---|---|
| `renewable-energy-analysis.pbix` | The Power BI report. Open in Power BI Desktop; data is embedded in the model, so it opens standalone. |
| `powerbi.html` / `powerbi.css` | Static page embedding the published report |
| `stream.html` / `stream.css` | Landing page linking the report, the consumption dashboard and the EDA notebook |

## Also in this repo (unrelated practice work)

Not part of this analysis — kept here because the repo doubled as a coursework scratch space:

- **`streamlit_app.py`** — Streamlit dashboard over the
  [PJM Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)
  dataset (US regional grid *load* in MW). Daily/monthly/annual trends with
  year/month/weekday filters. Expects `data/AEP_hourly.csv`.
- **`data.zip`** — the PJM hourly CSVs for the app above, plus `data.csv`, a vehicle
  specifications dataset (make/model/engine/MSRP) from a different exercise.

```bash
pip install pandas streamlit
unzip data.zip -d data
streamlit run streamlit_app.py
```

## Stack

Power BI · Power Query · DAX · Python · Pandas · Streamlit
