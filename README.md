# kube-vip Helm Chart

This Helm chart deploys [kube-vip](https://kube-vip.io/) for Kubernetes control plane high availability and load balancing.

## Prerequisites

- Helm 3.x
- Kubernetes cluster (control-plane nodes labeled appropriately)

## Installation

1. Clone or copy the chart to your local machine.
2. Customize `values.yaml` as needed (interface, IP, image tags, etc.).
3. Install the chart:

   ```sh
   helm install kube-vip ./kube-vip-helm-chart --namespace kube-system
   ```

## Configuration

Edit `values.yaml` to set:

- `vipInterface`: Network interface name on control-plane nodes
- `vipAddress`: VIP address for Kubernetes API
- `cidrGlobal`: Global CIDR for kube-vip
- `image` and `cloudController.image`: Image repositories and tags

## Files

- `kube-vip-helm-chart/Chart.yaml`: Helm chart metadata
- `kube-vip-helm-chart/values.yaml`: Default values
- `kube-vip-helm-chart/templates/`: Kubernetes manifests (ConfigMap, DaemonSet, cloud controller)

## Uninstall

```sh
helm uninstall kube-vip --namespace kube-system
```

## References

- [kube-vip documentation](https://kube-vip.io/)
