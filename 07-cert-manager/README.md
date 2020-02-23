# 7. cert-manager

* Install and configure cert-manager for AWS Route53

```
kubectl apply --validate=false -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.13/deploy/manifests/00-crds.yaml
```

```
helm repo add jetstack https://charts.jetstack.io
```

```
kubectl create namespace cert-manager
```

```
helm upgrade --install --namespace cert-manager --version v0.13.1 cert-manager jetstack/cert-manager
```

* Add AWS Secret Key to `route53/credentials-secret.yaml`

* Add AWS Access Key to `route53/clusterissuer.yaml`

* Create ClusterIssuer

```
kubectl apply -f route53/credentials-secret.yaml
```

```
kubectl apply -f route53/clusterissuer.yaml
```

* Change hostnames in `certificate.yaml`
* Create wildcard certificate

```
kubectl apply -f route53/certificate.yaml
```
