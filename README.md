# Last-Mile Delivery Dashboard · LogiSight Analytics (FA-2)

Interactive Streamlit dashboard built from the FA-1 design blueprint (FILTER → COMPARE → INVESTIGATE → ACT).

**Data:** `amazon_delivery.csv` — 43,739 last-mile orders (Feb–Apr 2022), `Delivery_Time` in minutes.

## What's inside
- **Stage 4 – Cleaning:** trimmed labels, fixed `Metropolitian`, dropped 91 rows missing weather/traffic/time, invalid ratings (>5) + missing ratings imputed with the median, flipped coordinates fixed, placeholder coordinates kept off the map. Derived fields: late flag (mean + 1 SD), age group (<25, 25–40, 40+), haversine distance, order hour, pickup wait.
- **Stage 5 – Compulsory visuals:** Delay analyzer (bar), Vehicle comparison (bar), Agent performance scatter, Area heatmap, Category boxplot.
- **Optional visuals:** daily/hourly trends, delivery-time histogram, % late by traffic × weather.
- **3D views:** weather × traffic surface, rating × age × time point cloud, 3D hexagon map of drop locations (pydeck).
- **Stage 6 – Interface:** sidebar multiselect filters (weather, traffic, vehicle, area, category), late-rule control, reset button, live KPIs, auto-generated "Act" prompts, data pipeline summary, CSV download.

## Run locally
```bash
pip install -r requirements.txt
streamlit run app.py
```
