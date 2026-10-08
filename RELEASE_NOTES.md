# Release notes

## FastDiff 3.0.0

FastDiff 3.0.0 delivers exact, deterministic data reconciliation for Windows x64, with bounded memory and evidence-preserving verification. The application is proprietary software for private commercial distribution.

### Product capabilities

| Capability | Available in 3.0.0 |
| --- | --- |
| VERIFY / LOCATE / FULL | Exact equality decisions, the first difference in the defined order, and complete difference reports. |
| Deterministic execution | Consistent results for the same inputs and comparison settings in the qualified cases. |
| Bounded RAM | Explicit memory limits for large local comparisons. |
| Local / offline | Comparison and replay without an external processing service. |
| Reference / Automatic | Selectable execution profiles with verified result agreement. |
| Adaptive Planner | An optional execution setting with qualified result consistency. |
| Checkpoint / Resume | Continue supported comparisons from retained progress with compatible settings and unchanged inputs. |
| Distributed Execution | Local distributed comparison with verified result consistency. |
| Distributed continuation | Controlled stop and resume for distributed FULL comparisons. |
| SQLite | Read-only comparison of supported SQLite data. |
| Fixed-point Finance | Exact monetary comparisons and totals at the selected precision; no currency conversion. |
| Evidence / Replay | Retain evidence and verify the recorded comparison result. |
| Fail-close | Reject invalid or incompatible operations instead of accepting a successful verified result. |

### Verified qualification results

| Area | Recorded result |
| --- | --- |
| Targeted performance | Reference/Automatic speedups of 6.99×, 4.62× and 3.55× in the three documented comparison cases. |
| Logical I/O | Approximately 1,322 MiB for Reference and 262–374 MiB for Automatic across those cases. |
| Checkpoint / Resume | 40,000 canonical rows and 10,000 committed pairs reused; 9,999 payload comparisons avoided; final result, events and RID preserved. |
| Distributed behavior | FULL equivalence, canonical-first LOCATE, worker retry, duplicate handling, rejection checks, recursive repartition and VERIFY cancellation passed. |
| Final integration | 23 product functions have PASS sources; Adaptive Planner and Distributed + Checkpoint/Resume passed their scoped integration checks. |
| Final Windows production smoke | PASS for all 14 functions listed in the [qualification summary](QUALIFICATION.md#final-windows-production-smoke). |

Performance observations and functional PASS results are separate evidence sets. The recorded timings precede the final production smoke and are not timings of that executable. See [measurement scope](QUALIFICATION.md#measurement-scope) for conditions and interpretation.

### Delivery status

| Item | Status |
| --- | --- |
| Product version | 3.0.0 |
| Qualified platform | Windows x64 |
| Distribution | Private commercial delivery |
| Windows build signing | Unsigned private build |
| This repository | Product documentation and three static graphics |
| Application download / GitHub Release | Not provided here |

This documentation package contains no application implementation, executable or customer entitlement. Usage and redistribution remain subject to the proprietary [LICENSE](LICENSE) and [NOTICE](NOTICE).
