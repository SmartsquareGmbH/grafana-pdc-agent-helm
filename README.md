# Grafana pdc-agent Helm

A Helm chart for Grafana's [pdc-agent](https://github.com/grafana/pdc-agent).

If you know what your doing just start using this chart from our OCI-registry:
### `oci://ghcr.io/smartsquaregmbh/helm/grafana-pdc-agent`

# Usage

This chart is stored in a OCI-based registry. Please either use Helm v3.8.0+ or consult the [Helm documentation](https://helm.sh/docs/topics/registries) for how to use OCI-registries in older versions.

Make sure you are authenticated against ghcr.io via a [github-pat](https://github.com/settings/tokens) with scope `package:read` using (this will prompt username & token):

```
$ helm registry login ghcr.io
```

Helm currently does not support adding OCI-registries as Helm-repositories. So use this chart like this:

```
$ helm install <release> oci://ghcr.io/smartsquaregmbh/helm/grafana-pdc-agent --version 0.1.0 -f path/to/values.yaml
```

Minimal required values.yaml (for all possible values see [values.yaml](./values.yaml)):

```yaml
secret:
  values:
    token: "<YOUR-GRAFANA-TOKEN>"
    hostedgrafanaid: "<YOUR-HOSTED-GRAFANA-ID>"
    cluster: "<YOUR-GRAFANA-CLUSTER>"
```

# Chart compability

This chart is confirmed to work with grafana-pdc-versions `v0.0.30` to `v0.0.37` but every version prior should work too.

