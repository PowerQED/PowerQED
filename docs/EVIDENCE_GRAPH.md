# Evidence Graph

Evidence Graph is a verifiable knowledge graph of physical energy.

It connects assets, events, claims and certificates.

## Nodes

- AI Job
- GPU Cluster
- Facility Load
- Meter
- Energy Interval
- Solar Generation
- Wind Generation
- Granular Certificate

## Edges

Every edge has:

- Subject
- Predicate
- Object
- Valid From
- Valid Until
- Issuer
- Policy
- Evidence Hash
- Signature
- Proof

## Example

AI Job executed-on GPU Cluster powered-by Facility Load measured-by Meter included-in Energy Interval matched-with Wind Generation attributes-issued-as Granular Certificate retired-for AI Job.

## Design Notes

- Graph is append-only.
- Each edge is independently verifiable.
- Graph supports replay and audit.
- Graph is the foundation for claims and certificates.