# Daylight Weather

A lightweight weather app that opens directly in your browser. Search for a city to see its current weather and a five-day forecast.

## Features

- Tokyo weather shown on load
- City search powered by the Open-Meteo Geocoding API
- Current temperature, feels-like temperature, wind speed, and a five-day forecast
- Forecast analytics: mean high, high-temperature variability, linear temperature trend with R², and mean rain probability
- An experimental, location-specific KNN analog forecast trained on eight years of daily temperature history
- Walk-forward ML error and skill compared with a persistence baseline
- High/low temperature chart and forecast CSV export for further analysis
- Weather-responsive accent colors and light/dark themes based on your system preference
- A built-in typical Tokyo forecast when the weather service is unavailable
- No API key, server, build step, or dependencies

## Run

Open `index.html` in a modern web browser. The app fetches live data from Open-Meteo when an internet connection is available.

## Data

Weather forecasts are provided by [Open-Meteo](https://open-meteo.com/). City names are resolved using the [Open-Meteo Geocoding API](https://open-meteo.com/en/docs/geocoding-api). The KNN model trains in the browser on daily observations from the [Open-Meteo Historical Weather API](https://open-meteo.com/en/docs/historical-weather-api); no Python runtime or JavaScript dependencies are required.

Forecast statistics are calculated from the next five daily forecasts. The temperature trend uses ordinary least-squares regression; R² indicates how well a straight line fits those daily highs. The CSV export includes each day's date, weather code, high and low temperatures, and precipitation probability.

The ML analog estimate is a separate experimental baseline, not a replacement for the operational weather forecast. It matches recent seven-day high/low patterns and season against the same location's historical data. Walk-forward validation samples origins from the latest 180 days and compares 1–5 day mean absolute error with a persistence forecast. The CSV also includes ML high/low estimates when historical training data is available.
