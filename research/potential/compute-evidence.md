# Compute Evidence

## Idea

Attribute energy consumption to specific AI workloads.

## Problem

Data center meter does not know which workload used the energy.

## How It Works

1. Workload identity captured.
2. GPU cluster and node allocation recorded.
3. PDU telemetry signed.
4. Facility allocation model applied.
5. Energy attributed per workload.
6. CFE matching per workload.

## Technical Dependencies

- Compute attestation: TDX, SEV-SNP, vTPM
- Container digest
- PDU telemetry
- Energy Evidence Protocol

## Why Later

This is a second evidence domain beyond physical energy.

Requires data center infrastructure access.