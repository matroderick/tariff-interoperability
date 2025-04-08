# API Documentation

## Overview
This API allows users to retrieve and search tariff data, as well as perform machine-to-machine authentication using OpenID Connect (OIDC).

## Dev Portal
API Specification can be found at [RECCo Public Dev Portal](https://38db35b56c92.edge.eu.portal.konghq.com/apis/api-for-sharing-tariff-data-1-0-0/specifications/84d45b00-df1b-40d4-a322-708590da9549).

## Endpoints

### 1. Get All Data
- **Endpoint:** `GET /data`
- **Description:** Retrieves a list of all available data entries.
- **Response:**
  - `200 OK`: A list of data entries.
- **For Tariff JSON output, refer to the Example at the end of this README.**

### 2. Search Data by Region
- **Endpoint:** `GET /data/search`
- **Description:** Retrieves a list of data entries filtered by the specified region.
- **Parameters:**
  - `region` (query parameter, required): Region to filter the data by.
- **Response:**
  - `200 OK`: A filtered list of data entries.
- **For Tariff JSON output, refer to the Example at the end of this README.**

### 3. Machine-to-Machine Authentication with OIDC
- **Endpoint:** `POST /authenticate`
- **Description:** Authenticates a machine using OpenID Connect (OIDC) for M2M communication.
- **Security:**
  - Uses TLS 1.3 for secure communication.
  - Authentication is JWT token-based.
  - Clients must present a valid client certificate and JWT for authentication.
- **Response:**
  - `200 OK`: Successfully authenticated.
  - `401 Unauthorized`: Authentication failed.

<!--
## Schema

| Field (Level 0) | Field (Level 1) | Field (Level 2) | Field (Level 3) | Field (Level 4) | Type | Example | Description |
|----------------|----------------|----------------|----------------|----------------|------|---------|-------------|
| object | | | | | string | tariff | |
| object_version | | | | | string | 1.0 | |
| provider_id | | | | | string | prv_63a6087272921ef075a8fd3e | Internal ID of the provider the tariff belongs to. |
| supplier_label | | | | | string | ACME Retail Energy Ltd | |
| tariff_reference | | | | | string | gb-acme | |
| tariff_label | | | | | string | Online Fixed | |
| location_id | | | | | string | loc_641b90b758fb8e6293716e40 | Internal Location ID the tariff element is associated with. |
| region | | | | | string | UKPN | |
| live_mode | | | | | boolean | true | Value true if the object exists in live mode, false otherwise. |
| tariff_date | | | | | string | 2023-04-16T00:00:00+01:00 | |
| tariff_version | | | | | string | 22 | |
| tariff_expiry | | | | | string | <value> | |
| contract_start_date | | | | | string | 2024-09-14T00:00:00+01:00 | Indicates start date of the energy supply contract. |
| contract_end_date | | | | | string | 2025-09-13T00:00:00+01:00 | Indicates end date of the energy supply contract. |
| mpxn | | | | | string | 1012345678901 | |
| is_linked | | | | | boolean | false | Indicates if the tariff is linked to an external data source. |
| direction | | | | | string | IMPORT | Indicates direction of energy transfer (IMPORT or EXPORT). |
| the_type | | | | | string | COMMODITY | Indicates tariff type (COMMODITY or NON_COMMODITY). |
| timezone | | | | | string | Europe/London | The timezone at the location. |
| tariff schedule | | | | | object[] | | Tariff schedule object. |
| | time_of_use | | | | string | DYNAMIC | Type of time-of-use tariff (STATIC or DYNAMIC). |
| | standing_charge | | | | number | 0.321 | £ per day. |
| | months | | | | string[] | ["All"] | Months when the tariff is valid. |
| | days_and_hours | | | | object[] or null | null | null if 'time_of_use' is 'DYNAMIC'. |
| | | days | | | string[] | ["All"] | Days when schedule is valid. |
| | | hours | | | object[] | | Hours when the schedule is valid. |
| | | | valid_from | | string | 00:00:00 | Start time in HH:MM:SS format. |
| | | | valid_to | | string | 00:00:00 | End time in HH:MM:SS format. |
| | | | rate | | object[] | | Tariff rate array object. |
| | | | | to_kwh | number or null | 30.5 | Specifies up to what kWh tariff applies. |
| | | | | value | number or null | 0.12 | £ per kWh. |
| time_created | | | | | string | 2023-05-15T05:37+01:00 | Time when this tariff object was created. |
-->

## Example Tariff JSON Output
```json
{
  "object": "tariff",
  "object_version": "1.0",
  "provider_id": "prv_63a6087272921ef075a8fd3e",
  "supplier_label": "ACME Retail Energy Ltd",
  "tariff_reference": "gb-acme",
  "tariff_label": "Online Fixed",
  "location_id": "loc_641b90b758fb8e6293716e40",
  "region": "UKPN",
  "live_mode": true,
  "tariff_date": "2023-04-16T00:00:00+01:00",
  "tariff_version": "22",
  "tariff_expiry": "<<value>>",
  "contract_start_date": "2024-09-14T00:00:00+01:00",
  "contract_end_date": "2025-09-13T00:00:00+01:00",
  "mpxn": "1012345678901",
  "is_linked": false,
  "direction": "IMPORT",
  "type": "COMMODITY",
  "timezone": "Europe/London",
  "tariff_schedule": [
    {
      "time_of_use": "STATIC",
      "standing_charge": 0.321,
      "months": ["All"],
      "days_and_hours": [
        {
          "days": ["Mon,Tue,Wed,Thu,Fri"],
          "hours": [
            {
              "valid_from": "08:00:00",
              "valid_to": "23:00:00",
              "rate": [
                {
                  "to_kwh": 30.5,
                  "value": 0.12
                }
              ]
            },
            {
              "valid_from": "23:00:00",
              "valid_to": "08:00:00",
              "rate": [
                {
                  "to_kwh": 30.5,
                  "value": 0.08
                }
              ]
            }
          ]
        },
        {
          "days": ["Sat,Sun"],
          "hours": [
            {
              "valid_from": "11:00:00",
              "valid_to": "16:00:00",
              "rate": [
                {
                  "to_kwh": 30.5,
                  "value": 0.14
                }
              ]
            },
            {
              "valid_from": "16:00:00",
              "valid_to": "11:00:00",
              "rate": [
                {
                  "to_kwh": 30.5,
                  "value": 0.22
                }
              ]
            }
          ]
        }
      ]
    }
  ],
  "time_created": "2023-05-15T05:37+01:00"
}
```

