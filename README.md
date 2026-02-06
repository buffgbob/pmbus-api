# PMBus Power Supply API

API specification for interfacing with PMBus-compliant power supplies.

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

## Commands

| Command | Method | Description |
|---------|--------|-------------|
| `psu_info` | GET | Device identification |
| `psu_control_clear_faults` | POST | Clear fault flags |
| `psu_control_fan` | GET/PUT | Fan enable and speed |
| `psu_monitoring` | GET | All sensor readings |
| `psu_status` | GET | All fault/warning flags |
| `psu_config_limits` | GET/PUT | Warning/fault thresholds |

## Example Usage

```
http://{host}:{port}/api?command=psu_info
http://{host}:{port}/api?command=psu_monitoring
http://{host}:{port}/api?command=psu_register_vin
```
