# FastDiff 3

**Offline data comparison with bounded RAM and retained evidence.**

Choose VERIFY for an exact equality decision, LOCATE for the first difference in deterministic comparison order, or FULL for the complete difference report within your selected scope. Designed for Windows x64 and local comparison of migration exports, inventory snapshots and ledger states.

Supported workflows include checkpoint continuation, local distributed execution, read-only SQLite comparison, fixed-point finance and evidence replay. Distributed checkpoint continuation is qualified for controlled FULL runs with unchanged inputs and compatible settings; arbitrary power-loss recovery is outside that result.

The public qualification summary reports scoped functional checks and three targeted 40,000-row-per-input Reference/Automatic measurements. Those measurements compare internal execution profiles, not competing products, earlier FastDiff editions or the final production executable. They are individual observations, not a statistical performance guarantee.

FastDiff 3 is proprietary commercial software for private distribution. This repository provides documentation and presentation graphics, with no public application download. The qualified Windows build is unsigned; operating-system trust must be addressed separately.

## Contact the author

Discuss a private evaluation, demonstration or commercial license: [cxclrfx@proton.me](mailto:cxclrfx@proton.me). Include the product edition, intended use, input formats or corpus type, scale and operating environment. Start with a non-sensitive summary; do not send confidential datasets in an initial inquiry. Availability and terms must be confirmed by the author.

## Choose the FastDiff edition for your workflow

| Edition | Documented focus | Public availability |
| --- | --- | --- |
| [FastDiff v0.2.1](https://github.com/cxclrfx/FastDiff) | Read-only keyed comparison of already sorted tabular exports; published Windows measurements. | Product documentation and benchmark report; ask the author about commercial evaluation. |
| [FastDiff V2](https://github.com/cxclrfx/FastDiff-2) | Large unsorted exports, schema comparison, fixed-point totals and offline verification. | Documentation and synthetic examples; production binary delivery has outstanding qualification, signing/trust and licensing conditions. |
| [FastDiff 3](https://github.com/cxclrfx/FastDiff-3) | VERIFY, LOCATE and FULL, bounded RAM, supported checkpoint continuation and local distributed execution. | Windows x64; proprietary private distribution, no public application download. |

Each edition has its own scope and terms. Measurements and qualification results belong only to the edition and workload that produced them.

## Evidence and terms

See the [README](README.md) for source documentation, qualification scope and limitations. Existing license terms remain unchanged.

*Product overview edition: 2026-10-12. This is an editorial addition, not a new executable release or qualification run.*
