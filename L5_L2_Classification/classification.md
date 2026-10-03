# L5 Narrow / L2 General Classification — api-oss-examples
**Platform:** Anticloud | **PAX:** 27B | **IP:** USPTO pending 2026, Anticloud FZ LLE
**Domain:** Runnable example collection for Anticloud API — all examples are AIOSS-verified

## L5 Narrow
api-oss-examples specializes in runnable example collection for anticloud api — all examples are aioss-verified within the Anticloud sovereign deployment boundary. All operations stay local — no cloud services, no external APIs, no data exfiltration. The narrow scope ensures deterministic, auditable behavior that PAX 27B can reason about precisely.

## L2 General
L2 General means api-oss-examples is available to all 9 Anticloud tiers without per-tier configuration. The same API serves hospital, defense, robotics, and research deployments.

## PAX Integration
PAX 27B is used to generate new examples from natural language descriptions and verify existing examples remain correct against the current codebase.

## AIOSS Audit Relevance
Every example execution (example ID + expected output hash + actual output hash + pass/fail) is AIOSS-chained: H_n = SHA3-256(H_{n-1} || entry_hash_n || timestamp_n).
Tamper-evident, offline-verifiable, zero cloud dependency.

## Regulatory / Compliance
ISO/IEC 12207 (software lifecycle), NIST SSDF
