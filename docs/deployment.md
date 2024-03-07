# Deployment to Azure

This guide will walk you through deploying the Prompt Flow to Azure and is only applicable if you have an Azure subscription and you set up your Azure resources as described in the [Azure setup guide](./azure_provision.md).

In this step you'll learn how to deploy the Prompt Flow to Azure.

1. From VS Code, navigate to the `deployment` folder and open the **push_and_deploy_pf.ipynb** Notebook.
1. Run the notebook to deploy the Prompt Flow to Azure.

## Testing the deployed app

1. After the deployment has completed, navigate to the [Azure AI Portal (ai.azure.com)](https://ai.azure.com).
1. Select **Build**.
1. Select the deployed Prompt Flow.
1. Select the **Deployments** tab
1. Select the deployed app endpoint.
1. Select **Test**.
1. Ask a question `what tents can you recommend for beginners?`.
