# Qualification

This is the public-facing engineering summary for FastDiff 3. It reports confirmed product behavior and measurements without implementation details. Detailed runtime evidence is retained separately and is not part of this repository.

## Targeted comparison measurements

A 40,000-row-per-input baseline was used for targeted Reference/Automatic observations. The unequal-count case contains an additional row on one side. Final results, events and RID agreed between the profiles in the three reported cases.

| Scenario | Mode | Reference | Automatic | Reported speedup |
| --- | --- | ---: | ---: | ---: |
| Identical inputs | VERIFY | 9.51 s | 1.36 s | 6.99× |
| Early mismatch | VERIFY | 9.22 s | 2.00 s | 4.62× |
| Unequal row count | LOCATE | 10.10 s | 2.84 s | 3.55× |

![Targeted wall-time observations](assets/performance-comparison.svg)

Logical I/O was approximately **1,322 MiB** for Reference and **262–374 MiB** for Automatic across these cases. The interval is a range across cases, not a confidence interval or a per-case mapping.

![Reported logical I/O range](assets/io-comparison.svg)

### Measurement scope

- These are individual targeted observations, not averages, statistical confidence bounds or best-of-many marketing selections.
- The comparison is between Reference and Automatic execution on the stated fixture, not between product generations.
- Timings include initial data preparation and result output; fixture generation, process startup and guard setup are outside the recorded interval.
- Operating-system caches were not explicitly cleared. Logical I/O includes cached transfers and must not be interpreted as physical disk traffic.
- Times and speedups are rounded as reported. Computing a ratio from the rounded display times can give a slightly different last digit.
- The measurements precede the final Windows production smoke. They are not timing measurements of that final executable.
- Performance varies with data, settings and the execution environment. These observations do not establish a universal performance or distributed-speedup guarantee.

## Checkpoint / Resume

| Property | Confirmed result |
| --- | ---: |
| Canonical rows reused | 40,000 |
| Committed comparison pairs reused | 10,000 |
| Payload comparisons avoided | 9,999 |
| Final result preserved | PASS |
| Final events preserved | PASS |
| Result identifier (RID) preserved | PASS |

These reuse counts belong to the standalone checkpoint/resume qualification. They do not describe the separate distributed checkpoint/resume case. RID is the product's result identifier; equality here concerns the same comparison task and data.

## Distributed execution

| Check | Result |
| --- | --- |
| FULL with execution Off/On | PASS — equal final result, events and RID. |
| LOCATE with out-of-order worker completion | PASS — first mismatch in the defined order, not merely the first response received. |
| Worker failure and retry | PASS — final result preserved after retry. |
| Duplicate completion handling | PASS — no duplicate counting. |
| Altered worker receipt | PASS — rejected. |
| Gap in distributed comparison coverage | PASS — rejected. |
| Recursive repartition | PASS — result preserved in the tested case. |
| VERIFY cancellation | PASS. |

These are behavior checks for the supported local distributed execution option. They do not qualify an external network service or every failure scenario.

## Final integration

**23 product functions have PASS qualification sources.** This combines existing scoped qualification with the final integration checks; it is not a claim that all functions and combinations were re-tested in one new global matrix.

| Integration check | Result |
| --- | --- |
| Adaptive Planner | PASS — verified result consistency in the stated integration cases. |
| Distributed + Checkpoint/Resume | PASS — FULL continuation preserved final result, events and RID. |

Distributed checkpoint/resume is qualified for a controlled stop and continuation of FULL. Unchanged inputs and compatible settings are required. Arbitrary crash and power-loss recovery are outside this result.

## Final Windows production smoke

The final private Windows production executable passed the following short smoke checks. This is functional smoke evidence, not a performance campaign or independent certification.

| Function | Status |
| --- | --- |
| VERIFY | PASS |
| LOCATE | PASS |
| FULL | PASS |
| Reference Execution | PASS |
| Automatic Execution | PASS |
| Adaptive Planner | PASS |
| Checkpoint / Resume | PASS |
| Distributed Execution | PASS |
| Distributed + Checkpoint/Resume | PASS |
| SQLite | PASS |
| Fixed-point Finance | PASS |
| Licensing | PASS |
| Replay | PASS |
| Memory Guard | PASS |

The qualified Windows build is unsigned. Application licensing success does not establish operating-system code-signing trust. Executables and entitlement files are delivered privately, outside this documentation repository.

## Reading PASS correctly

PASS records the stated behavior for the specified qualification case. It does not certify source-data truth, all workloads, all combinations, unrestricted scale, remote-node deployment or recovery from every interruption. No implementation or internal runtime archive is published here.
