# EV Fleet Expansion

## Idea

Full EV fleet charging provenance across multiple sites.

## Problem

Fleet operators need proof of renewable charging.

## How It Works

1. Charger connects via OCPP.
2. Meter records energy per session.
3. Evidence links session to renewable generation.
4. Fleet receives charging provenance report.

## Technical Dependencies

- OCPP connector
- Meter identity
- Evidence Graph
- Renewable matching policy

## Why Later

Requires OCPP integration at scale and fleet operator onboarding.