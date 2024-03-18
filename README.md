# GitHub Action: Flux kustomize kubeconform

Hyper specific GitHub action to validate Flux config from Kustomizations!

## Quickstart

```yaml
name: "util: <app name> Kustomize validate"
on:
  pull_request:
    types:
      - synchronize
      - opened
    paths:
      - .github/workflows/flux-<file-name>.yaml
      - path/to/deployment/or/config
jobs:
  validate:
    name: Kubeconform
    runs-on: ubuntu-latest
    timeout-minutes: 5
    steps:
      - name: Checkout Repo
        uses: actions/checkout@v4
      - name: Kubeconform
        uses: userbradley/action-flux-kustomize-kubeconform@v1.0.0
        with:
          directory: <path to deployment or config>
```

## Inputs

| Name                 | Description                                                                 | Required | Default Value |
|----------------------|-----------------------------------------------------------------------------|----------|---------------|
| `kubeconformVersion` | Version of Kubeconform to download                                          | `false`  | `v0.6.4`      |
| `kustomizeVersion`   | Version of Kustomize to download                                            | `false`  | `v5.0.3`      |
| `directory`          | Name of the directory that contains the kustomization.yaml file to validate | `true`   | `Null`        |

---

Built by [Bradley](https://bradley.breadnet.co.uk/?utm_source=github&utm_medium=action-flux-kustomize-kubeconform&utm_campaign=built%20by), with Love ❤️
