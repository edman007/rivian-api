---
title: GetVehicleState
parent: Vehicle Info Endpoints
grand_parent: App API
has_children: false
nav_order: 3
---

# GetVehicleState

## Overview

The `GetVehicleState` endpoint returns information about the status of a vehicle, such as speed, location, and closure statuses.

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
  "operationName": "GetVehicleState",
  "variables": {
    "vehicleID": <your-vehicle-id>
  },
  "query": "query GetVehicleState($vehicleID: String!) { vehicleState(id: $vehicleID) { __typename ...vehicleStateFields } }  fragment vehicleStateFields on VehicleState { gnssLocation { latitude longitude timeStamp isAuthorized } gnssSpeed { timeStamp value } gnssAltitude { timeStamp value } gnssError { timeStamp positionVertical positionHorizontal speed bearing } alarmSoundStatus { timeStamp value } timeToEndOfCharge { timeStamp value } doorFrontLeftLocked { timeStamp value } doorFrontLeftClosed { timeStamp value } doorFrontRightLocked { timeStamp value } doorFrontRightClosed { timeStamp value } doorRearLeftLocked { timeStamp value } doorRearLeftClosed { timeStamp value } doorRearRightLocked { timeStamp value } doorRearRightClosed { timeStamp value } windowFrontLeftClosed { timeStamp value } windowFrontRightClosed { timeStamp value } windowFrontLeftCalibrated { timeStamp value } windowFrontRightCalibrated { timeStamp value } windowRearLeftCalibrated { timeStamp value } windowRearRightCalibrated { timeStamp value } windowsNextAction { timeStamp value } closureFrunkLocked { timeStamp value } closureFrunkClosed { timeStamp value } closureFrunkNextAction { timeStamp value } gearGuardLocked { timeStamp value } closureLiftgateLocked { timeStamp value } closureLiftgateClosed { timeStamp value } closureLiftgateNextAction { timeStamp value } windowRearLeftClosed { timeStamp value } windowRearRightClosed { timeStamp value } closureSideBinLeftLocked { timeStamp value } closureSideBinLeftClosed { timeStamp value } closureSideBinRightLocked { timeStamp value } closureSideBinRightClosed { timeStamp value } closureSideBinLeftNextAction { timeStamp value } closureSideBinRightNextAction { timeStamp value } closureTailgateLocked { timeStamp value } closureTailgateClosed { timeStamp value } closureTailgateNextAction { timeStamp value } closureTonneauLocked { timeStamp value } closureTonneauClosed { timeStamp value } wiperFluidState { timeStamp value } powerState { timeStamp value } batteryHvThermalEventPropagation { timeStamp value } twelveVoltBatteryHealth { timeStamp value } vehicleMileage { timeStamp value } brakeFluidLow { timeStamp value } gearStatus { timeStamp value } batteryLevel { timeStamp value } chargerState { timeStamp value } batteryLimit { timeStamp value } remoteChargingAvailable { timeStamp value } batteryHvThermalEvent { timeStamp value } rangeThreshold { timeStamp value } distanceToEmpty { timeStamp value } otaAvailableVersionGitHash { timeStamp value } otaAvailableVersion { timeStamp value } otaCurrentVersionGitHash { timeStamp value } otaCurrentVersion { timeStamp value } otaDownloadProgress { timeStamp value } otaInstallDuration { timeStamp value } otaInstallProgress { timeStamp value } otaInstallReady { timeStamp value } otaInstallTime { timeStamp value } otaInstallType { timeStamp value } otaStatus { timeStamp value } otaCurrentStatus { timeStamp value } cabinClimateInteriorTemperature { timeStamp value } cabinPreconditioningStatus { timeStamp value } cabinPreconditioningType { timeStamp value } petModeStatus { timeStamp value } petModeTemperatureStatus { timeStamp value } cabinClimateDriverTemperature { timeStamp value } gearGuardVideoStatus { timeStamp value } gearGuardVideoMode { timeStamp value } gearGuardVideoTermsAccepted { timeStamp value } defrostDefogStatus { timeStamp value } steeringWheelHeat { timeStamp value } seatFrontLeftHeat { timeStamp value } seatFrontRightHeat { timeStamp value } seatRearLeftHeat { timeStamp value } seatRearRightHeat { timeStamp value } chargerStatus { timeStamp value } seatFrontLeftVent { timeStamp value } seatFrontRightVent { timeStamp value } chargerDerateStatus { timeStamp value } driveMode { timeStamp value } serviceMode { timeStamp value } trailerStatus { timeStamp value } btmFfHardwareFailureStatus { timeStamp value } btmIcHardwareFailureStatus { timeStamp value } btmLfdHardwareFailureStatus { timeStamp value } btmRfHardwareFailureStatus { timeStamp value } btmRfdHardwareFailureStatus { timeStamp value } carWashMode { timeStamp value } chargePortState { timeStamp value } chargingTimeEstimationValidity { timeStamp value } limitedAccelCold { timeStamp value } limitedRegenCold { timeStamp value } rearHitchStatus { timeStamp value } supportedFeatures { name status } }"
}
```

### Example Response

```json
{
  "data": {
    "vehicleState": {
      "__typename": "VehicleState",
      "gnssLocation": {
        "latitude": <your-lat>,
        "longitude": <your-lon>,
        "timeStamp": "2024-02-20T12:37:42.052Z",
        "isAuthorized": true
      },
      "gnssSpeed": {
        "timeStamp": "2024-02-20T12:37:42.052Z",
        "value": 0
      },
      "gnssAltitude": {
        "timeStamp": "2024-02-20T12:37:42.052Z",
        "value": null
      },
      "gnssError": {
        "timeStamp": "2024-02-20T12:37:42.052Z",
        "positionVertical": 1.344,
        "positionHorizontal": 1.968,
        "speed": 0.09,
        "bearing": 0.7453
      },
      "alarmSoundStatus": {
        "timeStamp": "2024-02-19T19:58:54.954Z",
        "value": "false"
      },
      "timeToEndOfCharge": {
        "timeStamp": "2024-02-20T12:36:07.281Z",
        "value": 1
      },
      "doorFrontLeftLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "locked"
      },
      "doorFrontLeftClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "doorFrontRightLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "locked"
      },
      "doorFrontRightClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "doorRearLeftLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "locked"
      },
      "doorRearLeftClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "doorRearRightLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "locked"
      },
      "doorRearRightClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "windowFrontLeftClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "windowFrontRightClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "windowFrontLeftCalibrated": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "Calibrated"
      },
      "windowFrontRightCalibrated": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "Calibrated"
      },
      "windowRearLeftCalibrated": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "Calibrated"
      },
      "windowRearRightCalibrated": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "Calibrated"
      },
      "windowsNextAction": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "Open_Allowed"
      },
      "closureFrunkLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "locked"
      },
      "closureFrunkClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "closureFrunkNextAction": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "Open_Allowed"
      },
      "gearGuardLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "unlocked"
      },
      "closureLiftgateLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "locked"
      },
      "closureLiftgateClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureLiftgateNextAction": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "SNA"
      },
      "windowRearLeftClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "windowRearRightClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "closed"
      },
      "closureSideBinLeftLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureSideBinLeftClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureSideBinRightLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureSideBinRightClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureSideBinLeftNextAction": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "SNA"
      },
      "closureSideBinRightNextAction": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "SNA"
      },
      "closureTailgateLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureTailgateClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureTailgateNextAction": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "SNA"
      },
      "closureTonneauLocked": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "closureTonneauClosed": {
        "timeStamp": "2024-02-20T11:39:28.553Z",
        "value": "signal_not_available"
      },
      "wiperFluidState": {
        "timeStamp": "2024-02-17T19:20:25.705Z",
        "value": "normal"
      },
      "powerState": {
        "timeStamp": "2024-02-20T12:37:16.682Z",
        "value": "sleep"
      },
      "batteryHvThermalEventPropagation": {
        "timeStamp": "2024-02-20T11:39:32.327Z",
        "value": "nominal"
      },
      "twelveVoltBatteryHealth": {
        "timeStamp": "2024-02-20T11:39:32.327Z",
        "value": "NORMAL_OPERATION"
      },
      "vehicleMileage": {
        "timeStamp": "2024-02-19T19:54:57.684Z",
        "value": 6080979
      },
      "brakeFluidLow": null,
      "gearStatus": {
        "timeStamp": "2024-02-20T12:37:16.663Z",
        "value": "park"
      },
      "batteryLevel": {
        "timeStamp": "2024-02-20T12:36:10.535Z",
        "value": 69.900002
      },
      "chargerState": {
        "timeStamp": "2024-02-20T12:36:14.781Z",
        "value": "charging_complete"
      },
      "batteryLimit": {
        "timeStamp": "2024-02-20T12:36:14.781Z",
        "value": 70
      },
      "remoteChargingAvailable": {
        "timeStamp": "2024-02-20T12:36:14.781Z",
        "value": 0
      },
      "batteryHvThermalEvent": {
        "timeStamp": "2024-02-18T21:11:35.762Z",
        "value": "off"
      },
      "rangeThreshold": {
        "timeStamp": "2024-02-20T12:35:10.524Z",
        "value": "vehicle_range_normal"
      },
      "distanceToEmpty": {
        "timeStamp": "2024-02-20T12:35:10.524Z",
        "value": 351
      },
      "otaAvailableVersionGitHash": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": ""
      },
      "otaAvailableVersion": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": "0.0.0"
      },
      "otaCurrentVersionGitHash": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": "09eae800"
      },
      "otaCurrentVersion": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": "2024.03.02"
      },
      "otaDownloadProgress": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": 0
      },
      "otaInstallDuration": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": 0
      },
      "otaInstallProgress": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": 0
      },
      "otaInstallReady": {
        "timeStamp": "2024-02-20T11:39:30.852Z",
        "value": "ota_available"
      },
      "otaInstallTime": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": 0
      },
      "otaInstallType": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": "Convenience"
      },
      "otaStatus": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": "Idle"
      },
      "otaCurrentStatus": {
        "timeStamp": "2024-02-15T12:53:40.798Z",
        "value": "Install_Success"
      },
      "cabinClimateInteriorTemperature": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": -3
      },
      "cabinPreconditioningStatus": {
        "timeStamp": "2024-02-20T12:36:15.311Z",
        "value": "undefined"
      },
      "cabinPreconditioningType": {
        "timeStamp": "2024-02-20T12:36:15.311Z",
        "value": "NONE"
      },
      "petModeStatus": {
        "timeStamp": "2024-02-20T12:36:15.212Z",
        "value": "Disabled"
      },
      "petModeTemperatureStatus": {
        "timeStamp": "2024-02-20T12:36:15.212Z",
        "value": "Default"
      },
      "cabinClimateDriverTemperature": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": 19
      },
      "gearGuardVideoStatus": {
        "timeStamp": "2024-02-19T19:41:42.697Z",
        "value": "Enabled"
      },
      "gearGuardVideoMode": {
        "timeStamp": "2024-02-19T19:41:42.697Z",
        "value": "Away_From_Home"
      },
      "gearGuardVideoTermsAccepted": {
        "timeStamp": "2024-02-19T19:41:42.697Z",
        "value": "true"
      },
      "defrostDefogStatus": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "steeringWheelHeat": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "seatFrontLeftHeat": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "seatFrontRightHeat": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "seatRearLeftHeat": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "seatRearRightHeat": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "chargerStatus": {
        "timeStamp": "2024-02-20T12:36:14.781Z",
        "value": "chrgr_sts_connected_no_chrg"
      },
      "seatFrontLeftVent": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "seatFrontRightVent": {
        "timeStamp": "2024-02-20T12:29:01.304Z",
        "value": "Off"
      },
      "chargerDerateStatus": {
        "timeStamp": "2024-02-20T12:36:14.781Z",
        "value": "NONE"
      },
      "driveMode": {
        "timeStamp": "2024-02-20T11:39:32.967Z",
        "value": "everyday"
      },
      "serviceMode": {
        "timeStamp": "2024-02-20T11:39:30.847Z",
        "value": "off"
      },
      "trailerStatus": {
        "timeStamp": "2024-02-20T12:37:16.663Z",
        "value": "TRAILER_NOT_PRESENT"
      },
      "btmFfHardwareFailureStatus": {
        "timeStamp": "2024-02-20T12:33:25.783Z",
        "value": "dtc_not_set"
      },
      "btmIcHardwareFailureStatus": {
        "timeStamp": "2024-02-20T12:37:16.191Z",
        "value": "dtc_not_set"
      },
      "btmLfdHardwareFailureStatus": {
        "timeStamp": "2024-02-20T12:34:10.794Z",
        "value": "dtc_not_set"
      },
      "btmRfHardwareFailureStatus": {
        "timeStamp": "2024-02-20T12:37:17.091Z",
        "value": "dtc_not_set"
      },
      "btmRfdHardwareFailureStatus": {
        "timeStamp": "2024-02-20T12:37:00.171Z",
        "value": "dtc_not_set"
      },
      "carWashMode": {
        "timeStamp": "2024-02-20T11:39:30.847Z",
        "value": "off"
      },
      "chargePortState": {
        "timeStamp": "2024-02-19T19:55:12.352Z",
        "value": "open"
      },
      "chargingTimeEstimationValidity": {
        "timeStamp": "2024-02-20T12:36:14.781Z",
        "value": "SNA"
      },
      "limitedAccelCold": {
        "timeStamp": "2024-02-20T12:37:16.446Z",
        "value": 0
      },
      "limitedRegenCold": {
        "timeStamp": "2024-02-20T12:37:16.446Z",
        "value": 0
      },
      "rearHitchStatus": null,
      "supportedFeatures": [
        {
          "name": "ADDR_SHR",
          "status": "AVAILABLE"
        },
        {
          "name": "ADDR_SHR_TXT",
          "status": "AVAILABLE"
        },
        {
          "name": "ADDR_SHR_YLP",
          "status": "AVAILABLE"
        },
        {
          "name": "CAR_WASH_MODE",
          "status": "AVAILABLE"
        },
        {
          "name": "CHARG_CMD",
          "status": "AVAILABLE"
        },
        {
          "name": "CHARG_SCHED",
          "status": "AVAILABLE"
        },
        {
          "name": "CHARG_SLIDER",
          "status": "AVAILABLE"
        },
        {
          "name": "DEFROST_DEFOG",
          "status": "AVAILABLE"
        },
        {
          "name": "FRUNK_NXT_ACT",
          "status": "AVAILABLE"
        },
        {
          "name": "GEAR_GUARD_VIDEO_SETTING",
          "status": "AVAILABLE"
        },
        {
          "name": "HEATED_SEATS",
          "status": "AVAILABLE"
        },
        {
          "name": "HEATED_SEATS_EXT",
          "status": "AVAILABLE"
        },
        {
          "name": "HEATED_WHEEL",
          "status": "AVAILABLE"
        },
        {
          "name": "LIFTGATE_CMD",
          "status": "AVAILABLE"
        },
        {
          "name": "PET_MODE",
          "status": "AVAILABLE"
        },
        {
          "name": "PRECON_CMD_RESP",
          "status": "AVAILABLE"
        },
        {
          "name": "PRECON_SCRN_PROT",
          "status": "AVAILABLE"
        },
        {
          "name": "RENAME_VEHICLE",
          "status": "AVAILABLE"
        },
        {
          "name": "SCHED_DPRT",
          "status": "AVAILABLE"
        },
        {
          "name": "SET_TEMP_CMD",
          "status": "AVAILABLE"
        },
        {
          "name": "TRAILER_STATUS",
          "status": "AVAILABLE"
        },
        {
          "name": "TRIP_ADD_STOP",
          "status": "AVAILABLE"
        },
        {
          "name": "TRIP_PLANNER",
          "status": "AVAILABLE"
        },
        {
          "name": "TRIP_PLANNER_DRIVE_MODE",
          "status": "AVAILABLE"
        },
        {
          "name": "VENTED_SEATS",
          "status": "AVAILABLE"
        },
        {
          "name": "WIN_CALIB_STS",
          "status": "AVAILABLE"
        },
        {
          "name": "WIN_NXT_ACT",
          "status": "AVAILABLE"
        }
      ]
    }
  }
}
```
