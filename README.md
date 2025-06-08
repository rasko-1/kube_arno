# kube-arno

This repository contains a Bash script plugin for kubectl that allows you to quickly get resource usage statistics (CPU and memory) for pods or nodes in a selected Kubernetes namespace.

## Usage

1. Copy the `kubectl-arno` script to a directory in your `$PATH` (for example, `/usr/local/bin`) and make it executable:
   ```bash
   sudo chmod +x scripts/kubectl-arno
   sudo cp scripts/kubectl-arno /usr/local/bin/
   ```

2. Use it as a kubectl plugin:
   ```sh
   kubectl arno pod <namespace>
   kubectl arno node <namespace>
   ```

> Metrics Server must be installed and configured in your cluster for this plugin to work.

## Example

```sh
kubectl arno pod test-ns
```

Output:
```
Resource,Namespace,Name,CPU,Memory
pod,test-ns,nginx-...,2m,10Mi
...
```