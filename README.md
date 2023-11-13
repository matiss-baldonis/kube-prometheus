
## Add repository to argocd
### Add this repositories URL and git key to ArgoCD
```  argocd repo add git@github.com:matiss-baldonis/kube-prometheus --ssh-private-key-path ~/.ssh/id_ed25519 ```

### Launch ArgoCD pipeline from manifests/setup/prometheus/application/prometheus
### by deploying a Kubernetes prometheus instance. 
```  kubectl apply -f prometheus.yaml ```
### ArgoCD will launch deployment and deploy all neccessary kubernetes manifests in this repository.

### Forward ports to make Prometheus available in browser
```
kubectl get pods -n monitoring 
kubectl port-forward <name of pod returned by previous command> 8080:9090 -n monitoring
```

### Open Prometheus in browser:

``` localhost:8080 ```

### TODO:
```- Implement ingress so that Prometheus can be accessed via DNS name that points to k8s service```
