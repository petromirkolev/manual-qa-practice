# Odin Weather – API Test Cases

## Geocoding API

### TC-API-GEO-001 – Valid city returns at least one result

**Endpoint:** `GET /v1/geocoding`

**Purpose:** Verify that a valid city name returns a non-empty result set.

**Preconditions:**

- API is reachable.
- `name` parameter is set to a real city (e.g. `Plovdiv`).

**Request:**

- Method: GET
- URL: `/v1/geocoding?name=Plovdiv&count=1`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is `200`.
- Response body contains a `results` array.
- `results.length >= 1`.
- First result has at least:
  - `name` (string, non-empty)
  - `latitude` (number)
  - `longitude` (number).

### TC-API-GEO-002 – Unknown/invalid city returns no results

**Endpoint:** `GET /v1/geocoding`

**Purpose:** Verify behavior when an unknown city is requested.

**Preconditions:**

- API is reachable.

**Request:**

- Method: GET
- URL: `/v1/geocoding?name=asdkjashdkjashd&count=5`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is `200` (or appropriate success code per API docs).
- `results` is either:
  - an empty array, or
  - missing / null with a dedicated flag indicating "no results".
- No error is returned.

### TC-API-GEO-003 – Missing required parameter `name`

**Endpoint:** `GET /v1/geocoding`

**Purpose:** Verify API validation when required parameter is missing.

**Preconditions:**

- API is reachable.

**Request:**

- Method: GET
- URL: `/v1/geocoding?count=1` (no `name` query param)

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is a client error (e.g. `400` or `422`) **or** a valid 200 with clear error message (depending on API spec).
- Response contains an error description indicating missing or invalid `name` parameter.

### TC-API-GEO-004 – Multiple results when city name is ambiguous

**Endpoint:** `GET /v1/geocoding`

**Purpose:** Verify that ambiguous city names return multiple candidates.

**Preconditions:**

- API is reachable.
- Selected city name exists in multiple locations (e.g. `Springfield`, `Sofia` with different countries depending on API).

**Request:**

- Method: GET
- URL: `/v1/geocoding?name=Springfield&count=10`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is `200`.
- `results.length >= 2` (if such city is known to have multiple matches).
- Each result has at least:
  - `name`
  - `country`
  - `latitude`
  - `longitude`.

---

## Forecast API

### TC-API-FORECAST-001 – Valid coordinates return current weather

**Endpoint:** `GET /v1/forecast`

**Purpose:** Verify that valid coordinates return current weather data.

**Preconditions:**

- API is reachable.
- Valid coordinates are known (e.g. Plovdiv lat/lon).

**Request:**

- Method: GET
- URL: `/v1/forecast?latitude=42.1354&longitude=24.7453&current_weather=true`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is `200`.
- Response includes a `current_weather` object.
- `current_weather` contains at least:
  - `temperature` (number)
  - `windspeed` (number)
  - `weathercode` or equivalent condition field.

### TC-API-FORECAST-002 – Missing latitude parameter

**Endpoint:** `GET /v1/forecast`  
**Purpose:** Verify behavior when `latitude` is missing.

**Preconditions:**

- API is reachable.

**Request:**

- Method: GET
- URL: `/v1/forecast?longitude=24.7453&current_weather=true`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is a client error (e.g. `400` or `422`), or explicit error response according to API spec.
- Error message indicates missing/invalid `latitude` parameter.
- No `current_weather` data is returned.

### TC-API-FORECAST-003 – Missing longitude parameter

**Endpoint:** `GET /v1/forecast`  
**Purpose:** Verify behavior when `longitude` is missing.

**Preconditions:**

- API is reachable.

**Request:**

- Method: GET
- URL: `/v1/forecast?latitude=42.1354&current_weather=true`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is a client error (e.g. `400` or `422`), or explicit error response according to API spec.
- Error message indicates missing/invalid `longitude` parameter.
- No `current_weather` data is returned.

### TC-API-FORECAST-004 – Latitude out of valid range

**Endpoint:** `GET /v1/forecast`  
**Purpose:** Verify validation for latitude range.

**Preconditions:**

- API is reachable.

**Request:**

- Method: GET
- URL: `/v1/forecast?latitude=999&longitude=24.7453&current_weather=true`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is a client error (e.g. `400` or `422`), or explicit error response according to API spec.
- Response indicates invalid latitude range.
- No valid forecast data is returned.

### TC-API-FORECAST-005 – Daily forecast returns requested number of days

**Endpoint:** `GET /v1/forecast`  
**Purpose:** Verify that the `days` or `forecast_days` parameter limits the number of returned days.

**Preconditions:**

- API is reachable.
- The forecast endpoint supports a parameter to control number of forecast days (e.g. `forecast_days`, `days`, `daily=...` + `timezone=...`).

**Request:**

- Method: GET
- Example URL (adapt to actual API):
  - `/v1/forecast?latitude=42.1354&longitude=24.7453&daily=temperature_2m_max&forecast_days=3`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is `200`.
- Response includes a `daily` object.
- `daily.time` (or equivalent date array) has length `3`.
- Each element has a corresponding `temperature_2m_max` value.

### TC-API-FORECAST-006 – Timezone handling

**Endpoint:** `GET /v1/forecast`

**Purpose:** Verify that specifying a timezone parameter affects the returned timezone field.

**Preconditions:**

- API is reachable.
- Forecast endpoint supports `timezone` parameter.

**Request:**

- Method: GET
- URL (example): `/v1/forecast?latitude=42.1354&longitude=24.7453&current_weather=true&timezone=Europe/Sofia`

**Steps:**

1. Send the above request.

**Expected result:**

- Status code is `200`.
- Response field `timezone` equals `Europe/Sofia` (or equivalent).
- `utc_offset_seconds` is consistent with the requested timezone (not mandatory to check in detail, but can be noted).
