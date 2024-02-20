---
title: getVehicleImages
parent: Vehicle Info Endpoints
grand_parent: App API
has_children: false
nav_order: 3
---

# getVehicleImages

## Overview

The `getVehicleImages` endpoint returns image assets for your vehicles.

If you are just looking for the images from the configurator, see [Configurator API](/configurator/).

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
  "operationName": "getVehicleImages",
  "variables": {
    "extension": "webp",
    "resolution": "hdpi",
    "versionForVehicle": "2",
    "versionForPreOrdere": "1"
  },
  "query": "query getVehicleImages($extension: String!, $resolution: String!, $versionForVehicle: String!, $versionForPreOrdere: String!) { getVehicleOrderMobileImages(resolution: $resolution, extension: $extension, version: $versionForPreOrdere) { orderId url resolution size design placement overlays { url overlay zIndex } } getVehicleMobileImages(resolution: $resolution, extension: $extension, version: $versionForVehicle) { vehicleId url resolution size design placement overlays { url overlay zIndex } } }"
}
```

### Example Response

```json
{
  "data": {
    "getVehicleOrderMobileImages": [
],
    "getVehicleMobileImages": [
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_front_dark_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "dark",
        "placement": "front",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_front_carwash_dark_hdpi.webp",
            "overlay": "carwash",
            "zIndex": 2
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_front_dark_small_hdpi.webp",
        "resolution": "hdpi",
        "size": "small",
        "design": "dark",
        "placement": "front",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_front_carwash_dark_hdpi.webp",
            "overlay": "carwash",
            "zIndex": 2
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_front_light_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "light",
        "placement": "front",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_front_carwash_light_hdpi.webp",
            "overlay": "carwash",
            "zIndex": 2
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_front_light_small_hdpi.webp",
        "resolution": "hdpi",
        "size": "small",
        "design": "light",
        "placement": "front",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_front_carwash_light_hdpi.webp",
            "overlay": "carwash",
            "zIndex": 2
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_in-use_dark_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "dark",
        "placement": "in-use",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_in-use_trailer_dark_hdpi.webp",
            "overlay": "trailer",
            "zIndex": 1
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_in-use_light_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "light",
        "placement": "in-use",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_in-use_trailer_light_hdpi.webp",
            "overlay": "trailer",
            "zIndex": 1
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_rear_dark_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "dark",
        "placement": "rear",
        "overlays": []
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_rear_light_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "light",
        "placement": "rear",
        "overlays": []
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_side-charging_dark_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "dark",
        "placement": "side-charging",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-complete_dark_hdpi.webp",
            "overlay": "charging-complete",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-error_dark_hdpi.webp",
            "overlay": "charging-error",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-initiating_dark_hdpi.webp",
            "overlay": "charging-initiating",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-inprogress_dark_hdpi.webp",
            "overlay": "charging-inprogress",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-scheduled_dark_hdpi.webp",
            "overlay": "charging-scheduled",
            "zIndex": 1
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_side-charging_light_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "light",
        "placement": "side-charging",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-complete_light_hdpi.webp",
            "overlay": "charging-complete",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-error_light_hdpi.webp",
            "overlay": "charging-error",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-initiating_light_hdpi.webp",
            "overlay": "charging-initiating",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-inprogress_light_hdpi.webp",
            "overlay": "charging-inprogress",
            "zIndex": 1
          },
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-charging_charging-scheduled_light_hdpi.webp",
            "overlay": "charging-scheduled",
            "zIndex": 1
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_side-rear_dark_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "dark",
        "placement": "side-rear",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-rear_trailer_dark_hdpi.webp",
            "overlay": "trailer",
            "zIndex": 1
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_side-rear_light_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "light",
        "placement": "side-rear",
        "overlays": [
          {
            "url": "https://rivian.com/mobile/static/img/v2/overlay/r1s/2021/r1s_2021_21_side-rear_trailer_light_hdpi.webp",
            "overlay": "trailer",
            "zIndex": 1
          }
        ]
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_side_dark_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "dark",
        "placement": "side",
        "overlays": []
      },
      {
        "vehicleId": <your-vehicle-id>,
        "url": "https://rivian.com/mobile/static/img/v2/vehicle/r1s/2021/adventure/ext/compass-yellow/21aer-brit-as/r1s_2021_adventure_ext_compass-yellow_21aer-brit-as_side_light_large_hdpi.webp",
        "resolution": "hdpi",
        "size": "large",
        "design": "light",
        "placement": "side",
        "overlays": []
      }
    ]
  }
}
```

The getVehicleOrderMobileImages element is array of images, similar to getVehicleMobileImages, but vehicleId is replaced with orderId.