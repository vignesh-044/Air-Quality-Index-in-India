# Air Quality Index in India

## Summary

Air pollution poses a significant threat to public health and quality of life, particularly in densely populated and industrial regions of India.
This project analyzes real-world air quality data collected from multiple cities and monitoring stations across India, provided by the Central Pollution Control Board (CPCB).

Using daily and hourly pollutant levels—including PM2.5, PM10, NO₂, SO₂, CO, and O₃—this study evaluates AQI trends, identifies pollution hotspots, and uncovers temporal patterns
in air pollution (such as seasonal effects and time-of-day variations). The analysis also compares city-wise and station-wise AQI buckets (Good, Moderate, Poor, etc.), offering visual
and statistical insights into the worsening air quality in urban centers like Delhi, Mumbai, and Patna.

### Pollutant Glossary:
- **PM2.5** – Particulate Matter ≤ 2.5 micrometers
- **PM10** – Particulate Matter ≤ 10 micrometers
- **NO** – Nitric Oxide
- **NO₂** – Nitrogen Dioxide
- **NOx** – Nitrogen Oxides (NO + NO₂)
- **NH₃** – Ammonia
- **CO** – Carbon Monoxide
- **SO₂** – Sulfur Dioxide
- **O₃** – Ozone
- **Benzene, Toluene, Xylene** – Volatile Organic Compounds (VOCs)
- **AQI** – Air Quality Index

## Tools and Technologies Used
- **Python**: For data cleaning and preprocessing
- **Tableau**: For data visualization and deriving insights

## Datasets Used
- `city_day.csv`
- `city_hour.csv`
- `station_day.csv`
- `station_hour.csv`
- `stations.csv`

## Python: Data Cleaning & Processing Steps

### 1. City-Level Dataset Cleaning (`city_day.csv`)
- Dataset contained ~50% null values.
- Replaced missing values with **mean values grouped by city** instead of dropping rows.
- Converted `Date` to `datetime`, and extracted day/month/year.

### 2. Station-Level Dataset (`station_day.csv` + `stations.csv`)
- Merged using `station_id`, handled 85% nulls in `Xylene` column.
- Filled missing values using **mean per station_id**.
- Converted datetime and extracted date parts.

### 3. AQI Correlation Analysis
- Found AQI is most influenced by: **PM2.5, PM10, NO, NO2, CO, SO2**.

### 4. Hourly Dataset Cleaning
- Used only `City`, `Datetime`, and `AQI` columns.
- Dropped rows with null AQI values.
- Extracted **day, month, year, hour** from datetime.

### 5. Cleaned Datasets Created
- `cleaned_stations.csv`
- `df_City_day.csv`
- `df_cHour_AQI.csv`
- `df_station.csv`
- `aqi_corr.csv` (for AQI-pollutant relationship analysis)

## Tableau: Visualizations & Dashboards

### Visualizations Built
- Map View of AQI Cities
- Average AQI Across Cities
- AQI Across Years
- Average AQI Across Stations
- Hour-wise AQI Trend
- Monthly AQI Variation
- Final Dashboards and Storylines

### Regional Insights (City-Wise)
- **Northern Cities** like **Ahmedabad, Delhi, Patna, Gurugram, Lucknow** show **higher AQI**:
  - Poor air quality due to urban density, industrialization, traffic
- **Southern Cities** like **Coimbatore, Bengaluru, Kochi** show **cleaner air**
- **Hotspots**: Ahmedabad & Delhi — due to dense traffic, urbanization, industrial activities

### Pollutant Influence on AQI
- Strongest influence from: **CO, PM2.5, NO2, NO, NOx, SO2**
- These originate from: **vehicle emissions, fossil fuels, industrial sources**
- Strongest correlation: **PM2.5 and NO2**

### Time-Based AQI Patterns
- **Yearly**: AQI averaged ~350 before 2020, dropped to ~250 in 2020 (lockdown effect)
- **Seasonal**: High AQI from **Jan–Mar** and **Oct–Dec**
- **Hourly**: Peaks before and after **9 AM** (traffic + atmospheric effects)

### Ahmedabad Focus
- Average AQI > 300; Peak AQI ~640
- Causes: **High population**, **hot/dry climate**, **low pollution awareness**
- Urgent need for pollution control policies and health protection measures

## Conclusion

The AQI trends from 2015 to 2020 highlight serious air quality concerns across Indian cities, especially in the north. Cities like **Ahmedabad and Delhi** consistently
record hazardous pollution levels. While a temporary dip in 2020 (due to lockdowns) revealed that AQI can be controlled, sustainable improvements require long-term efforts
in **policy**, **infrastructure**, and **awareness**.

---
*This project was built using Python for data wrangling and Tableau for rich visual storytelling. Cleaned datasets are provided, and visualizations are summarized above.
Tableau dashboards or a PDF listing of visuals may be added to this repository.*
## Regional AQI Insights

- **Northern cities** such as **Ahmedabad, Delhi, Patna, Gurugram**, and **Lucknow** consistently report **higher AQI levels**, indicating:
  - Poor air quality
  - Higher concentration of pollutants

- **Southern cities** like **Coimbatore, Bengaluru, Kochi**, and **Ernakulam** show **significantly lower AQI values**, reflecting:
  - Relatively cleaner air
  - Better air quality conditions

- This **regional disparity** highlights key influencing factors:
  - Urban density
  - Vehicular emissions
  - Industrialization
  - Climatic conditions

- **Ahmedabad and Delhi** are major contributors to India’s high AQI levels due to:
  - Dense traffic
  - Rapid urbanization
  - Extensive industrial activities

- These cities are **critical pollution hotspots**, often recording:
  - The highest pollutant concentrations in the country

### Conclusion

The findings emphasize the need for:
- **Targeted pollution control strategies**
- **Focused action in high-risk urban zones** to improve national air quality standards
