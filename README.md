# API Documentation

## Overview
This API provides access to tariff-related data, including schedules, rates, and provider details. The API follows OpenAPI Specification 3.1.0 and supports Machine-to-Machine authentication using OpenID Connect (OIDC) with TLS 1.3 security.

## Base URL
```
https://api.example.com/v1
```

## Authentication
The API requires authentication via OpenID Connect (OIDC). Requests must include a JWT token obtained from the authentication endpoint.

- Security: TLS 1.3
- Authentication: JWT Token-Based
- OpenID Connect URL: `https://auth.example.com/.well-known/openid-configuration`

## Endpoints

### 1. Get All Data
#### Request
```
GET /data
```
#### Response
- **200 OK**: Returns an array of data entries.

```json
[
  {
    "object": "tariff",
    "object_version": "1.0",
    "provider_id": "prv_63a6087272921ef075a8fd3e",
    "supplier_label": "ACME Retail Energy Ltd",
    "tariff_reference": "gb-acme"
  }
]
```

---

### 2. Search Data by Region
#### Request
```
GET /data/search?region=UKPN
```
#### Response
- **200 OK**: Returns a filtered list of data entries.

```json
[
  {
    "object": "tariff",
    "region": "UKPN",
    "tariff_label": "Online Fixed"
  }
]
```

---

### 3. Authenticate Machine-to-Machine
#### Request
```
POST /authenticate
```
#### Response
- **200 OK**: Successfully authenticated.
- **401 Unauthorized**: Authentication failed.

---

## Schema
The main object in the API is `DataEntry`, which contains the following properties:

| Field | Type | Description |
|-------|------|-------------|
| `object` | string | The type of object (e.g., tariff). |
| `provider_id` | string | Internal ID of the provider. |
| `supplier_label` | string | Name of the energy provider. |
| `tariff_reference` | string | Reference ID for the tariff. |
| `region` | string | The region where the tariff applies. |
| `tariff_schedule` | array | List of tariff schedules. |

The `tariff_schedule` object includes:

| Field | Type | Description |
|-------|------|-------------|
| `time_of_use` | string | Type of tariff (STATIC or DYNAMIC). |
| `standing_charge` | number | Charge per day in GBP. |
| `months` | array | Months when the tariff is valid. |
| `days_and_hours` | array | Days and hours when the tariff applies. |

The `days_and_hours` object includes:

| Field | Type | Description |
|-------|------|-------------|
| `days` | array | Days when the schedule is valid. |
| `hours` | array | Time slots when the tariff applies. |

The `hours` object includes:

| Field | Type | Description |
|-------|------|-------------|
| `valid_from` | string | Start time in HH:MM:SS format. |
| `valid_to` | string | End time in HH:MM:SS format. |
| `rate` | array | Tiered rate information. |

The `rate` object includes:

| Field | Type | Description |
|-------|------|-------------|
| `to_kwh` | number or null | Upper limit of kWh for the rate. |
| `value` | number or null | Cost per kWh in GBP. |

## Example Tariff Schedule JSON
```json
{
  "tariff_schedule": [
    {
      "time_of_use": "DYNAMIC",
      "standing_charge": 0.321,
      "months": ["All"],
      "days_and_hours": [
        {
          "days": ["All"],
          "hours": [
            {
              "valid_from": "00:00:00",
              "valid_to": "00:00:00",
              "rate": [
                {
                  "to_kwh": 30.5,
                  "value": 0.12
                }
              ]
            }
          ]
        }
      ]
    }
  ]
}
```

## License
This API schema is provided under an open-source license. Feel free to contribute and improve the documentation.
