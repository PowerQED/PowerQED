# Measurement Boundary

Measurement Boundary is the signed statement of all energy sources and loads at a site.

Without a complete boundary, perfectly signed data can still be a lie through omission.

## Structure

- Boundary ID
- Site ID
- Topology Version
- Valid From
- Signed By
- Signed At

## Components

### Incoming

- Grid meter
- External supply points

### Generation

- Solar meter
- Wind meter
- Backup generator meter

### Storage

- BESS meter
- Charge and discharge metering

### Loads

- IT load
- Cooling
- Auxiliary
- Losses

## Completeness Check

GridImport + LocalGeneration + StorageDischarge - StorageCharge ≈ ITLoad + Cooling + Auxiliary + Losses.

If the operator omits a generator, energy balance fails.

## Status

A claim can be evaluated only when boundary completeness passes.

## Design Notes

- Boundary is versioned.
- Changes require new version and signature.
- Signed by operator and independent verifier.
- Boundary is part of every claim.