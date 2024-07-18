# Automated Deployments for Azure Kubernetes Service   


## Create AKS cluster 

```bash
az group create --name aksghrg --location eastus2
az aks create --resource-group aksghrg --name akscluster --node-count 1
```


## Deploy application to AKS

- add a simple app.py in /src directory. 
- add a requirements.txt file in repo root.  

That's all required to deploy the application to AKS with this auto deployment tool/process.  Other files and folders are created by the tool/process.

From portal,  click 'Automated deployments' under AKS resource.

Authorize Github 
Selecting 'App environment' will drive the wizard to create a Dockerfile to containerize the application. 
Click 'Preview file' to check generated Dockerfile. 
Choose a new name for 'namespace'. 

This creates a new branch  aks-devhub-xyz12 and creates a PR to merge the changes to main branch.  


At the end of this, the application is deployed to AKS. 

As you can see, the process is very simple and easy to use. No need to write any yaml files or Dockerfile. It's similar to Azure Functions code deployment. 


## Review  

Review the yaml in .github/workflows folder to understand GH actions.   

Review manifest files in /manifests folder to understand the deployment.  

Review the Dockerfile in repo root to understand the containerization process.  

You can modify any of these files to trigger a new deployment. 

Also, add paths-ignore to github actions workflow to exclude updates to this README.md file (sample below). 

```yaml
"on":
    push:
        paths-ignore:
            - "README.md"
        branches:
            - main```

```

Any more updates to this doc will not trigger a new deployment. Any other file changes will trigger a new deployment.