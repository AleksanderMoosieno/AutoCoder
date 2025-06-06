# AutoCoder

### Overview

AutoCoder is a GitHub Action that automates the process of generating code directly from GitHub issues using Grock’s GPT technology and then creates a pull request with the generated code for review. This action is designed to simplify workflows by enabling developers to seamlessly convert issue descriptions into code snippets, functions, or entire modules. AutoCoder is particularly useful for teams looking to prototype features quickly, automate repetitive coding tasks, or maintain a consistent coding standard across a repository.
To use this action in your repository, include it in your GitHub workflow YAML file. Below is an example configuration:

## Example Workflow
Go to .github/workflows/main.yml

## Environment Variables
You may need to set the following environment variables to use the action effectively:

TOKEN: This should be set to secrets.TOKEN....
API: The API key for accessing OpenAI’s ChatGPT, set to secrets.API
Required Permissions
This action requires the following permissions to function properly:

Contents: write
Pull Requests: write

Possible problems:

We ran into a problem when creating a pull request.
The reason was identified - the same names of the base and branch branches
They suggested a solution - to use main as the base branch.
We provided the corrected workflow code
Added additional recommendations for checking the configuration
