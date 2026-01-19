# Odin Weather — API Testing (Postman)

## What’s inside

- Postman collections: "./Geocode API.postman_collection.json" and "./Open Meteo API.postman_collection.json"
- API test cases: "./weather-api-test-cases.md"
- Test run summary: "./TEST_RUN_SUMMARY.md"

## How to run

1. Import the collection JSON into Postman:

   - Postman → Import → Select "./Geocode API.postman_collection.json" or "./Open Meteo API.postman_collection.json"

2. Open the collection → **Variables**

   - Confirm these collection variables exist and have values:

     - "base_url" = "https://geocoding-api.open-meteo.com"
     - "base_url" = "https://api.open-meteo.com"

3. Run the collection

   - Use **Collection Runner** (recommended) OR send requests manually in order.

## Notes

- The APIs used are public and require no auth.
- If requests fail, check your internet connection or API rate limits.
