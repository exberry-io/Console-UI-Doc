# Containers

## Workspace details

Display workspace attributes in 4 columns

| Column 1  | Column 2        | Column 3       | Column 4           |
| --------- | --------------- | -------------- | ------------------ |
| Cluster   | Deployment type | Workspace type | Created date       |
| Namespace | Branch          |                | Last modified date |

## Resource details

Display workspace attributes in 4 columns

<table><thead><tr><th width="170">Column 1</th><th width="153">Column 2</th><th width="254">Column 3</th><th>Column 4</th></tr></thead><tbody><tr><td>Type</td><td>AWS region</td><td>Internal Ingress route suffix</td><td>Cluster name</td></tr><tr><td>Ownership type</td><td>AWS account</td><td>External Ingress route suffix</td><td>Namespace</td></tr><tr><td>First created</td><td>AWS bucket</td><td>Vault name</td><td>DNS suffix</td></tr><tr><td>Last modified</td><td>Certificate Arn</td><td>Resource type</td><td>Tolerations</td></tr><tr><td></td><td>Transit Gw Arn</td><td>Resource name</td><td>Default toleration</td></tr><tr><td></td><td>Atlas account</td><td>Resource version</td><td>KMS key alias</td></tr></tbody></table>

For attributes without value, show the label as disabled.

For Tolerations field, display the list of values separated by comma.
