---
title: CurrentUser
parent: Account Endpoints
grand_parent: App API
has_children: false
nav_order: 3
---

# CurrentUser

## Overview

The `CurrentUser` endpoint returns information about the user's account.

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
  "operationName": "CurrentUser",
  "variables": {},
  "query": "query CurrentUser { currentUser { __typename ...CurrentUserFields } }  fragment CurrentUserFields on User { id settings { distanceUnit { value timestamp } temperatureUnit { value timestamp } } firstName lastName email address { country } vehicles { id owner roles vin vas { vasVehicleId vehiclePublicKey } vehicle { deviceSlots { phone { max free } } model mobileConfiguration { trimOption { optionId optionName } exteriorColorOption { optionId optionName } interiorColorOption { optionId optionName } driveSystemOption { optionId optionName } tonneauOption { optionId optionName } wheelOption { optionId optionName } driveSystemTowingDriveModes driveSystemDriveModes maxVehiclePower } maintenanceSchedule { sections { items { description isDue } serviceLifetime { __typename ... on MaintenanceDistanceLimit { km mi } ... on MaintenanceDateLimit { year } } } } } settings { name { value } } } enrolledPhones { vas { vasPhoneId publicKey } enrolled { deviceType deviceName vehicleId identityId shortName } } pendingInvites { id invitedByFirstName role status vehicleId vehicleModel email } }"
}
```

### Example Response

```json
{
  "data": {
    "currentUser": {
      "__typename": "User",
      "id": <your-user-id>,
      "settings": {
        "distanceUnit": null,
        "temperatureUnit": null
      },
      "firstName": <your-first-name>,
      "lastName": <your-last-name>,
      "email": <your-email>,
      "address": null,
      "vehicles": [
        {
          "id": <your-vehicle-id>,
          "owner": null,
          "roles": [
            "driver"
          ],
          "vin": <your-vin>,
          "vas": {
            "vasVehicleId": <your-vas-vehicleID>,
            "vehiclePublicKey": <your-vas-public-key>
          },
          "vehicle": {
            "deviceSlots": {
              "phone": {
                "max": 4,
                "free": 3
              }
            },
            "model": "R1S",
            "mobileConfiguration": {
              "trimOption": {
                "optionId": "PKG-ADV",
                "optionName": "Adventure Package"
              },
              "exteriorColorOption": {
                "optionId": "EXP-CYL",
                "optionName": "Compass Yellow"
              },
              "interiorColorOption": {
                "optionId": "INT-GYP",
                "optionName": "Ocean Coast + Dark Ash Wood"
              },
              "driveSystemOption": {
                "optionId": "MOT-401",
                "optionName": "Quad-Motor AWD"
              },
              "tonneauOption": null,
              "wheelOption": {
                "optionId": "WHL-1RD",
                "optionName": "21\" Road"
              },
              "driveSystemTowingDriveModes": [
                "everyday",
                "off_road_auto",
                "winter"
              ],
              "driveSystemDriveModes": [
                "everyday",
                "off_road_auto",
                "winter",
                "sport",
                "distance",
                "off_road_rocks",
                "off_road_sport_auto",
                "off_road_sport_drift",
                "off_road_sand"
              ],
              "maxVehiclePower": 215
            },
            "maintenanceSchedule": {
              "sections": [
                {
                  "items": [
                    {
                      "description": "Tire rotation",
                      "isDue": null
                    },
                    {
                      "description": "Multi-point inspection",
                      "isDue": null
                    }
                  ],
                  "serviceLifetime": {
                    "__typename": "MaintenanceDistanceLimit",
                    "km": 12000,
                    "mi": 7500
                  }
                },
                {
                  "items": [
                    {
                      "description": "Brake fluid flush",
                      "isDue": false
                    }
                  ],
                  "serviceLifetime": {
                    "__typename": "MaintenanceDateLimit",
                    "year": 3
                  }
                },
                {
                  "items": [
                    {
                      "description": "Coolant change",
                      "isDue": null
                    },
                    {
                      "description": "Drive unit fluid change (Quad-Motor AWD vehicles only)",
                      "isDue": null
                    }
                  ],
                  "serviceLifetime": {
                    "__typename": "MaintenanceDistanceLimit",
                    "km": 180000,
                    "mi": 112500
                  }
                }
              ]
            }
          },
          "settings": {
            "name": {
              "value": "Banana"
            }
          }
        }
      ],
      "enrolledPhones": [],
      "pendingInvites": []
    }
  }
}
```
