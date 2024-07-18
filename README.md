# aksghautodeploy


## Create AKS cluster 

```bash
az group create --name aksghrg --location eastus2
az aks create --resource-group aksghrg --name akscluster --node-count 1
```


## Deploy application to AKS


Automatically containerize and deploy
Authorize Github 
Selecting 'App environment' will drive the wizard to create a Dockerfile to containerize the application. 
Click 'Preview file' to check generated Dockerfile. 
Choose a new name for 'namespace'. 

This creates a new branch  aks-devhub-xyz12