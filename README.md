# istio-sync-operator

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```console
helm repo add istio-sync-operator https://networkcat89.github.io/istio-sync-operator/charts
helm install istio-sync-operator istio-sync-operator/istio-sync-operator
```

## Example
[Istio](https://istio.io) Virtual Services, Ingresses, Services, [Cert-manager](https://cert-manager.io/) must be 
installed before working with the operator
Please refer to Istio's docs [documentation](https://istio.io/latest/docs/) 
and to Cert-manager's docs [documentation](https://cert-manager.io/docs/getting-started/) to get started

Let's create an application with the domain name example.com

```console
kubectl apply -f example-custom-resource.yaml
```

Then the following resources will be created:
Istio HTTPS gateway: https://example.com
Istio HTTPS-WWW gateway with redirect to non-WWW: https://www.example.com
Istio HTTP-WWW-non-WWW gateway with redirect to HTTPS: http://www.example.com http://example.com
SSL Certificate
