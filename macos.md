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