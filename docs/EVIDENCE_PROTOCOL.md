# Energy Evidence Protocol

The Energy Evidence Protocol defines the canonical format for energy events.

It is independent of blockchain, storage and proof systems.

## Event

- Event ID
- Source ID
- Event Type
- Interval Start
- Interval End
- Value
- Unit
- Direction
- Sequence
- Timestamp
- Previous Event Hash
- Signature

## Event Types

- Generation
- Consumption
- Storage Charge
- Storage Discharge
- Grid Import
- Grid Export
- Temperature
- State Change

## Source Identity

- Device ID
- Manufacturer
- Model
- Serial Number
- Gateway ID
- Firmware Digest
- Attestation Type

## Integrity

- Payload Hash
- Signature
- Signature Algorithm
- Public Key Reference

## Design Notes

- Events are source-local sequenced.
- Global order is achieved through Merkle batches.
- Protocol is versioned.