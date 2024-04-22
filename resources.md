# Azure CI/CD Setup Guide

This guide provides step-by-step instructions on setting up Continuous Integration and Continuous Deployment (CI/CD) pipelines using Azure services.

## Container Registry Setup

1. **Find Container Registry**: Navigate to the Azure portal and locate the Container Registry service.
   
2. **Registry Name and Resource Group**: Note down the Registry Name and the Resource Group associated with it. For example, `testdockerifte.azurecr.io`.

3. **Enable Admin User**: Access the Container Registry resource and enable the admin user. Remember the login server and password.

## Web Application Deployment

1. **Create Web App Instance**: Go to the Azure portal and create a new Web App instance. Provide a name (e.g., `mltestifte`) and link it to the previously created resource group (`testdockerifte`).

2. **Publish Container**: During the creation process, choose to publish a container. Use the default values for the code.

3. **Container Configuration**: Navigate to the Container Tab within the Web App settings and specify the Azure Container Registry. Ensure the desired image is available in the dropdown list.

## Docker Commands

Run the following commands from the terminal to build and push the Docker image:

```bash
# Build the Docker image
docker build -t testdockerifte.azurecr.io/mltestifte:latest .

# Login to Azure Container Registry
docker login testdockerifte.azurecr.io

# Push the Docker image to Azure Container Registry
docker push testdockerifte.azurecr.io/mltestifte:latest

# If facing login issues, install Azure CLI and run the following commands:
# az login
# az acr login --name testdockerifte
```

## Continuous Deployment Setup

1. **Deployment Center**: In the Web App settings, navigate to the Deployment Center.

2. **Source Selection**: Choose the source for continuous deployment (e.g., GitHub actions, build pipelines, etc.).

3. **Repository Information**: Provide the necessary repository information for the selected source.

4. **Enable Continuous Deployment**: Turn on continuous deployment to automate the deployment process.

## Additional Notes

- Ensure proper permissions and access controls are set up for the Azure services.
- Regularly monitor the CI/CD pipeline for any errors or failures.
- Refer to Azure documentation for more advanced configuration options and troubleshooting.



https://www.youtube.com/watch?v=g687fRBNNGo&list=PLZoTAELRMXVPS-dOaVbAux22vzqdgoGhG&index=13

Azure Set up for CICD
https://www.youtube.com/watch?v=g687fRBNNGo&list=PLZoTAELRMXVPS-dOaVbAux22vzqdgoGhG&index=13&pp=iAQB
Find Container Registry → Registry Name + Resource group → testdockerifte.azurecr.io (keeping docker image) 
After Creation → go to resource → Access Keys → enable admin user → keep remember 
Login server/password
Create Webapp → Instance Name (mltestifte) → Resource testdockerifte → publish container (default value code)
Go to Container Tab → Azure container registry → Image (Need to create from Local machine) → after the following step Image name should be in drop down list

Run from terminal:
# docker build -t testdockerifte.azurecr.io/mltestifte:latest .
# docker login testdockerifte.azurecr.io → here password is only the testdockerifte from testdockerifte.azurecr.io
# docker push testdockerifte.azurecr.io/mltestifte:latest  → if there is any login issues then install azure cli → run the following commands in cmd
az login
az acr login --name testdockerifte
Then Try again 
Webapp → deployment center → source (Github action build deploy ….. ) → provide repository infos → continuous deployment Turn it on 
