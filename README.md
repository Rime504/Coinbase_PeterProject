# Coinbase Peter Project

## Overview

This project is a sophisticated cryptocurrency analysis and visualization tool developed by me in collaboration with PETE an institutional quantitative developer in , this is a proprietary trading framework designed for high-frequency and quantitative trading strategies, and this project leverages its capabilities to provide deep insights into cryptocurrency markets.

The tool connects to the Coinbase Cloud REST API to fetch historical price data for major cryptocurrencies such as Bitcoin (BTC), Ethereum (ETH), Solana (SOL), and Ripple (XRP). It processes this data using a suite of technical indicators, detects whale activity through volume anomaly analysis, and generates interactive visualizations to aid in trading decisions.

Originally starting as a basic data fetching script, the project has been iteratively enhanced with advanced features like the whale detector, multi-timeframe analysis, and comprehensive indicator calculations, making it a unique blend of institutional-grade quantitative analysis and user-friendly visualization.

## What It Does

The project performs the following key functions:

1. **Data Acquisition**: Fetches historical OHLCV (Open, High, Low, Close, Volume) data from Coinbase for multiple cryptocurrencies across various time granularities (1-minute, 15-minute, 60-minute, and daily).

2. **Technical Indicator Calculation**: Computes a wide array of technical indicators including:
   - Simple Moving Averages (SMA3, SMA7)
   - Exponential Moving Averages (EMA12, EMA26)
   - Moving Average Convergence Divergence (MACD) with signal line and histogram
   - Relative Strength Index (RSI)
   - Average True Range (ATR) for volatility measurement
   - True Range and other volatility metrics

3. **Whale Activity Detection**: Identifies potential "whale" trades by analyzing volume spikes relative to a rolling average, flagging unusual trading activity that could indicate large institutional moves.

4. **Market Trend Analysis**: Determines bullish/bearish market conditions based on MACD histogram and tracks trend continuations.

5. **Interactive Visualization**: Creates multi-panel charts using Plotly, including:
   - Candlestick charts with overlaid indicators
   - Colored trend periods (green for bull, red for bear)
   - Subplots for ATR and RSI
   - Whale alert markers on price charts

6. **Performance Metrics**: Calculates 24-hour, 30-day, and 90-day performance statistics, including highs, lows, and volatility spans.

## Why It Was Built

In the volatile and fast-moving cryptocurrency markets, institutional traders need tools that can process large amounts of data quickly, identify patterns, and provide actionable insights. This project addresses several key needs:

- **Quantitative Analysis**: Provides objective, data-driven insights rather than relying on subjective analysis.
- **Risk Management**: ATR and volatility metrics help assess market risk and position sizing.
- **Trend Identification**: MACD and EMA indicators help identify market trends and potential entry/exit points.
- **Anomaly Detection**: Whale detection alerts traders to significant market-moving events.
- **Visualization**: Interactive charts allow for quick interpretation of complex data sets.

The project was developed to bridge the gap between raw market data and actionable trading intelligence, specifically tailored for crypto markets where traditional financial tools may not suffice.

## How It's Unique

What sets this project apart from other crypto analysis tools:


2. **Comprehensive Indicator Suite**: Combines multiple indicators in a single, cohesive analysis framework, allowing for cross-validation of signals.

3. **Whale Detection Algorithm**: A proprietary volume-based anomaly detection system that flags potential large trades, which is crucial in crypto markets where whales can significantly impact prices.

4. **Multi-Timeframe Analysis**: Simultaneously analyzes data across different time scales (1-min to daily), providing a holistic view of market dynamics.

5. **Real-Time Data Integration**: Fetches live data from Coinbase API, ensuring analysis is based on the most current market information.

6. **Interactive Visualizations**: Uses Plotly for web-based, interactive charts that can be embedded in dashboards or shared with team members.

7. **Iterative Development**: Started as a basic script and evolved with advanced features, demonstrating a scalable approach to quantitative tool development.

8. **Open-Source Accessibility**: While built with institutional tools, the project is shared openly, making advanced quantitative techniques accessible to retail traders and developers.

## Project Dissection

The project is structured as a Jupyter Notebook (`coinbase-nb.ipynb`) for easy execution and modification. Here's a breakdown of its components:

### 1. Setup and Imports
- Imports necessary libraries: pandas, requests, numpy, plotly
- Defines constants for currencies, granularities, and colors
- Establishes connection functions for API calls

### 2. Data Fetching Module
- `connect()`: Generic function for API requests with error handling
- `get_historic_data()`: Fetches historical candle data from Coinbase
- Server time synchronization for accurate data retrieval

### 3. Product Information
- Retrieves available trading pairs from Coinbase
- Filters for user-specified cryptocurrencies

### 4. Statistics and Performance
- Fetches 24-hour statistics for each currency
- Calculates performance metrics and formats for display

### 5. Historical Data Collection
- Aggregates data across multiple timeframes
- Processes and cleans raw API data into structured DataFrames

### 6. Indicator Calculations
- Implements technical analysis functions:
  - Moving averages (SMA, EMA)
  - MACD with signal and histogram
  - RSI for momentum
  - ATR for volatility
  - True Range calculations

### 7. Whale Detection
- `detect_whale_activity()`: Identifies volume spikes above a threshold
- Flags potential large trades for further analysis

### 8. Visualization Engine
- Creates candlestick charts with indicator overlays
- Adds trend coloring based on bull/bear conditions
- Generates multi-panel subplots for comprehensive analysis

### 9. Additional Analysis
- Computes performance statistics across timeframes
- Identifies trend continuations and market phases

## Dependencies

The project requires the following Python packages (listed in `requirements.txt`):
- pandas
- requests
- numpy
- plotly

## Usage

1. Install dependencies: `pip install -r requirements.txt`
2. Open the Jupyter notebook: `jupyter notebook coinbase-nb.ipynb`
3. Run cells sequentially to fetch data, calculate indicators, and generate visualizations
4. Customize parameters (currencies, timeframes, thresholds) as needed

## Future Enhancements

Potential areas for expansion:
- Integration with additional exchanges
- Machine learning models for price prediction
- Real-time alerting system
- Portfolio optimization features
- Backtesting framework

## Contributing

This project is open-source and welcomes contributions. Please submit pull requests or issues via the GitHub repository.

## Contact

For questions or collaborations, please reach out to the project maintainer.
@rimerizha@gmail.com
