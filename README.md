# ⚡ Australian Energy Market (NEM) Data Analytics Portfolio

Project 1 is in the notebook NEM Volatility Analysis,ipynb, Project 2 is in the notebook NEM Duck Curve Analysis.ipynb.

## 📖 Background: The Australian Energy Transition

The Australian National Electricity Market (NEM) is currently undergoing one of the fastest and most complex renewable energy transitions in the world. As traditional coal-fired baseload generation is phased out and residential rooftop solar adoption reaches record highs, grid operators (like AEMO) and energy retailers are facing unprecedented engineering and economic challenges.

This repository contains two end-to-end data analytics projects that programmatically extract, clean, and model real-world, 5-minute interval data to investigate the two largest challenges in the NEM today: Extreme Price Volatility and The Duck Curve.

## 📂 Projects Overview

### Project 1: NEM Wholesale Price Volatility & Extreme Weather

Energy retailers are exposed to massive financial risks when wholesale electricity prices spike from an average of $50/MWh up to the market cap of $16,600/MWh. This project investigates the driving forces behind these price blowouts during high-summer periods by mapping extreme weather events to grid stress.

Key Highlights:

API Integration: Dynamically merges AEMO 5-minute DISPATCHPRICE data with real historical daily maximum temperatures via the Open-Meteo Archive API.

Heatwave Thresholds: Discovered a non-linear tipping point where temperatures exceeding 35°C trigger extreme upward price volatility, particularly in South Australia and Victoria.

Negative Pricing: Identified the massive frequency of negative pricing intervals during peak solar hours (10:00 AM - 2:00 PM) driven by rooftop PV over-generation.

### Project 2: The "Duck Curve" & Minimum System Load

The "Duck Curve" phenomenon occurs when massive amounts of residential rooftop solar push midday grid demand to record lows (the "belly"), requiring steep, multi-gigawatt generation ramps in the evening when the sun sets (the "neck").

Key Highlights:

Time-Series Profiling: Extracted multi-year historical data (2018–Present) to visually demonstrate the severe, year-over-year "hollowing out" of midday demand.

Ramp Rate Deltas: Calculated the massive evening generation ramps required between 16:00 and 19:00, highlighting the urgent need for fast-discharge batteries and gas peaker plants.

Predictive Modeling: Deployed a Polynomial Regression machine learning model using scikit-learn to forecast future minimum system loads, demonstrating how market economics and battery charging will eventually "flatten" the curve before demand reaches zero.

## 🛠️ Data Sources & Tech Stack

AEMO Data Extraction: Used the nemosis Python library to bypass manual CSV downloads and dynamically query the Australian Energy Market Operator databases (DISPATCHPRICE and DISPATCHREGIONSUM).

Data Engineering: Pandas and NumPy for complex time-series aggregation, timezone handling, delta calculations, and data merging.

Machine Learning: Scikit-Learn for non-linear predictive demand forecasting.

Visualization: Seaborn and Matplotlib for creating complex multi-year overlapping line charts, heatmaps, and correlation scatter plots.
