# Daylight Weather

A lightweight weather app that opens directly in your browser. Search for a city to see its current weather and a five-day forecast.

## Features

- Tokyo weather shown on load
- City search powered by the Open-Meteo Geocoding API
- Current temperature, feels-like temperature, wind speed, and a five-day forecast
- Forecast analytics: mean high, high-temperature variability, linear temperature trend with R², and mean rain probability
- High/low temperature chart and forecast CSV export for further analysis
- Weather-responsive accent colors and light/dark themes based on your system preference
- A built-in typical Tokyo forecast when the weather service is unavailable
- No API key, server, build step, or dependencies

## Run

Open `index.html` in a modern web browser. The app fetches live data from Open-Meteo when an internet connection is available.

## Data

Weather forecasts are provided by [Open-Meteo](https://open-meteo.com/). City names are resolved using the [Open-Meteo Geocoding API](https://open-meteo.com/en/docs/geocoding-api).

Forecast statistics are calculated from the next five daily forecasts. The temperature trend uses ordinary least-squares regression; R² indicates how well a straight line fits those daily highs. The CSV export includes each day's date, weather code, high and low temperatures, and precipitation probability.
