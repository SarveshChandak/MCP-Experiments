# MCP Weather Server

This project is a weather server built using the MCP (Model Context Protocol) framework. It provides tools to fetch weather alerts and forecasts for specific locations in the United States using the National Weather Service (NWS) API.

## Features

- **Get Weather Alerts**: Retrieve active weather alerts for a specific US state.
- **Get Weather Forecast**: Fetch detailed weather forecasts for a specific latitude and longitude.

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   ```
2. Navigate to the project directory:
   ```bash
   cd MCP Server/weather
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

### Run the Server

Start the MCP weather server:
```bash
python weather.py
```

If the server and client are on the same machine, use the `stdio` transport:
```bash
uv run weather.py
```

### Tools

#### 1. Get Weather Alerts
Fetch active weather alerts for a US state using the `get_alerts` tool.

**Arguments**:
- `state`: Two-letter US state code (e.g., `CA` for California, `NY` for New York).

**Example**:
```json
{
  "tool": "get_alerts",
  "args": {
    "state": "CA"
  }
}
```

#### 2. Get Weather Forecast
Fetch a detailed weather forecast for a specific location using the `get_forecast` tool.

**Arguments**:
- `latitude`: Latitude of the location (e.g., `34.0522` for Los Angeles).
- `longitude`: Longitude of the location (e.g., `-118.2437` for Los Angeles).

**Example**:
```json
{
  "tool": "get_forecast",
  "args": {
    "latitude": 34.0522,
    "longitude": -118.2437
  }
}
```

### Automatic Invocation by LLM

These tools are designed to be automatically invoked by a Language Model (LLM) through the client whenever required. The client can seamlessly interact with the server to fetch weather alerts or forecasts based on user queries.

## Contributing

Feel free to submit issues or pull requests to improve the project.

## License

This project is licensed under the MIT License.
