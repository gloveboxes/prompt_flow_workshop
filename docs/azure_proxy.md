# Event access to Azure AI resources

You are following these instructions because you are taking part in an event where the Azure AI resources for the workshop are provided for you. In this case, you'll be given an [Azure AI Proxy](https://aka.ms/ai-proxy-docs) Endpoint and a time bound API Key to access the Azure AI resources.

You will perform the follow steps:

1. Set up the workshop environment with GitHub Codespaces.
1. Create the Prompt Flow connections.
1. Proceed to the workshop.

## Azure Resources backing the workshop

The Azure AI resources for the workshop are provided by the Azure AI Proxy Endpoint. The Azure AI Proxy Endpoint provides access to the following Azure AI resources:

- [Azure AI Search](https://azure.microsoft.com/products/ai-services/ai-search/). The Azure AI Search connection provides access to the `contoso-products` search index.
- [Azure OpenAI](https://azure.microsoft.com/products/ai-services/openai-service). The Azure OpenAI connection provides access to the GPT-3.5-turbo, GPT-4 large, and embedding models.

To run the workshop with [GitHub Codespaces](https://docs.github.com/en/codespaces/overview), complete the following steps:

1. From your web browser, navigate to the [Contoso Chat Proxy](https://github.com/gloveboxes/contoso-chat-proxy){target=_blank} repo. This will open the GitHub repository in a new browser tab so you can follow the instructions in this tab.
1. Select the `<> Code` button, then select `Codespaces`.
1. Next select `Create codespace in main`. This will start up a GitHub Codespaces environment for you. It will take approximately 1 minute to create the environment.

    <!-- ![](media/codespaces_open.png) -->

    !!! warning
        When you have finished the workshop, be sure to stop the Codespace to avoid incurring unnecessary charges.

## Grounding data for the workshop

There are two data sources for the workshop:

1. Product information from Azure AI Search. This data is accessed via the Azure AI Proxy Endpoint. The data was loaded into Azure AI Search from the `data/product_info` folder using the `create-azure-search.ipynb` notebook.
1. Customer order history data is loaded from the `data/customer_info` folder into a Python Pandas DataFrame. The data is used to create a personalized shopping experience for the customer. In production, this data would be accessed from a database such as [Cosmos DB](https://learn.microsoft.com/azure/cosmos-db/).

## Create the Prompt Flow connections

The following connections are created:

- **aoai-connection**: This connection is used to access Azure OpenAI embedding, gpt-35-turbo and gpt-4 large language models (LLMs).
- **contoso-search**: This connection is used to access the Azure AI Search service and `contoso-products` search index.

Create the Prompt Flow connections:

1. From VS Code, update the `.env.proxy` file with the Azure AI Proxy Endpoint and API Key provided to you. Update the AI_PROXY_ENDPOINT and AI_PROXY_KEY with the values from the Azure AI Proxy Endpoint. Ignore the rest of the environment variables.

1. Configure the Prompt Flow connections:

    - Open the `connections` folder, then open the `proxy-create-connections.ipynb` notebook.
    - Select `Run All` in the notebook to create the connections.

## Proceed to the workshop

Proceed to the [Workshop](workshop.md) section.
