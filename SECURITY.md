# Security

FastDiff 3 is proprietary software for private commercial distribution. This repository contains documentation, not an application download.

## Operational safeguards

| Area | Guidance |
| --- | --- |
| Application delivery | Obtain the executable and entitlement through an authorized private delivery channel. |
| File integrity | Compare supplied checksums against an independently trusted reference before using a delivered package. |
| Evidence | Keep the full evidence set and its trusted integrity reference; use replay to verify the recorded comparison. |
| Input stability | Use stable data snapshots for comparisons and retain unchanged inputs for checkpoint continuation. |
| Access | Protect inputs, outputs and checkpoints with appropriate operating-system permissions. |
| Resource limits | Set a suitable memory budget and provide enough local storage for the task. |

## Verified behavior

The published qualification includes fail-close behavior, altered-receipt rejection, coverage-gap rejection, retry without duplicate counting, checkpoint continuation and replay. See [QUALIFICATION.md](QUALIFICATION.md) for exact scope. A rejected or incomplete operation must not be treated as a successful verified comparison.

Hash agreement establishes byte integrity. It does not establish the truth of input data or independently certify the business meaning of a result. Replay verifies a recorded comparison within the supported product contract.

## Signing and licensing

The qualified private Windows build is **unsigned**. Application entitlement validation is separate from operating-system code signing. Do not interpret a licensing PASS as Authenticode verification, and do not disable operating-system protection to run an untrusted file.

## Report issues privately

Use the private support channel established with the supplier. Do not disclose customer data, entitlement files, sensitive evidence or security details in public issues. Include the product version, observed behavior and a minimal synthetic reproduction when possible. A successful local check is not independent security certification.

## Documentation checksums

`SHA256SUMS.txt` lists relative filenames and SHA-256 values for every documentation file and graphic except the checksum list itself. Verify the list against a trusted copy. Changes to the documentation require regenerated checksums; this list is not a signature and does not cover privately delivered executables.
