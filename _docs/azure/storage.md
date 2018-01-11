---
title: Azure Storage
category: Azure
order: 4
---

## List all Blobs from Azure Storage via Azure CLI

``` bash
az storage blob list --container-name raw --account-name account-name --sas-token "?sv=...="
```

> For account-name use the name of the account or rather the part before .blob.core.windows.net

