# CODECRAFT_DS_01

# World Bank Population Data Visualization

This repository contains Python scripts designed to analyze and visualize global population trends using the World Bank's Total Population dataset (Indicator: SP.POP.TOTL). 

The visualizations address key data analysis practices, such as handling skewed distributions with logarithmic scales, removing duplicate regional aggregates to prevent double counting, and presenting readable, decluttered time series charts.

---

## Dataset Schema

The scripts assume the input dataset contains the following attributes:

| Column Name | Description |
| :--- | :--- |
| `Country_Name` | The name of the country or territory |
| `Country_Code` | The 3-letter ISO code (e.g., USA, IND, WLD) |
| `Indicator_Name` | Name of the indicator (Population, total) |
| `Indicator_Code` | World Bank indicator code (SP.POP.TOTL) |
| `Year` | The year of observation (e.g., 1960–2024) |
| `Population` | Total population count |

---

## Features & Visualizations

The project generates three distinct types of visualizations:

### 1. Global Population Distribution & Top Entities
* **Distribution (Histogram):** Uses a logarithmic scale to display the continuous distribution of country populations. This normalization technique addresses the high skewness between smaller nations and populous countries.
* **Top 10 Most Populous Countries (Bar Chart):** Focuses on the single year of 2022 to display the absolute sizes of the most populous countries using formatted tick marks.

### 2. Global Population Growth Over Time (1960–2024)
* Plots the true global population growth curve.
* **Correction applied:** It filters out duplicate regional aggregates (such as "High income" or "Sub-Saharan Africa") to isolate the actual 'World' record, correcting the y-axis scaling that otherwise inflates the total.
* Declutters the x-axis by showing timeline ticks at 10-year intervals and removes scientific notation in favor of standard billion/million labels.

### 3. Population Increase by Country (1960–2024)
* Plots individual growth curves representing the absolute population *increase* since the 1960 baseline.
* To keep the line plot legible, the script calculates absolute increases over the full timeframe and isolates the top 10 countries with the largest overall population growth.

---

## Requirements

Ensure you have the following Python libraries installed:

```bash
pip install pandas matplotlib seaborn requests
