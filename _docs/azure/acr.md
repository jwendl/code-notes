---
title: Azure Container Registry
category: Azure
order: 3
---
# Azure Container Registry

## Create a new Registry

``` bash
containername="example"
subscriptionid=`az account show | jq -r '.id'`
az acr create --name $containername --resource-group ContainerSandbox -location centralus --sku Basic
az ad sp create-for-rbac --scopes /subscriptions/$subscriptionid/resourcegroups/ContainerSandbox/providers/Microsoft.ContainerRegistry/registries/JwContainerRegistry --role Owner --password "P@SSW0rd!"
```
