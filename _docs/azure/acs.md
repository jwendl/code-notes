---
title: Azure Container Service
permalink: /docs/acs/
---

## Creating with Azure CLI
``` bash
az group create --name ContainerSandbox --location centralus
az acs create --orchestrator-type=kubernetes --resource-group ContainerSandbox --name=JwContainerSandbox --dns-prefix=jwcontainersandbox --generate-ssh-keys
sudo az acs kubernetes install-cli
```

## Kube CTL
``` bash
kubectl
az acs kubernetes get-credentials --resource-group ContainerSandbox --name JwContainerSandbox
kubectl get nodes
kubectl run nginx --image nginx
kubectl get nodesca
kubectl get pods
kubectl expose deployments nginx --port=80 --type=LoadBalancer
watch 'kubectl get svc'
```
