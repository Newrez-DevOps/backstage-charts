# Backstage Helm Chart

> NewRez Chart Adoption Notes: This repo is forked from the [official backstage chart repo](https://github.com/backstage/charts). We added mkdocs container to the deployment so that the mkdocs container resides in the same pod as the backstage container, allowing us to set generator to `local` instead of `docker` to avoid DID situation. The updated chart is packaged and pushed to JFrog Artifactory:
```bash
cd charts/backstage
helm dependency update
helm package .
curl -uadmin:cmVmdGtuOjAxOjE3MTkwMTQyNzE6clZLclVTbmY0YTRzNWlUaHhjWjVZQWZWYnZz -T ./backstage-1.1.2.tgz "https://artifactory.awsk8snonprod.newrez.cloud/artifactory/devops-dev-helm/backstage-1.1.2.tgz"
```
> Note: Below are official Backstage chart README contents.

[Backstage](https://backstage.io) is an open platform for building developer portals. Powered by a centralized software catalog, Backstage restores order to your microservices and infrastructure and enables your product teams to ship high-quality code quickly — without compromising autonomy.

Backstage unifies all your infrastructure tooling, services, and documentation to create a streamlined development environment from end to end.

> Disclaimer: This Helm chart deploys a pre-packaged container image which contains a vanilla Backstage instance for demo purposes. This image is probably not suitable for use in production. For further customization of the Backstage instance (plugin installation, UI changes, etc.) please create your own custom instance and container image. For details please consult the [Backstage documentation](https://backstage.io/docs)

## Scope

This chart focuses on providing users the same experience and functionality no matter what flavor of Kubernetes they use. This chart will support only patterns that are either customary for all Kubernetes flavors, are commonly used in the Bitnami charts ecosystem, and recognized as Backstage official patterns.

We welcome other, more specialized, charts to use this cannonical chart as a direct dependency, expanding the feature set further, beyond this scope.

A list of derived charts:
- OpenShift specialized chart: [Janus Backstage Helm chart](https://github.com/janus-idp/helm-backstage/tree/main/charts/backstage)

## Usage

Charts are available in the following formats:

* [Chart Repository](https://helm.sh/docs/topics/chart_repository/)
* [OCI Artifacts](https://helm.sh/docs/topics/registries/)

### Installing from the Chart Repository

The following command can be used to add the chart repository:

```console
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add backstage https://backstage.github.io/charts
```

Once the chart has been added, install one of the available charts:

```console
helm upgrade -i <release_name> backstage/backstage
```

### Installing from an OCI Registry

Charts are also available in OCI format. The list of available charts can be found [here](https://github.com/orgs/backstage/packages?repo_name=charts).

Install one of the available charts:

```shell
helm upgrade -i <release_name> oci://ghcr.io/backstage/charts/backstage --version=<version>
```

## Backstage Chart

More information can be found by inspecting the [backstage chart](charts/backstage).
