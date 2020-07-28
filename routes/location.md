# Location Service Routes
The Location module is responsible for providing the current location of users.
Sensor Nodes measure RSSI of all clients nearby and send the values to the master. The master calculates the location via trilateration and provides the data via API endpoints. 
 
 ---
 
## Get location of User or Node
**GET** /api/v1/location/current
>Returns a Location object that contains the current position of the user or the node, depending on the client that sent the request
### Authorization:
JWT required
### Query Params:
None
### Successful Response:
|name|type|description|
|--|--|--|
|id|string|The ID of the node or client requested|
|location|[Location](https://github.com/nickcrd/trable-api-docs/tree/master/models/location.md) object|The physical location of the object
---

## Get all locations
**GET** /api/v1/location/listAll
> Debug only: Returns current locations of all clients and nodes connected
### Authorization:
JWT required. Permission "admin.listAllLocations" required
### Query Params: 
None
### Successful Response:
|name|type|description|
|--|--|--|
|locations|array|Array containing object described below|
| |-> id: string||
| |-> location: location object
---

## Submit RSSI measurement
**POST** /api/v1/location/submitRSSI
> Sensor Nodes use this endpoint to send latest RSSI measurements to the master
### Authorization: 
JWT required, Permission "sensor.submitRSSI" required
### Request Body
|name|type|description|
|--|--|--|
|targetId|string|ID of the client whose RSSI was measured|
|rssi|number|RSSI measured by the node|
|timestamp|number|Timestamp of the measurement in Seconds since UNIX epoch|

### Successful Response:
|name|type|description|
|--|--|--|
|status|number|HTTP response code|


