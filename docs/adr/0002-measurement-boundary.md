# ADR 0002: Measurement Boundary as Core Concept

## Status

Accepted

## Context

Signed data alone can be a lie through omission.

An operator can connect solar, wind and battery, but omit the gas generator.

## Decision

Every claim requires a signed Measurement Boundary.

Boundary completeness is verified before claim evaluation.

## Consequences

- Energy balance becomes a hard check.
- Omission attacks are detectable.
- Claim validity depends on boundary completeness.

## Alternatives Considered

Trust signed events without boundary: rejected. Does not protect against omission.