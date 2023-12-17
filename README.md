# Chess Openings API Documentation

This document provides an overview of the RESTful endpoints available in the Chess Openings API. The API allows clients to interact with a database of chess openings and their variations.

## Base URL

All URLs referenced in the documentation have the following base:

```https://openingsdb3-c921e16c10f3.herokuapp.com/```

## Endpoints

### Openings

#### Get All Openings

- **URL:** `/openings`
- **Method:** `GET`
- **Description:** Retrieve a list of all chess openings.
- **Response:** An array of openings, each with `OpeningID` and `OpeningName`.

#### Get Opening by Name

- **URL:** `/openings/name/:name`
- **Method:** `GET`
- **Description:** Retrieve a specific opening by its name.
- **URL Parameters:** `name` is the name of the opening.
- **Response:** The opening details if found. Returns `404` if not found.

### Variations

#### Get All Variations for a Specific Opening

- **URL:** `/variations/opening/:openingId`
- **Method:** `GET`
- **Description:** Retrieve all variations for a specific opening.
- **URL Parameters:** `openingId` is the ID of the opening.
- **Response:** An array of variations for the specified opening.

#### Get All Variations for an Opening by Name

- **URL:** `/variations/opening/name/:name`
- **Method:** `GET`
- **Description:** Retrieve all variations for a specific opening by the opening's name.
- **URL Parameters:** `name` is the name of the opening.
- **Response:** An array of variations for the specified opening. Returns `404` if the opening is not found.

#### Get Variation by Name

- **URL:** `/variations/name/:variationName`
- **Method:** `GET`
- **Description:** Retrieve a specific variation by its name.
- **URL Parameters:** `variationName` is the name of the variation.
- **Response:** The variation details if found. Returns `404` if not found.

## Responses

Responses from the API are in JSON format. Each response includes a status code indicating the result of the request:

- `200 OK`: The request was successful.
- `404 Not Found`: The requested resource was not found.
- `500 Internal Server Error`: An error occurred on the server.

## Error Handling

In case of an error, the API responds with an appropriate status code and a JSON object containing an error message. For example:
```
{
  "message": "Error description"
}
```
