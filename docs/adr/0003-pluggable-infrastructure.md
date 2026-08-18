# ADR 0003: Pluggable Infrastructure

## Status

Accepted

## Context

PowerQED needs data availability, compute, proof engine, attestation and settlement.

Specific technologies will evolve.

## Decision

Every infrastructure dependency is behind an interface.

DataAvailability, ComputeBackend, ProofEngine, AttestationProvider, SettlementAdapter are abstractions.

Current implementations: EigenDA, EigenCompute, Flock-class proofs, TPM/PSA/OEM PKI, Ethereum.

## Consequences

- The Energy Evidence Protocol is independent of infrastructure.
- The system follows SOLID and Clean Architecture.
- Each layer is testable by contract.

## Alternatives Considered

Tight coupling to Eigen: rejected. Would make the product dependent on one stack.