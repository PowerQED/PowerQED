# Evidence Assurance

Evidence Assurance evaluates every source across multiple dimensions.

A single Proof Grade is not enough. A device with strong attestation may have weak metrology. A certified meter may have weak identity.

## Dimensions

- Identity
- Authentication
- Integrity
- Attestation
- Metrology
- Time
- Provenance
- Completeness
- MarketEligibility

## Example

- Identity: A4
- Authentication: A5
- Integrity: A5
- Attestation: A4
- Metrology: A5
- Time: A4
- Provenance: A5
- Completeness: A3
- MarketEligibility: A2

## Derived Proof Grade

Derived Proof Grade is a UI label, not a strict hierarchy.

Different policies may derive different grades from the same assurance vector.

## Design Notes

- Assurance is evaluated per source and per event.
- Policies define required assurance levels.
- Evidence Package includes the full assurance vector.