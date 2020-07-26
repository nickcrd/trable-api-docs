
# Device Manager Routes
The Device Manager module is responsible for the management and registration of both sensor nodes and client nodes.

## About Nodes
There are two types of nodes to be differentiated: Sensor Nodes and Client Nodes
Sensor Nodes are responsible for collecting the RSSI from Bluetooth packets send out by client nodes.
Client Nodes need to connect to the master in order to get a public id, which will be sent in the Bluetooth packets.
 
 ---
 
## Enroll new Sensor Node
**GET** /api/v1/devices/enrollNode
>Enrolls a sensor node to the master and returns a generated Node ID and API Key
### Authorization:
JWT required
### Request Body: 
|name|type|description|
|--|--|--|
|displayName|string|Name of the node to be shown in dashboard|
|location|(Location)[https://github.com/nickcrd/trable-api-docs/tree/master/models/location.md] object|The physical location of the node in x,y,z coordinates|
### Successful Response:
|name|type|description|
|--|--|--|
|nodeId|string|The generated node ID for the new node|
|apiKey|string|A JWT API Key to be used by the new node|

---

## Enroll new Client
**GET** /api/v1/devices/enrollClient
> This route will be called when the client app is installed the first time. A new API key and a public client id will be generated and returned
### Authorization:
None
### Query Params: 
None
### Successful Response:
|name|type|description|
|--|--|--|
|clientId|string|The generated public client ID for the new node|
|apiKey|string|A JWT API Key to be used by the client|

---

## Heartbeat
**GET** /api/v1/devices/heartbeat
> Sensor nodes use this route to send out their heartbeat. This will keep the node listed as online on the master
### Authorization: 
JWT required
### Query Params:
None
### Successful Response:
|name|type|description|
|--|--|--|
|status|number|HTTP response code|


