
## Add repository to argocd
### Add this repositories URL and git key to ArgoCD
```  argocd repo add git@github.com:matiss-baldonis/kube-prometheus --ssh-private-key-path ~/.ssh/id_ed25519 ```

## Launch ArgoCD pipeline from manifests/setup/prometheus/application/prometheus
### Will deploy a prometheus instance. 
```  kubectl apply -f prometheus.yaml ```
### Forward ports to make Prometheus available in browser
```
kubectl get pods -n monitoring 
kubectl port-forward <name of pod returned by previous command> 8080:9090 -n monitoring
```
 
## ArgoCD will launch deployment and deploy all neccessary kubernetes manifests in this repository. 
