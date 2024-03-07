# Event access to Azure AI resources

You are following these instructions because you are participating in an event where the Azure AI resources for the workshop are provided for you. In this case, you'll be given an Azure AI Proxy Endpoint and a time bound API Key to access the Azure AI resources.

You will perform the follow steps:

1. Set up the workshop environment on your own computer or with GitHub Codespaces.
1. Create the Prompt Flow connections.
1. Proceed to the workshop.

## Set up the workshop environment

You can run the workshop on your own computer or with GitHub Codespaces.

### Run the workshop on your own computer

To run the workshop on your own computer, complete the following steps:

1. Install the following:
    - On Windows install [Python](https://www.python.org/downloads/), skip for macOS and Linux as Python is pre-installed.
    - [Visual Studio Code](https://code.visualstudio.com/)
    - [Python VS Code Extension](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

1. From the command line, navigate to your preferred folder for the workshop.
1. Clone the Contoso Chat Proxy repository from GitHub:

    ```shell
    git clone https://github.com/gloveboxes/contoso-chat-proxy.git
    ```

1. Navigate to the `contoso-chat-proxy` folder.
1. Create a Python virtual environment:

    ```shell
    python -m venv .venv
    ```

1. Activate the virtual environment:

    On Windows:

    ```shell
    .venv/Scripts/activate
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

### Run the workshop with GitHub Codespaces

To run the workshop with GitHub Codespaces, complete the following steps:

1. Fork the [Contoso Chat Proxy](https://github.com/gloveboxes/contoso-chat-proxy) repository to your GitHub account.

    ![](media/repo_fork.png)

1. Open the forked repository in GitHub Codespaces. In the forked repository, select `Code`, then the `Codespaces` tab, and then select `Create codespace on main`. The GitHub Codespaces environment will be created for you. It will take approximately 5 minutes to create the environment.

    <!-- ![](media/codespaces_open.png) -->

    !!! warning
        Be sure to stop the Codespace when you are done to avoid incurring charges.

## Create the Prompt Flow connections

1. From VS Code, update the `.env.proxy` file with the Azure AI Proxy Endpoint and API Key provided to you.
1. Configure the Prompt Flow connections:

    - Open the `connections` folder, then open the `proxy-create-connections.ipynb` notebook.
    - You will be prompted to install the Jupyter extension, select **Install**.
    - Select `Run All` in the notebook to create the connections.

## Proceed to the workshop

Proceed to the [Workshop](workshop.md) section.
