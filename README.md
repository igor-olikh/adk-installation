# IBM watsonx Orchestrate Agent Development Kit (ADK) Installation Guides

This repository contains comprehensive installation guides for the IBM watsonx Orchestrate Agent Development Kit (ADK) across different operating systems.

## Overview

The IBM watsonx Orchestrate Agent Development Kit (ADK) is a powerful set of tools designed to simplify the process of building and deploying agents using IBM watsonx Orchestrate. These guides provide step-by-step instructions for setting up the development environment on various platforms.

## What's Included

- **Windows Installation Guide** - Complete setup instructions for Windows users using WSL
- **macOS Installation Guide** - Complete setup instructions for macOS users using Homebrew

## Prerequisites

Before following any installation guide, ensure you have:

- **Python 3.11-3.13** - The ADK requires Python 3.11 or higher
- **pip** - Python package installer
- **IBM Cloud Account** - Access to watsonx.ai services
- **Docker Engine** - Container runtime (Rancher Desktop recommended)
- **WSL 2** (Windows users) - Windows Subsystem for Linux 2
- **Homebrew** (macOS users) - Package manager for macOS

## Quick Start

### Windows Users
1. Follow the [Windows Installation Guide](windows.md)
2. Install WSL 2 and Ubuntu
3. Set up your watsonx.ai project and deployment space
4. Install the ADK using pip

### macOS Users  
1. Follow the [macOS Installation Guide](macos.md)
2. Install Homebrew and Python 3.12
3. Set up your watsonx.ai project and deployment space
4. Install the ADK using pip

## Key Features

- **Cross-platform Support** - Installation guides for Windows and macOS
- **Step-by-step Instructions** - Detailed, easy-to-follow setup procedures with 8 comprehensive steps
- **Self-contained Guides** - Complete instructions without heavy reliance on external resources
- **Comprehensive Verification** - Built-in testing and verification procedures
- **Platform-specific Troubleshooting** - Common issues and solutions for each platform
- **Professional Documentation** - Consistent formatting and clear organization

## Installation Process

Both guides follow a consistent 8-step installation process:

1. **System Dependencies** - Install platform-specific tools (WSL/Homebrew)
2. **Python Setup** - Install and configure Python 3.12
3. **IBM Cloud Setup** - Configure watsonx.ai project and deployment space
4. **Docker Installation** - Set up container runtime (Rancher Desktop)
5. **Entitlement Key** - Obtain required access credentials
6. **Environment Configuration** - Create and configure `.env` file
7. **ADK Installation** - Install the orchestrate package
8. **Verification & Testing** - Verify installation and create first agent

## Getting Help

If you encounter issues during installation:

1. Check the [Official Troubleshooting Guide](https://developer.watson-orchestrate.ibm.com/release/troubleshooting)
2. Review the troubleshooting section in your platform's guide
3. Ensure all prerequisites are properly installed
4. Verify your IBM Cloud account has the necessary permissions

## Resources

- [IBM watsonx Orchestrate Documentation](https://developer.watson-orchestrate.ibm.com/)
- [watsonx.ai Platform](https://dataplatform.cloud.ibm.com/wx/home?context=wx)
- [IBM Cloud Documentation](https://cloud.ibm.com/docs)
- [WSL Documentation](https://learn.microsoft.com/en-us/windows/wsl/) (Windows users)
- [Homebrew Documentation](https://brew.sh/) (macOS users)
- [Rancher Desktop](https://rancherdesktop.io/) (Docker runtime)

## Contributing

This project welcomes contributions! If you'd like to:

- Add missing installation guides (Linux)
- Improve existing guides
- Fix errors or add clarifications
- Suggest enhancements

Please feel free to submit a pull request or open an issue.

## License

Please refer to IBM's licensing terms for usage rights.

---

**Note**: These guides are designed for the latest version of the IBM watsonx Orchestrate Agent Development Kit. Always refer to the [official documentation](https://developer.watson-orchestrate.ibm.com/) for the most up-to-date information. 