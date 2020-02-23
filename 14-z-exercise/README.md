# Exercise

* Deploy the Helm chart bitnami/ghost (https://hub.helm.sh/charts/bitnami/ghost)
* Configure it so that it uses the Ingress controller, the Certificate and the MySQL database created before
* Installation would look like:
```
helm upgrade --install ghost bitnami/ghost -f values.yaml
```

Bonus:

* Inject LinkerD Proxies into the Ghost Deployment
