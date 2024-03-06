# Provision Azure workshop resources

## Requirements

You require an Azure Subscription. If you don't have an Azure subscriptions, you can create a [free subscription](https://azure.microsoft.com/en-us/free/free-account-faq).

## Step 1: Provisioning Azure resources

In this section you'll set up the Azure resources required for the workshop.

1. Clone the [contoso-chat](https://github.com/azure-Samples/contoso-chat) repo.
1. From the VS Code Dev Container or the virtual Python environment, run the `./provision.sh` script.
1. After the provisioning script completes, follow the instructions raised in this [issue](https://github.com/Azure-Samples/contoso-chat/issues/52).

## Step 2: Load grounding data

The solutions uses two data sources to ground the LLM prompt. The first is an Azure AI Search index that contains product information. The second is a Cosmos DB database that contains customer information.

### Load the product catalog

In this step you'll learn how to load product data into [Azure AI Search](https://learn.microsoft.com/en-us/azure/search/). The product database will be used to ground the LLM prompt with product information.

Azure AI Search is a hybrid index service with support for keyword and semantic vector search. When data the is loaded into Azure AI Search, a keyword index is built for each product, and an embedding is generated for each product and is stored in a vector index.

Architecturally, a search service sits between the external data stores that contain your un-indexed data, and your client app that sends query requests to a search index and handles the response.

![](./media/azure-search.svg)

Follow these steps:

1. Ensure you have the **contoso-chat** repo open in VS Code.
1. Load the Product catalog
    - Open the `data/product_info/products.csv` file and review the contents.
    - Run the `data/product_info/create-azure-search.ipynb` Jupyter Notebook. The notebook will store product data and generated product description embeddings in Azure AI Search.
    - Switch to Azure AI Search in the Azure Portal
    - Review the AI Search resource and note that the semantic search feature is enabled.
    - Show the indexes:
        - Select the `contoso-products` index. There are 20 documents indexed.
        - Search the index - `what tents can you recommend?`. Azure AI Search will use the keyword index to return the product catalog results that most closely match the question.
        - Review the results and note the vector from the embedding is returned with each result.
        - The Prompt Flow will use the index to ground the LLM prompt.

            ![](./media/contoso-products.png)

### Load the customer database

In this step you'll learn how to load customer data into [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/introduction). The customer data will be used to ground the LLM prompt with customer order history.

1. Run the `/data/customer_info/create-cosmos-db.ipynb` Jupyter Notebook to load the customer data into Cosmos DB.
1. Navigate to Cosmos DB in Azure Portal and update one of the records with your name.
    - Select Data Explorer -> contoso-outdoor -> Customers -> Items.
    - Pick and item to update, the select Update.

        ![](./media/cosmos-explore-data.png)

