# API Testing Exercise — DummyJSON (Postman)

## Goal

Practice API testing in Postman: request design, assertions, variables, and negative cases using the DummyJSON public API.

## Contents

- Postman collection: "./DummyJSON.postman_collection.json"
- Postman collection: "./JSONPlaceholder.postman_collection.json"
- Test notes / cases: "./test-cases"

## How to run

1. Import the collection:

   - Postman → Import → select "DummyJSON.postman_collection.json" or "JSONPlaceholder.postman_collection.json"

2. Collection variables

- "base_url" = set in Collection → Variables

3. Run

- Use Collection Runner (recommended) or send requests manually.

## Notes

- No authentication required.
- Tests cover typical flows: list, single resource, invalid id, status code checks, basic schema checks.
