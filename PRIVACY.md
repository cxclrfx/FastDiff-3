# Privacy

FastDiff 3 supports local data comparison and offline replay. These operations do not require uploading datasets to an external service. The supported distributed option is local; this documentation does not describe or promise a hosted processing service.

Comparison evidence remains in local storage under the operator's control unless the operator chooses to share or transfer it.

## Data under the operator's control

Comparison outputs, checkpoints and retained evidence can contain input data, values that differ and operational information. Treat them with the same confidentiality as the original datasets. Do not assume that a report or evidence bundle is anonymous or redacted.

| Material | Operator responsibility |
| --- | --- |
| Input data | Use authorized, appropriately scoped datasets and stable snapshots. |
| Comparison reports | Limit access according to the sensitivity of the included values. |
| Checkpoints and evidence | Keep access restricted; retain them only as required for continuation or verification. |
| Copies and backups | Apply the same protection and retention policy as for the originals. |
| Entitlements | Keep customer licensing information separate from shared documentation and reports. |

## Sharing and retention

Share only the minimum information needed for review. Inspect data and evidence before sending them to another party. For support or issue reporting, prefer a small synthetic example with sensitive values removed. Never post customer datasets or entitlement files in repository discussions.

Operators control storage location, access, backups and retention. Deletion and backup handling should follow the operator's own data policy. Local operation does not by itself establish regulatory compliance or secure deletion guarantees.

## Repository boundary

This repository contains product documentation and static presentation graphics. It contains no application source code, executable, customer dataset, entitlement, key material or internal development archive. The capability illustrations contain only the published product facts and measurements.
