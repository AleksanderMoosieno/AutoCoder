# AutoCoder

### Overview

AutoCoder is a GitHub Action that automates the process of generating code directly from GitHub issues using Grock’s GPT technology and then creates a pull request with the generated code for review. This action is designed to simplify workflows by enabling developers to seamlessly convert issue descriptions into code snippets, functions, or entire modules. AutoCoder is particularly useful for teams looking to prototype features quickly, automate repetitive coding tasks, or maintain a consistent coding standard across a repository.
To use this action in your repository, include it in your GitHub workflow YAML file. Below is an example configuration:

## Example Workflow
name: you name

on:
 issues:
 types: [opened, reopened, labeled]
  workflow_dispatch:

permissions:
 contents: write
  pull-requests: write

jobs:
 build:
 if: contains(github.event.issue.labels.*.name, 'autocoder-bot')
    runs-on: ubuntu-latest

    steps:
 - uses: actions/checkout@v4

 name: Generate Code with ChatGPT
        id: generate_code
        uses: PGSch/AutoCoder@main
        with:
 GITHUB_TOKEN: ${{ you.secrets.GITHUB_TOKEN }}
          REPOSITORY: ${{ github.repository }}
          ISSUE_NUMBER: ${{ github.event.issue.number }}
          OPENAI_API_KEY: ${{ you.secrets.OPENAI_API_KEY }}
