# Citi Bike NYC: Casual-to-Member Conversion Analysis

## Overview
This project analyzes Citi Bike NYC trip data to identify where and how casual riders differ from members, using geospatial and behavioral patterns to answer a business question: which stations and areas are the strongest candidates for a targeted membership conversion campaign?

## Business Question
Where should Citi Bike focus membership marketing to convert casual riders into subscribers, and what ride patterns distinguish high-conversion-potential areas from low-potential ones?

## Data
Citi Bike NYC trip data for June 2026, downloaded from [citibikenyc.com/system-data](https://citibikenyc.com/system-data) (file: `202606-citibike-tripdata.zip`).

Not included in this repo due to file size. To reproduce:
1. Download `202606-citibike-tripdata.zip` from the link above
2. Extract it
3. Place the resulting CSVs in `data/raw/202606-citibike-tripdata/`
4. Run the notebooks in order starting with `01_clean.ipynb`

The dataset includes ride-level records with start/end station, coordinates, timestamps, bike type (classic/electric), and rider type (member/casual).

## Methodology
1. **Data cleaning** — combine monthly CSVs, handle missing station and coordinate data, parse timestamps, compute trip duration and distance
2. **Station-level aggregation** — summarize trips by station, including casual-rider share, trip duration/distance by rider type, and hour-of-day activity
3. **Spatial analysis** — hot-spot detection (Getis-Ord Gi*) and spatial autocorrelation (Moran's I) to identify statistically significant clusters of casual-ride concentration
4. **Station segmentation** — clustering stations into behavioral profiles based on ride patterns
5. **Business recommendation** — translating station clusters into targeted conversion opportunities

## Repo Structure
```
citibike-conversion-analysis/
├── data/
│   ├── raw/              # not tracked in git — see Data section above
│   └── processed/        # cleaned trips, station-level aggregates
├── notebooks/
│   ├── 01_clean.ipynb
│   ├── 02_station_agg.ipynb
│   ├── 03_spatial_analysis.ipynb
│   ├── 04_clustering.ipynb
│   └── 05_maps_and_viz.ipynb
├── outputs/
│   ├── figures/
│   └── maps/
├── README.md
└── requirements.txt
```

## Key Findings
_TBD — in progress_

## Tools
Python, pandas, PySAL/esda, scikit-learn, folium
