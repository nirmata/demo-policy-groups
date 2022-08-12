# Demo Policy Group PCI

A Kyverno policy group that enforces:
1. Namespaces have a `data-classification` label with values `PCI` or `OTHER`.
2. Namespaces and workloads are mutated with a label `kyverno.io/createdBy` with the value set to the user that creates the resource.
3. Disallows use of the `default` namespace.
4. Pods are mutated with a `nodeSelector` with the label `storage: encrypted-ssd`.
5. Requires that pods drop all Linux capabilities.

## Usage

1. Install Kyverno
2. Install this policy group
3. Run the [namespaces.yaml](/pci/resources/namespaces.yaml)
4. Try creating a [bad deployment](/pci/resources/bad-deployment.yaml)
5. Try creating a [good deployment](/pci/resources/good-deployment.yaml)
