# Install the workshop prerequisites on your local computer

Tested and supported on Windows 11 x64 and macOS Apple Silicon. Fails on Windows and Linux on Arm, use GitHub Codespaces instead.

To run the workshop on your own computer you need admin rights on Windows. Complete the following steps:

1. Install the following:
    - On Windows install [Python](https://www.python.org/downloads/), skip for macOS and Linux as Python is pre-installed.
    - [Visual Studio Code](https://code.visualstudio.com/)
    - [Python VS Code Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python)
    - [Prompt Flow VS Code Extension](https://marketplace.visualstudio.com/items?itemName=prompt-flow.prompt-flow)

1. From the command line, navigate to your preferred folder for the workshop.
1. Clone the Contoso Chat Proxy repository from GitHub:

    ```shell
    git clone https://github.com/gloveboxes/contoso-chat-proxy.git
    ```

1. Navigate to the `contoso-chat-proxy` folder.

    ```shell
    cd contoso-chat-proxy
    ```

1. Create a Python virtual environment:

    On Windows:

    ```shell
    python -m venv .venv
    ```

    On macOS and Linux:

    ```shell
    python3 -m venv .venv
    ```

1. Activate the virtual environment:

    On Windows:

    ```shell
    # In cmd.exe
    .venv\Scripts\activate.bat

    # In PowerShell
    .venv\Scripts\Activate.ps1
    ```

    On macOS and Linux:

    ```shell
    source .venv/bin/activate
    ```

1. Install the required Python packages:

    ```shell
    pip install -r requirements.txt
    ```

1. Open the `contoso-chat-proxy` folder in Visual Studio Code.

    ```shell
    code .
    ```

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
    - You will be prompted to install the Jupyter extension, select **Install**.
    - Select `Run All` in the notebook to create the connections.

## Proceed to the workshop

Proceed to the [Workshop](workshop.md) section.
