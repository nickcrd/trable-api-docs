
# Trable API Documentation
Welcome to the Trable API Documentation. This GitHub Repo describes the API provided by the main Trable application which is used by the frontend and client mobile apps.

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

## Error Handling 
When an error occurrs while executing an API request, a payload like below will be returned together with the corresponding HTTP code.
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
