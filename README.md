# GitHub Action with Keeper Secrets Manager Integration

This GitHub repository demonstrates the integration of Keeper Secrets Manager (KSM) with GitHub Actions. This integration facilitates the secure retrieval of secrets from Keeper Vaults directly into GitHub Actions, supporting dynamic secrets management in CI/CD workflows.

## Features

- **Retrieve Secrets**: Securely pull secrets from Keeper Vaults into GitHub Actions.
- **Environment and Build Arguments**: Set secret credentials directly as build arguments or environment variables.
- **Secure File Handling**: Copy secure files from Keeper Vaults to the GitHub runner.

## Prerequisites

Before using this GitHub Action, ensure the following prerequisites are met:

- Access to Keeper Secrets Manager. [Quick Start Guide](https://docs.keeper.io/en/v/secrets-manager/secrets-manager/quick-start-guide)
- Secrets Manager addon enabled for your Keeper account.
- Membership in a Role with Secrets Manager enforcement policy enabled.
- A Keeper Secrets Manager Application with secrets shared to it. Instructions for creating an application are in the Quick Start Guide.
- An initialized Keeper Secrets Manager Configuration in Base64 format.

## Configuration

1. **GitHub Secrets**: Configure the `KSM_CONFIG` as a secret in GitHub repository settings.
2. **Keeper Secrets Manager Configuration**: Ensure your Keeper configuration is set up and accessible as described in the [Keeper documentation](https://docs.keeper.io/en/v/secrets-manager/secrets-manager/integrations/github-actions).

## Usage

To execute this action:

**Manual Trigger**: This action is configured to trigger manually through the GitHub UI under the *Actions* tab using `workflow_dispatch`.

## Explanation of Demo

Upon execution, the following takes place:
- A Github Action ubuntu runner is launched
- A GPG public/private key pair and password is pulled from the Keeper vault
- The GPG key from Keeper is imported
- A sample "Hello World" Go application is built
- The binary is signed with the GPG key
- The signature is displayed
- The application is run

## Documentation and Resources

For more detailed documentation on the Keeper Secrets Manager and its integration with GitHub Actions, visit the official [documentation](https://docs.keeper.io/en/v/secrets-manager/secrets-manager/integrations/github-actions).
