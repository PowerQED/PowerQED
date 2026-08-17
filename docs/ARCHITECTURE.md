# PowerQED Architecture

## Layers

### Applications

- 24/7 Carbon-Free Matching
- Verified Flexibility
- EV Fleet Charging
- ESG Audit

### Verification Engine

- Policies
- Claims
- ZK Proofs
- Aggregation

### Evidence Graph

- Provenance
- Ownership
- Lineage
- Replay

### Energy Evidence Protocol

- Event
- Identity
- Timestamp
- Signatures

### Trust / Attestation

- TPM 2.0
- Intel TDX
- ARM PSA
- OEM PKI
- Secure Element

### Connectors

- SunSpec
- OCPP
- OpenEMS
- MQTT
- Vendor APIs

### Physical Assets

- Solar
- Battery
- Wind
- Data Center Load

## Storage

- MS SQL: operational data, reference data, reports
- Object Storage: raw telemetry
- EigenDA: temporary evidence data
- Permanent Storage: commitments and final proofs

## Compute

- Native deterministic compute
- Customer compute
- EigenCompute as backend

## Settlement

- Ethereum L1 / L2
- Traditional market systems

## Infrastructure

PowerQED Network is built on Eigen stack.

- EigenDA for temporary evidence data
- EigenLayer for shared security
- EigenCompute as backend for heavy compute

The system stays pluggable.

- Data Availability abstraction
- Compute abstraction
- Proof Engine abstraction: Groth16, Plonk, STARK, Flock

## Connectors Strategy

PowerQED connects through standard industrial protocols.

Each connector has a Trust Profile.

PowerQED shows the origin of a fact and the trust level of every link in the chain.

## Interface

C# Blazor for energy network map, documents, reports, SLA, chat, asset management.

MS SQL for operational data.

## Principle

Blockchain is a trust anchor, not a CRUD database.