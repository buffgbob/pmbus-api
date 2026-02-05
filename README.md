# PMBus Power Supply API

OpenAPI specification for interfacing with PMBus-compliant power supplies.

## Files

- `pmbus_api.yaml` - OpenAPI 3.1 specification
- `docs.html` - Interactive API documentation (Swagger UI)
- `p2*.txt` - PMBus register documentation for specific PSU models

## Viewing the Documentation

The API docs require a local web server (browsers block loading local YAML files directly).

### Option 1: Python (recommended)

```bash
python3 -m http.server 8000
```

Open http://localhost:8000/docs.html

### Option 2: Node.js

```bash
npx serve
```

Open the URL shown in the terminal (usually http://localhost:3000/docs.html)

### Option 3: PHP

```bash
php -S localhost:8000
```

Open http://localhost:8000/docs.html

## API Overview

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/info` | GET | Device identification |
| `/register/{name}` | GET/PUT | Read/write any register |
| `/control/power` | GET/PUT | Enable/disable PSU output |
| `/control/clear-faults` | POST | Clear fault flags |
| `/control/fan` | GET/PUT | Fan enable and speed |
| `/control/voltage` | GET/PUT | Output voltage setpoint |
| `/monitoring` | GET | All sensor readings |
| `/status` | GET | All fault/warning flags |
| `/status/summary` | GET | Quick health check |
| `/config/limits` | GET/PUT | Warning/fault thresholds |
