# PowerQED Architecture

## Core

PowerQED is built around three core systems:

- Energy Evidence Protocol
- Evidence Assurance Model
- Evidence Graph / Policy Engine

These are the product. Infrastructure is replaceable.

## Layers

### Applications

- 24/7 Carbon-Free Matching
- Verified Flexibility
- Workload Energy Attribution
- EV Fleet Charging
- ESG Audit

### Verification Engine

- Policy evaluation
- Claim generation
- Aggregation
- Optional ZK proofs

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

### Measurement Boundary

- Incoming sources
- Generation sources
- Storage
- Loads
- Topology version
- Signed by operator and verifier

### Evidence Assurance

Every source evaluated across:

- Identity
- Authentication
- Integrity
- Attestation
- Metrology
- Time
- Provenance
- Completeness
- MarketEligibility

### Trust / Attestation

Physical asset attestation:

- TPM 2.0
- Secure Element
- OEM PKI
- Meter certificate
- Gateway identity

Compute attestation:

- Intel TDX
- AMD SEV-SNP
- vTPM
- Workload identity
- Container digest

### Connectors

- SunSpec
- OCPP
- OpenEMS
- MQTT
- Vendor APIs

### Physical Assets

- Solar
- Wind
- Battery
- Grid
- Backup generator
- Data center load

## Data Flow

Physical event, signed event, evidence graph, policy evaluation, claim, certificate / settlement.

## Storage

- MS SQL: operational data, reference data, reports
- Object Storage: raw telemetry
- EigenDA: temporary evidence data
- Permanent Storage: commitments and final proofs

## Commitments

Source-local sequence with optional previous event hash.

15-minute batch, Merkle tree, batch manifest, signed root, DA / Ethereum anchor.

Evidence Graph builds on top.

## Compute

- Native deterministic compute
- Customer compute
- EigenCompute as backend

## Proof Engine

Pluggable proof backend.

- Groth16
- Plonk
- STARK
- Flock-class proofs

Flock-class proofs run on x86 Linux. Post-quantum proving already 3x faster on Mac, x86 ceiling still open.

Benchmarks on real PowerQED circuits.

## Proof Verification

Proof systems are validated by formal verification where available.

Hash-based SNARKs for post-quantum Ethereum are formally verified through Lean 4 via Yukon Research and Ethereum Foundation.

Ethereum Foundation and zkSecurity run a $1M proximity challenge to establish strong security bounds.

PowerQED adopts formally verified proof backends when production ready.

## Settlement

- Ethereum L1 / L2
- Traditional market systems

## Decentralized Verification

Optional decentralized verification network.

PowerQED AVS verifies evidence, attestation, policy execution, proof verification, dispute resolution.

EigenLayer as potential shared security for the verifier set.

## Abstractions

The system follows SOLID principles and Clean Architecture.

- DataAvailability
- ComputeBackend
- ProofEngine
- AttestationProvider
- SettlementAdapter

Every dependency is behind an interface. Implementations can be swapped without changing the Energy Evidence Protocol.

## Interface

C# Blazor for energy network map, documents, reports, SLA, chat, asset management.

MS SQL for operational data.

## Principle

Blockchain is a trust anchor, not a CRUD database.