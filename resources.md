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


1. **Azure CI/CD Setup**

    **Container Registry Setup:**
    - Find Container Registry: Locate the Container Registry service in the Azure portal.
    - Registry Name + Resource group: Note down the Registry Name and the associated Resource group, for example, `testdockerifte.azurecr.io`.
    - Enable Admin User: Access the Container Registry resource and enable the admin user. Remember the login server and password.

    **Web Application Deployment:**
    - Create Webapp: Create a Web App instance named `mltestifte` linked to the `testdockerifte` resource group.
    - Publish Container: During creation, choose to publish a container using the default code value.
    - Container Tab: Navigate to the Container Tab within the Web App settings and specify the Azure Container Registry. Ensure the desired image appears in the dropdown list.

    **Run from Terminal:**
    ```bash
    # Build Docker image
    docker build -t testdockerifte.azurecr.io/mltestifte:latest .

    # Login to Azure Container Registry
    docker login testdockerifte.azurecr.io

    # Push Docker image to Azure Container Registry
    docker push testdockerifte.azurecr.io/mltestifte:latest
    ```
    If login issues occur, install Azure CLI and execute the following commands:
    ```bash
    az login
    az acr login --name testdockerifte
    ```

    **Continuous Deployment Setup:**
    - Deployment Center: In Web App settings, navigate to the Deployment Center.
    - Source: Choose the source for continuous deployment (e.g., GitHub action build deploy).
    - Provide repository information and turn on continuous deployment.

2. **References**
   - [Azure CI/CD Setup Video playlist ](https://www.youtube.com/watch?v=g687fRBNNGo&list=PLZoTAELRMXVPS-dOaVbAux22vzqdgoGhG&index=13)
   - [Azure CI/CD Setup Video ](https://www.youtube.com/watch?v=g687fRBNNGo&list=PLZoTAELRMXVPS-dOaVbAux22vzqdgoGhG&index=13&pp=iAQB)

Feel free to use this organized information for your documentation.