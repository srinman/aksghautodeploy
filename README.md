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

This creates a new branch  aks-devhub-xyz12 and creates a PR to merge the changes to main branch.  


First 'Github Actions' workflow will fail since we have not added any code yet but we should have all the necessary files to deploy the application.  

add a simple app.py in /src directory. 
add a requirements.txt file in repo root.  

git add . 
git commit -m "add code"
git push