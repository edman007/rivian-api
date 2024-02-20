---
title: planTrip
parent: Vehicle Info Endpoints
grand_parent: App API
has_children: false
nav_order: 3
---

# planTrip

## Overview

The `planTrip` endpoint is used for planning charging stops along a route.

`POST https://rivian.com/api/gql/gateway/graphql`

### Required Headers

```text
a-sess: <your app session token>
u-sess: <your user session token>
csrf-token: <your CSRF token>
```

### Request Body

```json
{
  "operationName": "planTrip",
  "variables": {
    "origin": {
      "latitude": 40.7685063,
      "longitude": -73.977357
    },
    "destination": {
      "latitude": 38.889573,
      "longitude": -77.0091605
    },
    "bearing": 0,
    "vehicleId": <your-vehicle-id>,
    "startingSoc": 57.20000076293945,
    "startingRangeMeters": 298000,
    "targetArrivalSocPercent": 20,
    "driveMode": "winter",
    "networkPreferences": [
      {
        "networkId": "10001",
        "preference": 1
      },
      {
        "networkId": "10002",
        "preference": 1
      },
      {
        "networkId": "10031",
        "preference": 1
      },
      {
        "networkId": "10050",
        "preference": 1
      },
      {
        "networkId": "10050",
        "preference": 1
      }
    ]
  },
  "query": "query planTrip($origin: CoordinatesInput!, $destination: CoordinatesInput!, $bearing: Float!, $vehicleId: String!, $startingSoc: Float!, $startingRangeMeters: Float!, $targetArrivalSocPercent: Float, $driveMode: String, $networkPreferences: [NetworkPreference!]) { planTrip(bearing: $bearing, vehicleId: $vehicleId, startingSoc: $startingSoc, origin: $origin, destination: $destination, startingRangeMeters: $startingRangeMeters, targetArrivalSocPercent: $targetArrivalSocPercent, driveMode: $driveMode, networkPreferences: $networkPreferences) { routes { routeResponse destinationReached totalChargingDuration arrivalSOC arrivalReachableDistance waypoints { waypointType entityId name latitude longitude maxPower chargeDuration arrivalSOC arrivalReachableDistance departureSOC departureReachableDistance } energyConsumptionOnLeg batteryEmptyToDestinationDistance batteryEmptyLocationLatitude batteryEmptyLocationLongitude } tripPlanStatus chargeStationsAvailable socBelowLimit } }"
}
```

### Example Response

```json
{
  "data": {
    "planTrip": {
      "routes": [
        {
          "routeResponse": <large-object-with-route-data>,
          "destinationReached": true,
          "totalChargingDuration": 2232,
          "arrivalSOC": 20,
          "arrivalReachableDistance": 104000,
          "waypoints": [
            {
              "waypointType": "DC_CHARGE_STATION",
              "entityId": "riv_chrg_2564224766546878632",
              "name": "3995 Aramingo Ave, Philadelphia [EVgo]",
              "latitude": 39.99734115600586,
              "longitude": -75.08834838867188,
              "maxPower": 350,
              "chargeDuration": 2232,
              "arrivalSOC": 17,
              "arrivalReachableDistance": 89000,
              "departureSOC": 76,
              "departureReachableDistance": 397000
            },
            {
              "waypointType": "OTHER",
              "entityId": null,
              "name": null,
              "latitude": 38.889573,
              "longitude": -77.0091605,
              "maxPower": null,
              "chargeDuration": 0,
              "arrivalSOC": 20,
              "arrivalReachableDistance": 104000,
              "departureSOC": 20,
              "departureReachableDistance": 104000
            }
          ],
          "energyConsumptionOnLeg": null,
          "batteryEmptyToDestinationDistance": null,
          "batteryEmptyLocationLatitude": null,
          "batteryEmptyLocationLongitude": null
        }
      ],
      "tripPlanStatus": "Ok",
      "chargeStationsAvailable": true,
      "socBelowLimit": false
    }
  }
}
```
