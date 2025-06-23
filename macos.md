# IBM watsonx Orchestrate ADK macOS Installation Guide

## Introduction

The IBM watsonx Orchestrate Agent Development Kit (ADK) is a set of tools designed to make it easy to build and deploy agents using IBM watsonx Orchestrate.

This guide provides step-by-step instructions for installing the ADK on macOS.

## Prerequisites

Before starting the installation, ensure you have:

- **macOS 10.15 (Catalina) or higher**
- **Administrator access** to your Mac
- **Internet connection** for downloading components
- **IBM Cloud account** with access to watsonx.ai services

## Installation Steps

### Step 1: Install Homebrew

Homebrew is a package manager for macOS that we'll use to install Python and other dependencies.

1. **Open Terminal:**
   - Press `Cmd + Space` to open Spotlight
   - Type `Terminal` and press `Enter`

2. **Check if Homebrew is already installed:**
   ```bash
   brew --version
   ```

3. **Install Homebrew** (if not already installed):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

4. **Add Homebrew to your PATH** (follow the instructions shown at the end of the installation process):
   ```bash
   echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zshrc
   source ~/.zshrc
   ```

### Step 2: Install Python

1. **Check current Python version:**
   ```bash
   python3 --version
   ```

2. **Install Python 3.12 using Homebrew:**
   ```bash
   brew install python@3.12
   ```

3. **Set Python 3.12 as default:**
   ```bash
   ln -s /opt/homebrew/opt/python@3.12/bin/python3.12 /opt/homebrew/opt/python@3.12/bin/python
   ln -s /opt/homebrew/opt/python@3.12/bin/pip3.12 /opt/homebrew/opt/python@3.12/bin/pip
   echo 'export PATH="/opt/homebrew/opt/python@3.12/bin:$PATH"' >> ~/.zshrc
   source ~/.zshrc
   ```

4. **Verify installation:**
   ```bash
   python3.12 --version
   pip3 --version
   ```

### Step 3: Set up watsonx.ai and Watson Machine Learning

