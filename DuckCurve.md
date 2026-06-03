# NEM "Duck Curve" & Minimum System Load Analysis

## 📖 Project Overview

The "Duck Curve" is arguably the greatest engineering and economic challenge currently facing the Australian National Electricity Market (NEM). As residential rooftop solar installations surge, midday operational demand is dropping to unprecedented lows (the "belly" of the duck), followed by extreme spikes in demand as the sun sets and evening routines begin (the "neck" of the duck).

This project programmatically extracts multi-year, 5-minute interval data directly from the Australian Energy Market Operator (AEMO) to visualize this phenomenon, measure the severity of evening ramp requirements, and predict future grid stability using non-linear machine learning models.

## 📊 Key Insights & Findings

Based on the time-series profiling and predictive modeling, here are the detailed insights answering our core business questions:

### 1. The Rapid "Hollowing Out" of Midday Demand

Question: How has the midday "belly" of the operational demand curve deepened year-over-year from 2018 to the present day in South Australia and Queensland?

Insight: The year-over-year line charts reveal a drastic hollowing out of the grid between 10:00 AM and 2:00 PM. In states like South Australia and Queensland, which have world-leading rooftop PV penetration, the midday demand drops significantly lower every single year. This proves that residential solar is not just supplementing the grid; it is actively displacing traditional baseload generation during daylight hours, creating immense pressure on coal plants that cannot easily switch off and on.

### 2. The Multi-Gigawatt Evening Ramp

Question: What is the maximum "Ramp Rate" (change in MW demand per hour) required between 4:00 PM and 7:00 PM during the transition from solar to evening peak?

Insight: By calculating the delta between 16:00 and 19:00, the data exposes the sheer stress placed on the grid as the sun sets. Within just a 3-hour window, the market must find thousands of Megawatts of flexible, fast-start generation to cover the loss of solar energy simultaneously colliding with the evening residential peak. This highlights the urgent commercial need for deep storage (pumped hydro) and fast-discharge battery systems to prevent blackouts.

### 3. The Bridging Role of Gas and Batteries

Question: On days with the lowest minimum system load, what is the generation mix keeping the grid stable?

Insight: Analyzing the generation mix on minimum-load days shows a grid completely dominated by wind and rooftop solar during the day. However, to keep the system stable during the evening ramp, the grid heavily relies on fast-responding gas peaker plants and grid-scale battery dispatch. Batteries soak up the excess (often negatively priced) solar during the day and discharge it precisely when the "neck" of the duck requires it most.

### 4. Winter Ramps are Steeper and Earlier

Question: How do seasonal daylight hours shift the timing and severity of the evening ramp requirement?

Insight: Comparing Winter to Spring demand profiles reveals a critical seasonal shift. In Winter, the sun sets much earlier, meaning solar generation drops off right as the 5:00 PM commuter peak begins. This creates a highly condensed, steeper ramp requirement compared to Spring/Summer, where prolonged daylight delays the solar drop-off, spreading the evening demand surge over a wider, more manageable timeframe.

### 5. Predicting the Future: The "Flattening" of the Duck Curve

Question: At current rooftop PV installation rates, in what year will Victoria's midday operational demand regularly drop below zero?

Insight: A basic linear projection suggests Victoria's demand will crash below zero in the coming years. However, by applying a Polynomial Regression model, the data reveals a different story: the curve is beginning to "flatten" out as we approach 2030. This mathematical flattening reflects real-world market economics—as prices drop to zero or negative during the day, it triggers massive automated charging from grid-scale batteries and daytime EV charging. This creates an artificial demand "floor," proving that while the Duck Curve is severe, emerging technologies will eventually stabilize minimum system load.

## 🛠️ Data Sources & Technologies

AEMO Data: Extracted 5-minute DISPATCHREGIONSUM interval data via the nemosis Python API.

Tools Used: * Pandas / NumPy for time-series aggregation and delta calculations.

Seaborn / Matplotlib for complex multi-year overlapping line visualizations.

Scikit-Learn (Polynomial Regression) for non-linear predictive demand forecasting.
