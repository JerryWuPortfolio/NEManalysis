# ⚡ NEM Wholesale Price Volatility & Extreme Weather Analysis

## 📖 Project Overview

Energy retailers are exposed to massive financial risks when wholesale electricity prices spike from an average of $50/MWh up to the market cap of $16,600/MWh during extreme grid stress.

This project investigates the driving forces behind these price blowouts in the Australian National Electricity Market (NEM) during the high-summer period (Jan-Feb 2023). By combining live, 5-minute interval data from the Australian Energy Market Operator (AEMO) with historical weather data, this analysis uncovers critical correlations between extreme heat, solar generation, and wholesale price volatility.

## 📊 Key Insights & Findings

Based on the data extraction and visualization, here are the detailed insights answering our core business questions:

### 1. The "Evening Peak" is the Most Hazardous Time for Price Spikes

Question: Which specific months and times of day experience the highest frequency of extreme wholesale price spikes (>$300/MWh)?

Insight: A severe concentration of price spikes occurs between 5:00 PM and 7:30 PM (17:00 - 19:30) across the mainland states, particularly in Queensland and New South Wales. This specific window represents the critical "solar ramp-down" period. As residential workers return home and switch on air conditioning units, demand surges exactly as rooftop and grid-scale solar generation drops to zero. This forces the market to rely on expensive fast-start gas peaker plants and hydro, driving the wholesale price exponentially higher.

### 2. The 35°C Tipping Point in South Australia and Victoria

Question: How strongly do extreme temperature days (heatwaves >35°C) correlate with Regional Reference Price (RRP) blowouts in South Australia versus Victoria?

Insight: There is an aggressive, non-linear correlation between extreme heat and price blowouts. On days where the maximum temperature remains below 30°C, the maximum daily RRP stays highly stable. However, once the 35°C threshold is crossed, prices exhibit extreme upward volatility, frequently blowing out past $1,000/MWh. South Australia shows a slightly higher sensitivity to these heatwaves compared to Victoria, likely due to its heavy reliance on wind generation, which often drops during stagnant, high-pressure heatwave conditions.

### 3. South Australia Dominates Negative Pricing During Solar Hours

Question: What is the frequency of negative pricing intervals during peak solar hours (10:00 AM - 2:00 PM), and which state is most affected?

Insight: South Australia is by far the most heavily impacted by negative pricing, followed by Victoria. Between 10:00 AM and 2:00 PM, South Australia's massive penetration of rooftop solar frequently generates more electricity than the state's entire operational demand. Because traditional base-load generators cannot easily switch off for just a few hours, they must pay the market to take their excess power, resulting in consistent negative wholesale prices mid-day.

### 4. Weekdays Exhibit Significantly Higher Pricing Instability

Question: How does the variance in operational demand between weekends (lower industrial use) and weekdays affect pricing stability?

Insight: By measuring the standard deviation of wholesale prices, the data proves that weekdays are significantly more volatile than weekends. On weekends, the absence of heavy industrial and commercial load flattens the overall demand curve, leading to highly stable, predictable pricing. Conversely, weekdays suffer from the synchronized alignment of commercial operations and residential peaks, leading to rapid demand swings and a much higher financial risk for energy retailers.

### 5. Massive State Disparities During Top 10% Peak Demand

Question: During top 10% peak demand intervals, what is the average price differential between states?

Insight: Filtering for the 90th percentile of operational demand reveals stark contrasts in how different states handle extreme grid stress. Queensland and South Australia exhibit the highest average prices during their respective peak demand intervals, reflecting their reliance on expensive peaking generation when the grid is stretched. In contrast, Tasmania maintains the lowest average price during its top 10% demand periods, insulated by its deep, highly dispatchable hydro-electric storage which can easily ramp up to meet peak needs without triggering massive price blowouts.

## 🛠️ Data Sources & Technologies

AEMO Data: 5-minute DISPATCHPRICE and DISPATCHREGIONSUM tables dynamically extracted using the nemosis Python library.

Weather Data: Historical daily maximum temperatures fetched via the Open-Meteo Archive API.

Tools Used: Python, Pandas, Matplotlib, Seaborn, Requests.