1. **Create IBM Cloud Account:**
   - Sign up at [watsonx AI](https://eu-de.dataplatform.cloud.ibm.com/registration/stepone)

2. **Create a watsonx.ai Project:**
   - Go to [Projects](https://dataplatform.cloud.ibm.com/projects/?context=wx)
   - Click "New Project" and follow the setup wizard

3. **Create a Deployment Space:**
   - Navigate to [Deployment Spaces](https://dataplatform.cloud.ibm.com/ml-runtime/spaces?context=wx)
   - Click "New Space" and associate it with your project
   - Note: You may be able to associate an existing watsonx.ai Runtime Service during creation

4. **Configure Runtime Service:**
   - Open your deployment space
   - Go to the "Manage" tab
   - Associate your watsonx.ai Runtime Service or create a new one

5. **Get Your Space ID:**
   - Go to [Developer Access](https://dataplatform.cloud.ibm.com/developer-access?context=wx)
   - Under "Project or space ID", select "Space" from the Location dropdown
   - Your Space ID will auto-populate - copy this value

6. **Create API Key:**
   - Navigate to [watsonx Home Page](https://dataplatform.cloud.ibm.com/wx/home?context=wx)
   - Under "Developer access", select your deployment space
   - Click "Create API key"
   - Give your key a name and copy/download the key value

### Step 4: Install Docker Engine

The watsonx Orchestrate team recommends [Rancher Desktop](https://rancherdesktop.io/):

1. **Download and install Rancher Desktop:**
   - Visit [Rancher Desktop](https://rancherdesktop.io/)
   - Download the macOS version
   - Install the application

2. **Configure Rancher settings:**
   - Open Rancher Desktop
   - Go to Settings
   - Ensure Docker is selected as the container engine
   - Configure according to [recommended settings](https://github.ibm.com/WatsonOrchestrate/wxo-clients/blob/main/_docs/recommended-docker-settings/rancher-settings.md)

3. **Verify Docker installation:**
   ```bash
   docker --version
   docker ps
   ```

### Step 5: Get Entitlement Key

1. **Follow the official guide** to obtain your watsonx Orchestrate entitlement key:
   - Visit [Getting the Entitlement Key](https://developer.watson-orchestrate.ibm.com/getting_started/wxOde_setup#getting-the-entitlement-key)
   - Complete the required steps to generate your key

### Step 6: Create Environment Configuration

1. **Create a .env file** in your home directory:
   ```bash
   cd ~
   nano .env
   ```

2. **Add the following content** (replace with your actual values):
   ```bash
   WO_DEVELOPER_EDITION_SOURCE=myibm
   WATSONX_APIKEY=<your_ibm_cloud_api_key>
   WATSONX_SPACE_ID=<your_watsonx_ai_space_id>
   WO_ENTITLEMENT_KEY=<your_entitlement_key>
   ```

3. **Save the file** (Ctrl+X, then Y, then Enter in nano)

### Step 7: Install the ADK

1. **Install the watsonx Orchestrate package:**
   ```bash
   pip3 install ibm-watsonx-orchestrate
   ```

2. **Verify installation:**
   ```bash
   orchestrate --version
   ```

### Step 8: Start Local Server and Create Your First Agent

1. **Start the local server:**
   ```bash
   orchestrate server start --env-file=.env
   ```

2. **Set your environment:**
   ```bash
   orchestrate env activate local
   ```
   and check it is active
   ```bash
   orchestrate env list
   ```

3. **Create your first agent:**
   - Follow the [Hello World Tutorial](https://developer.watson-orchestrate.ibm.com/tutorials/tutorial_1_hello_world)
   - Or use the CLI to create a basic agent:
   ```bash
   orchestrate agents create my-first-agent
   ```

## CLI Reference

After installation, you have access to the WXO CLI tool using the `orchestrate` command:

```bash
orchestrate --help
```

### Available Commands:
- `orchestrate tools` - Manage development tools
- `orchestrate agents` - Manage agents
- `orchestrate server` - Control the local server
- `orchestrate chat` - Chat with agents
- `orchestrate connections` - Manage connections
- `orchestrate models` - Manage models
- `orchestrate env` - Environment management

## Verification

To verify your installation is working correctly:

1. **Check all components:**
   ```bash
   python3.12 --version
   docker --version
   orchestrate --version
   ```

2. **Check your environment is active:**
   ```bash
   orchestrate env list
   ```

3. **Test agent creation:**
   ```bash
   orchestrate agents list
   ```

## Troubleshooting

### Common Issues:

1. **Homebrew installation fails:**
   - Ensure you have administrator privileges
   - Check your internet connection
   - Try running the installation command again

2. **Python path issues:**
   - Verify the PATH is correctly set in `~/.zshrc`
   - Restart Terminal or run `source ~/.zshrc`
   - Check that the symlinks are created correctly

3. **Docker not accessible:**
   - Ensure Rancher Desktop is running
   - Check that Docker is selected as the container engine
   - Restart Rancher Desktop if needed

4. **Permission errors:**
   - Ensure you're using the correct user permissions
   - Check file permissions for the `.env` file

5. **Environment variables not found:**
   - Verify your `.env` file is in the correct location (`~/.env`)
   - Check that the file has the correct format
   - Ensure no extra spaces or characters in the file

### Getting Help:

- **Official Troubleshooting Guide:** [Troubleshooting](https://developer.watson-orchestrate.ibm.com/release/troubleshooting)
- **IBM watsonx Orchestrate Documentation:** [Documentation](https://developer.watson-orchestrate.ibm.com/)
- **Homebrew Documentation:** [Homebrew](https://brew.sh/)
- **Rancher Desktop Documentation:** [Rancher Desktop](https://rancherdesktop.io/)

## Next Steps

After successful installation:

1. **Complete the Hello World Tutorial** to create your first agent
2. **Explore the CLI commands** to understand available functionality
3. **Read the official documentation** for advanced features
4. **Join the community** for support and updates

---

**Note:** This guide is designed for the latest version of the IBM watsonx Orchestrate Agent Development Kit. Always refer to the [official documentation](https://developer.watson-orchestrate.ibm.com/) for the most up-to-date information.