# API Reference

This page documents the technical details of the Dog API.

## Base URL
`https://dogapi.dog/api/v2`

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

## Error Handling
- **404 Not Found**: If the ID does not exist.
- **400 Bad Request**: If required parameters are missing.
