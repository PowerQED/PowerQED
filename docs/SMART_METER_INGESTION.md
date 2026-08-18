# Smart Meter Ingestion

Smart meters produce the raw energy measurements behind every claim.

PowerQED ingests signed meter events through a dedicated endpoint.

## Endpoint

POST /v1/events

## Event Schema

- eventId
- sourceId
- eventType
- intervalStart
- intervalEnd
- value
- unit
- direction
- sequence
- timestamp
- previousEventHash
- signature

## Event Types

- Generation
- Consumption
- GridImport
- GridExport
- StorageCharge
- StorageDischarge

## Trust Profile

Each smart meter has an assurance profile:

- Identity
- Authentication
- Integrity
- Attestation
- Metrology
- Time
- Provenance
- Completeness
- MarketEligibility

## Meter Attestation

Revenue-grade meter with calibration chain.
Secure Element or TPM-backed identity.
Gateway signing with hardware attestation.

## Example

```json
{
  "eventId": "evt_01HZ...",
  "sourceId": "meter_solar_01",
  "eventType": "Generation",
  "intervalStart": "2026-08-18T14:00:00Z",
  "intervalEnd": "2026-08-18T14:15:00Z",
  "value": 4.211,
  "unit": "kWh",
  "direction": "export",
  "sequence": 8421,
  "timestamp": "2026-08-18T14:15:00Z",
  "previousEventHash": "0x...",
  "signature": "0x..."
}
```

## Design Notes

- Meter events are source-local sequenced.
- Global order comes from Merkle batches.
- Raw meter data stays in object storage.
- Permanent layer stores commitments and proofs.