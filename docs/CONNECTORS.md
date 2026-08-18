# Connectors

PowerQED connects through standard industrial protocols.

Each connector has a Trust Profile.

## Protocols

- SunSpec: solar inverters
- OCPP: EV charging stations
- OpenEMS: energy management gateway
- MQTT: IoT telemetry
- Vendor APIs: cloud APIs from manufacturers

## Trust Profile

Every connector declares:

- Authentication method
- Data integrity level
- Time source
- Firmware verification
- Attestation support

## Design Notes

- Connectors are adapters behind interfaces.
- PowerQED does not claim every JSON is truth.
- PowerQED shows the origin of a fact and the trust level of every link.
- MVP starts with one or two connectors.