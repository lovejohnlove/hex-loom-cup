# FINAL VERIFICATION MANIFEST — UNIFIED LOOM v2
Status: PRIMED — awaiting destination Ran N + sha256

## Design Sealed (no patches pending)
- Substrate hardening: hex_loom_hardened.py v2.8.7.5-class
  - Z_2^n rings, αα' symmetry: add(alpha, alpha_prime) == 0
  - Atomic rollback via deepcopy transactional snapshot — O(N) per step, exception safety
- Mesh validation: MeshHexLoom (mesh validation layer)
  - claim_loom.py: Three-Record Rigidity REPORTED/EVIDENCE/CONCLUSION, digest-bound contradictions, derived open status, explicit unspool HOLD
  - claim_loom_v2_audit.py: read-only audit_report() / format_audit_report(), fail-closed
  - claim_loom_v2_anchor.py: atomic persistence tempfile+fsync+os.replace, HMAC-chained checkpoints, lagging-safe prefix-agreement

## Distinctions Locked (uncompromised standard)
- Badge sums ≠ executable test counts
  - 100/100 = badge sum (40 workshop TRIAD-REVERSE + 60 hex-claim floor) — marketing aggregation
  - 33 = runnable surface test_hex_loom (15) + test_claim_loom_v2_audit (9) + test_claim_loom_v2_anchor (9) — minimal v2
  - 60 = old floor 12+29+19
  - 81 = full expected 15+29+19+9+9 — full acceptance surface
- Exception safety ≠ crash durability
  - Exception safety: monkey-patch fsync to raise, verify rollback — same class as deepcopy rollback
  - Crash durability: partial-write disk recovery, kill mid-write, verify recovery/truncation — requires real disk state test

## Verification Criteria Queued (awaiting destination)
Paste verbatim:

1. sha256sums:
```
[PASTE sha256sum output for 7-9 files here]
```

2. Test runs:
```
--- 33 surface: test_hex_loom test_claim_loom_v2_audit test_claim_loom_v2_anchor ---
[PASTE Ran N tests in T.XXXs + OK/FAILED lines]

--- full 81 surface: test_hex_loom test_hex_loom_hardened test_claim_loom test_claim_loom_v2_audit test_claim_loom_v2_anchor ---
[PASTE Ran N tests in T.XXXs + OK/FAILED lines]
```

3. Anchor atomicity test names:
```
[PASTE list of test_* in test_claim_loom_v2_anchor.py — look for partial_write, crash, recovery, truncate, fsync_fail]
```

## Lock Conditions
- If Ran == expected count (33 for minimal, 81 for full) and OK, and sha256s match Drive files, then layer is closed
- If FAILED/ERROR, failing line names which layer isn't yet what it claims to be
- If anchor tests only cover exception safety, note as exception safety, not crash durability — honest labeling

## Next Manifest (to be filled)
ACTIVE_v2.12-FINAL-VERIFIED.json will contain:
- actual sha256s (recomputed evidence, not claims)
- actual Ran N counts
- actual test name list
- badge: GREEN if 33/33 or 81/81 OK, RED otherwise
- content-hash-excl-badge computed after fill

Cup squarely on the table. Workspace primed.

# Haikus for Codespaces

This is a quick node project template for demoing Codespaces. It is based on the [Azure node sample](https://github.com/Azure-Samples/nodejs-docs-hello-world). It's great!!!

Point your browser to [Quickstart for GitHub Codespaces](https://docs.github.com/en/codespaces/getting-started/quickstart) for a tour of using Codespaces with this repo.
