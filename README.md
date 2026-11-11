# KubeKin Samples

Synthetic example Kubernetes manifests for testing
[KubeKin](https://urlcallapp.github.io/kubekin/)'s URL import
([source](https://github.com/urlcallapp/kubekin)). No real cluster data, no secrets.

**Sample picker UI (GitHub Pages):** https://urlcallapp.github.io/kubekin-samples/
- "Copy all raw links" copies every sample URL, ready to paste into KubeKin's URL field.
- Each sample has its own "Copy raw link" button.
- The list updates automatically when a `.yaml` file is added to `samples/`.

## Samples

Base raw URL: `https://raw.githubusercontent.com/urlcallapp/kubekin-samples/main/samples/`

| File | What it demonstrates |
| --- | --- |
| `01-web-app.yaml` | Small app: Deployment, Service, Ingress route, ConfigMap/Secret/PVC/SA references, HPA target |
| `02-microservices.yaml` | Two namespaces, cross-namespace traffic, NetworkPolicy, ResourceQuota, LimitRange |
| `03-stateful-database.yaml` | StatefulSet with headless Service and volumeClaimTemplates |
| `04-jobs-and-cron.yaml` | CronJob + Job with namespace RBAC (Role/RoleBinding) |
| `05-daemonset-cluster-rbac.yaml` | DaemonSet with ClusterRole/ClusterRoleBinding |
| `06-gateway-api.yaml` | Gateway API: Gateway + HTTPRoute routing to a Service |
| `07-custom-resource.yaml` | A CRD and a custom resource instance |
| `08-owner-references.yaml` | Explicit ownerReferences chain (Deployment → ReplicaSet → Pod): solid "owns" arrows |
| `09-large-map.yaml` | 55 resources: triggers the simplified >40-resource view |

Example raw link: <https://raw.githubusercontent.com/urlcallapp/kubekin-samples/main/samples/01-web-app.yaml>

## Negative tests

`negative-tests/` holds intentionally broken files for checking KubeKin's error handling.
They are excluded from "Copy all raw links" so a bulk import never fails unexpectedly.

| File | What it demonstrates |
| --- | --- |
| `syntax-error.yaml` | One valid + one broken document: red banner, partial map |
