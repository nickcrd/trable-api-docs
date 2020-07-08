
# Trable API Documentation
Welcome to the Trable API Documentation. This GitHub Repo describes the API provided by the main Trable application which is used by the frontend and client mobile apps.

<br/>

> ### Warning - Work In Progress
> This project is still very early in the design phase and is subject to change. New changes will be progressively added to this documentation and some functionality may be completely scrapped. 

<br/>

## Authentication
Most API routes require authentication. This is done via **JWT** (JSON Web Tokens)  authentication. The key is provided via the Authorization header as described below:
```HTTP
Authorization: Bearer <JWT>
```
The JWT payload contains this data:
|key|description  |
|--|--|
|id|The user/entity id|
|iat|Timestamp when the token was issued, used to invalidate old tokens

## Responses & Error Handling
The API will send responses in the JSON format. When an error occurrs while executing an API request, a JSON payload including a status code (which corresponds to the HTTP status code) and an error message will be returned. See example below:
```json
{
  "status": 500,
  "message": "A description of the error occurred"
}
```
## Routes
Browse available API routes doucmentation by clicking on the link below
- [Auth Manager Routes (/auth)](https://github.com/nickcrd/trable-api-docs/blob/master/routes/auth.md)
- [Device Manager Routes (/device)](https://github.com/nickcrd/trable-api-docs/blob/master/routes/device.md)
- [Location Service Routes (/location)](https://github.com/nickcrd/trable-api-docs/blob/master/routes/location.md)
