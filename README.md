# C# Weather App

A simple C# Weather Forecast application that fetches and displays current weather and short-term forecasts. Designed to be minimal, cross-platform, and easy to extend.

## Features
- Retrieve current weather and a short forecast for a given location
- Lightweight, configurable HTTP client
- CLI usage with optional configuration file or environment variables
- Clear separation of API, service, and UI layers for easy extension

## Requirements
- .NET 6.0 or later SDK
- Internet access for weather API requests
- (Optional) API key from a weather provider (e.g., OpenWeatherMap)

## Getting started

1. Clone the repository
    ```
    git clone <repo-url>
    cd WeatherApp
    ```

2. Configure an API key (example environment variable)
    - Linux / macOS:
      ```
      export WEATHERAPP_API_KEY=your_api_key_here
      ```
    - Windows (PowerShell):
      ```
      $Env:WEATHERAPP_API_KEY="your_api_key_here"
      ```

    Alternatively, create a `appsettings.json` with the following:
    ```json
    {
      "WeatherApi": {
         "BaseUrl": "https://api.openweathermap.org/data/2.5",
         "ApiKey": "your_api_key_here"
      }
    }
    ```

3. Build and run
    ```
    dotnet build
    dotnet run --project src/WeatherApp -- CityName
    ```

## Usage
- CLI:
  ```
  dotnet run --project src/WeatherApp -- "London"
  ```
  Replace "London" with a city name or coordinates as supported by the configured API.

- Configuration options:
  - WEATHERAPP_API_KEY or WeatherApi:ApiKey in appsettings.json
  - WeatherApi:BaseUrl

## Project structure (example)
- src/WeatherApp        — CLI and presentation layer
- src/WeatherApp.Core   — business logic and models
- src/WeatherApp.Api    — API client and network logic
- tests/                — unit and integration tests

## Testing
Run tests with:
```
dotnet test
```

## Extending
- Swap or extend the API client to support multiple providers
- Add caching, retry policies, or background refresh
- Add a GUI (WPF, MAUI) or web frontend

## Contributing
- Fork the repo, create a branch, open a PR with a clear description and tests if applicable.
- Follow existing code style and include API key handling guidance in PRs that add new providers.

## License
Specify your license (e.g., MIT) in a LICENSE file.

## Contact
For issues or feature requests, open an issue in the repository.
