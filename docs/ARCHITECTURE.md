# PowerQED Architecture

## Core

PowerQED is built around three core systems:

- Energy Evidence Protocol
- Evidence Assurance Model
- Evidence Graph / Policy Engine

These are the product. Infrastructure is replaceable.

## Backend & Frontend

- C# Blazor Server / WebAssembly — single stack.
- ASP.NET Core — REST API, OpenAPI, webhooks.
- Entity Framework Core + MS SQL Server — operational data, analytics.
- FluentValidation — request and domain validation.
- MediatR + CQRS — command and query separation.
- SignalR — real-time updates.
- RabbitMQ — message bus for telemetry and event processing.
- Redis — hot cache and pub/sub.
- Seq — structured logging and tracing.

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

PowerQED uses different storage layers for different purposes.

### Redis

Purpose: speed and real-time.

Use cases:

- Hot cache for active assets and boundaries
- Pub/Sub for meter events and alerts
- Rate limiting for API
- Job queues for event processing

Redis is an operational cache. It is not a system of record.

### MS SQL

Purpose: system of record.

Use cases:

- Assets, boundaries, policies, claims
- Reports and analytics
- Reference data

MS SQL stores current state and business data.

### Object Storage

Purpose: raw telemetry.

Use cases:

- Raw meter readings
- Historical sensor data

Object storage keeps raw data with retention policies.

### EigenDA

Purpose: temporary evidence availability.

Use cases:

- Signed meter events
- Hash chains
- Temporary evidence before aggregation

EigenDA provides short-term verifiable availability. It is not permanent storage.

### Permanent Storage

Purpose: permanent evidence.

Use cases:

- Final Evidence Packages
- Proof roots
- Audit records

Permanent storage preserves what must survive for years.

### Principle

Redis speeds up operations. MS SQL records state. Object storage keeps raw data. EigenDA proves availability. Permanent storage preserves truth.

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

### Verification Backends

Pluggable proof verification services.

- Native verifier — direct verification for low volume or local checks.
- Aligned Proof Aggregation — potential backend for cheap ZK verification at scale. Aggregates thousands of proofs into one, reducing L1 gas cost by 10-100x. Verification in milliseconds with cents-level fees. Security backed by EigenLayer validator pool.
- EigenLayer — optional decentralized verification through AVS.

## Settlement

- Ethereum L1 / L2
- Traditional market systems

## Decentralized Verification

Optional decentralized verification network.

PowerQED AVS verifies evidence, attestation, policy execution, proof verification, dispute resolution.

EigenLayer as potential shared security for the verifier set.

## Observability

- Seq — structured logging.
- Correlation ID — end-to-end tracing across all async flows.
- Grafana — dashboards and metrics.
- Every evidence event traceable from ingest to Arweave.

Data is not lost. Every packet can be traced in seconds.

## AI-Friendly Design

PowerQED is AI-ready.

Semantic tags on all entities. OpenAPI documented API. Webhooks for external agents.

See [AI_FRIENDLY.md](AI_FRIENDLY.md).

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