# cis-interfaces

This project contains specifications for the u-space data provisioning and exchange between the CIS and USS.

## Geo-Awareness

ED-318 geozones distribution is done through ASTM UTM [F3548-22](https://github.com/interuss/astm-utm-protocol/) Constraints.

The set of changes from the official specification is defined in the OpenAPI overlay [utm-overlay.yaml](./geoawareness/utm-overlay.yaml):
- relaxing Constraint Reference time bounds.
- required `geozone_ed318` field containing full ED-318 feature at the origin of the constraint.

## DAR Coordinator

Dynamic Airspace Reconfiguration (DAR) is a time-bounded U-space change.

The DAR Coordinator interface is defined in the standalone OpenAPI document
[dar-coordinator.yaml](./dar/dar-coordinator.yaml). It documents:

- test-only `/dar_sandbox` endpoints for creating, retrieving, and
  deactivating DARs;
- the `VACATED` callback a USSP sends after vacating a DAR.

All DAR Coordinator endpoints require the `utm.dar_vacated` scope.

## Surveillance

The distribution of ATC surveillance data follows the data-sharing principles established in the ASTM RemoteID [F3411-22](https://github.com/uastech/standards) standard.

The specification for surveillance data exchange is defined in this OpenAPI [surveillance.yaml](./surveillance/surveillance.yaml).
