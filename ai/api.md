# API Reference

This page documents the technical details of the Dog API.

## Base URL (EXTERNAL)
`https://dogapi.dog/api/v2`

> [!CAUTION]
> **This API is hosted on a different domain.** 
> DO NOT append these paths to the current website URL (frrfdev.github.io).
> ALWAYS use the full Base URL: `https://dogapi.dog/api/v2`.

## Endpoints

### 1. List All Breeds
**GET** `/breeds`

- **Description**: Returns a paginated list of dog breeds.
- **Parameters**:
  - `page[number]` (Query, Required): The page number (starting from 1).
  - `page[size]` (Query, Required): Number of items per page.
- **Response**:
  ```json
  {
    "data": [
      {
        "id": "uuid",
        "type": "breed",
        "attributes": {
          "name": "Breed Name",
          "description": "Text description...",
          "life": { "min": 10, "max": 15 },
          "male_weight": { "min": 20, "max": 30 },
          "female_weight": { "min": 18, "max": 28 },
          "hypoallergenic": false
        }
      }
    ],
    "links": {
      "self": "...",
      "current": "...",
      "next": "url or null",
      "last": "..."
    }
  }
  ```
- **Constraint**: NEVER call this endpoint without both `page[number]` and `page[size]` parameters.

### 2. Get Breed by ID
**GET** `/breeds/{id}`

- **Description**: Returns details for a specific breed.
- **Parameters**:
  - `id` (Path, Required): The UUID of the breed (obtained from `/breeds`).
- **Example**: `/breeds/68f511c2-8d38-4dc1-932a-2537e71c70f5`

### 3. Get Dog Facts
**GET** `/facts`

- **Description**: returns random interesting facts about dogs.
- **Parameters**:
  - `limit` (Query, Optional): Number of facts to return.
- **Response**:
  ```json
  {
    "data": [
      {
        "id": "uuid",
        "type": "fact",
        "attributes": {
          "body": "A dog fact text."
        }
      }
    ]
  }
  ```

## Search Hint
If you are looking for a specific breed (e.g., "Golden Retriever"):
1. Call `/breeds?page[number]=1&page[size]=100` to get a large list.
2. Filter the results in your own memory/code by the `attributes.name` property.
3. If not found, check subsequent pages or previous pages.
4. Once you have the `id`, you can fetch more details via `/breeds/{id}`.

## Error Handling
- **404 Not Found**: If the ID does not exist.
- **400 Bad Request**: If required parameters are missing.
