******************************************
## IBM watsonx Orchestrate ADK macOS Installation Guide
******************************************

## Introduction

The IBM watsonx Orchestrate Agent Development Kit (ADK) is a set of tools designed to make it easy to build and deploy agents using IBM watsonx Orchestrate.

- If you encounter any issues during installation, refer to the published [Troubleshooting](https://developer.watson-orchestrate.ibm.com/release/troubleshooting)

------------------------------------------

## Prerequisites

- **Python 3.11-3.13:**
  Ensure you have Python 3.11-3.13 installed.

- **Dependencies:**
  All required python dependencies will be automatically installed when you install the orchestrate package (pip is required).

------------------------------------------

## Installing Prerequisites

### Installing Homebrew on macOS
Homebrew is a popular package manager for macOS. Follow these steps to install it:

1. Open Terminal
    - Use Spotlight (press <kbd>Cmd</kbd> + <kbd>Space</kbd>), type `Terminal`, and press <kbd>Enter</kbd>.
2. Check if homebrew is installed `brew --version` if you get an error proceed to the next step
3. Install Homebrew
    - In the Terminal window, paste the following command and press <kbd>Enter</kbd>:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
4. Add the brew command to your PATH, by following the instructions shown at the end of the installation process

### Installing Python 3.12 with Homebrew
Follow these steps to verify whether Python 3.12 is installed on your Mac, install it using Homebrew if necessary, and configure your system so that Python 3.12 is the default.

1. Open Terminal
    - Press <kbd>Cmd</kbd> + <kbd>Space</kbd>, type `Terminal`, and press <kbd>Enter</kbd>.
2. Check if Python 3.12 is Installed
    - Run `python3.12 --version` to see if python 3.12 is installed, if not proceed with the following steps.
3. `brew install python@3.12`
4. Set python3.12 as your default
```bash
ln -s /opt/homebrew/opt/python@3.12/bin/python3.12 /opt/homebrew/opt/python@3.12/bin/python
ln -s /opt/homebrew/opt/python@3.12/bin/pip3.12  /opt/homebrew/opt/python@3.12/bin/pip
echo 'export PATH="/opt/homebrew/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```


------------------------------------------

## Setting up watsonx.ai and Watson Machine Learning (WML) Instance

1. Log in or sign up to [watsonx AI](https://eu-de.dataplatform.cloud.ibm.com/registration/stepone)
2. Create a watsonx.ai project [here](https://dataplatform.cloud.ibm.com/projects/?context=wx)
3. After you've created your project, you need to create a deployment space for that project [here](https://dataplatform.cloud.ibm.com/ml-runtime/spaces?context=wx). During space creation, you may be able to associate an existing watsonx.ai Runtime Service to the space. If you choose to do so, skip step 3 and go directly to step 4.
4. After creating your deployment space, open the space by clicking on its name, then navigate to the Manage tab. 
   Associate your watsonx.ai Runtime Service to that deployment space, or create a new Runtime Service if necessary.
5. Retrieve your Space ID [here](https://dataplatform.cloud.ibm.com/developer-access?context=wx), under the `Project or space ID` section, select the Location dropdown and select Space. The deployment space you created in step 2 and its Space ID should autopopulate in their respective fields. Copy the Space ID for later use in your environment file.
6. If you do not already have a watsonx.ai API key, create one by navigating to the [IBM watsonx Home Page](https://dataplatform.cloud.ibm.com/wx/home?context=wx). Under the "Developer access" section, select the Deployment Space that you created in step 3 above from the "Project or space" dropdown menu. Select the `Create API key` button. Give your API Key a name, then copy/download the key value for later use in your environment file.
------------------------------------------

## Docker Engine

### Rancher
Ensure that you have a docker engine installed. The watsonx Orchestrate team 
   recommends [Rancher](https://rancherdesktop.io/).

Please make sure your instance of Rancher is configured with the following settings:
- Settings for [Rancher](https://github.ibm.com/WatsonOrchestrate/wxo-clients/blob/main/_docs/recommended-docker-settings/rancher-settings.md)

------------------------------------------

## Generating an entitlement key
To get a watsonx Orchestrate entitlement key, follow the instructions provided [here](https://developer.watson-orchestrate.ibm.com/getting_started/wxOde_setup#getting-the-entitlement-key). 

------------------------------------------

## Create a .env file with the following contents
```
WO_DEVELOPER_EDITION_SOURCE=myibm
WATSONX_APIKEY=<your ibm cloud api key>
WATSONX_SPACE_ID=<your watsonx ai space id>
WO_ENTITLEMENT_KEY=<your entitlement key>
```

------------------------------------------

## Installing the ADK, Starting a local server instance, and Creating Your First Agent

1. https://developer.watson-orchestrate.ibm.com/getting_started/installing<br>
2. https://developer.watson-orchestrate.ibm.com/getting_started/wxOde_setup#installing-the-watsonx-orchestrate-developer-edition-with-adk<br>
3. https://developer.watson-orchestrate.ibm.com/tutorials/tutorial_1_hello_world<br>

------------------------------------------

## CLI Documentation

After installation, you will have access to the WXO CLI tool
This tool can be accessed using the `orchestrate` command

```bash
 orchestrate --help
                                                                                
 Usage: orchestrate [OPTIONS] COMMAND [ARGS]...                                 
                                                                                
╭─ Options ────────────────────────────────────────────────────────────────────╮
│ --install-completion          Install completion for the current shell.      │
│ --show-completion             Show completion for the current shell, to copy │
│                               it or customize the installation.              │
│ --help                        Show this message and exit.                    │
╰──────────────────────────────────────────────────────────────────────────────╯
╭─ Commands ───────────────────────────────────────────────────────────────────╮
│ tools                                                                        │
│ agents                                                                       │
│ server                                                                       │
│ chat                                                                         │
│ connections                                                                  │
│ models                                                                       │
│ env                                                                          │
╰──────────────────────────────────────────────────────────────────────────────╯
```
------------------------------------------