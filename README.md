# GitHub Action with Keeper Secrets Manager Integration

This GitHub repository demonstrates the integration of Keeper Secrets Manager (KSM) with GitHub Actions. This integration facilitates the secure retrieval of secrets from Keeper Vaults directly into GitHub Actions, supporting dynamic secrets management in CI/CD workflows.

## Features

- **Retrieve Secrets**: Securely pull secrets from Keeper Vaults into GitHub Actions.
- **Environment and Build Arguments**: Set secret credentials directly as build arguments or environment variables.
- **Secure File Handling**: Copy secure files from Keeper Vaults to the GitHub runner.

## Prerequisites

Before using this GitHub Action, ensure the following prerequisites are met:

- Access to Keeper Secrets Manager. [Quick Start Guide](https://docs.keeper.io/en/v/secrets-manager/secrets-manager/integrations/github-actions)
- Secrets Manager addon enabled for your Keeper account.
- Membership in a Role with Secrets Manager enforcement policy enabled.
- A Keeper Secrets Manager Application with secrets shared to it. Instructions for creating an application are in the Quick Start Guide.
- An initialized Keeper Secrets Manager Configuration in JSON or Base64 format.

## Configuration

1. **GitHub Secrets**: Configure the `KSM_CONFIG` as a secret in GitHub repository settings.
2. **Keeper Secrets Manager Configuration**: Ensure your Keeper configuration is set up and accessible as described in the [Keeper documentation](https://docs.keeper.io/en/v/secrets-manager/secrets-manager/integrations/github-actions).

## Usage

To execute this action:

1. **Manual Trigger**: This action is configured to trigger manually through the GitHub UI under the *Actions* tab using `workflow_dispatch`.
2. **Output Handling**:
    - Step outputs like `REC_TITLE`, `LOGIN`, etc., are retrieved from the specified Keeper records.
    - Environment variables like `LOGIN2`, `PASSWORD2`, etc., are set directly for use in subsequent steps.
    - Files specified in the Keeper queries are copied to the specified paths like `/tmp/cmd.txt`.

## Expected Outputs

Upon execution, expect to see:
- Output parameters printed from the step outputs.
- Environment variables and file contents displayed in the GitHub Actions logs.

## Documentation and Resources

For more detailed documentation on the Keeper Secrets Manager and its integration with GitHub Actions, visit the official [documentation](https://docs.keeper.io/en/v/secrets-manager/secrets-manager/integrations/github-actions).

## Video Demo

A video overview of the setup and basic integration with GitHub Actions can be found linked in the Keeper documentation page. This can be useful for visual learners and in-depth demonstrations.
