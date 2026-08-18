# Data Flow

## Overview

Physical energy events become policy-bound claims.

## Flow

1. INGEST
   Meter or device sends signed event.

2. AUTHENTICATE
   Signature verified. Source identity checked. Assurance evaluated.

3. BOUNDARY
   Measurement Boundary completeness verified.

4. PROVENANCE
   Event added to Evidence Graph.

5. POLICY
   Policy engine evaluates events against policy version.

6. CLAIM
   Claim generated with matched generation and assurance profile.

7. COMMIT
   Merkle batch committed to DA and Ethereum anchor.

8. VERIFY
   External party verifies claim without raw telemetry.

## Example

Grid meter, solar meter, wind meter, BESS meter, backup generator.

Signed events. Boundary complete. Policy CFE24x7.v1.

Claim: DC-17, 14:00–15:00, consumption 10.842 MWh, matched generation 10.842 MWh, CFE 100%.

Verification Receipt with proof root and Ethereum anchor.

## Design Notes

Each step is signed and hashable.

Raw telemetry stays in object storage.

Permanent layer contains commitments and proofs.