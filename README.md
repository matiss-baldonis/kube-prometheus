
# Add repository to argocd 
```  argocd repo add git@github.com:matiss-baldonis/kube-prometheus --ssh-private-key-path ~/.ssh/id_ed25519 ```

# Launch ArgoCD pipeline from manifests/setup/prometheus/application/prometheus
```  kubectl apply -f prometheus.yaml ```
 
# ArgoCD will launch deployment and deploy all neccessary kubernetes manifests in this repository. 
