******************************************
## IBM watsonx Orchestrate ADK Windows Installation Guide
******************************************

## Introduction

The IBM watsonx Orchestrate Agent Development Kit (ADK) is a set of tools designed to make it easy to build and deploy agents using IBM watsonx Orchestrate.

- If you encounter any issues during installation, refer to the published [Troubleshooting](https://developer.watson-orchestrate.ibm.com/release/troubleshooting)

------------------------------------------

## Prerequisites

- **Windows Subsystem for Linux (WSL):**
  WSL 2 is recommended. 

- **Python 3.11-3.13:**
  Ensure you have Python 3.11-3.13 installed. The instructions below are for installation of Python 3.12.

- **Dependencies:**
  All required python dependencies will be automatically installed when you install the orchestrate package (pip is required).

------------------------------------------

## Installing Prerequisites

### WSL Installation
1. Install [Windows Subsystem for Linux (WSL)](https://learn.microsoft.com/en-us/windows/wsl/install) on your laptop following the published instructions from Microsoft. Windows Subsystem for Linux (WSL) 2 is a full Linux kernel built by Microsoft, which lets Linux distributions run without managing virtual machines. WSL allows developers to install a Linux distribution and use Linux applications, utilities, and Bash command-line tools directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup.
  - Open PowerShell or Windows Command Prompt in administrator mode by right-clicking and selecting "Run as administrator", enter the `wsl --install` command, then restart your machine. This command will enable all the necessary features for WSL and install the default Ubuntu distribution of Linux. [(The default distribution can be changed)](https://learn.microsoft.com/en-us/windows/wsl/basic-commands#install), however these instructions will assume that you're using Ubuntu.
2. Once you've installed WSL, open Ubuntu via the Start Menu. You will be prompted to create a Username and Password. Follow the published [best practices](https://learn.microsoft.com/en-us/windows/wsl/setup/environment#set-up-your-linux-username-and-password) for set up.

------------------------------------------