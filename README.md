# GitHub-Copilot-agent-task

A GitHub Actions workflow that leverages GitHub Copilot to automatically write code based on task descriptions.

[![GitHub Copilot Agent](https://github.com/idea2app/GitHub-Copilot-agent-task/actions/workflows/copilot-agent.yml/badge.svg)](https://github.com/idea2app/GitHub-Copilot-agent-task/actions/workflows/copilot-agent.yml)

## Features

- **Manual Trigger**: Create pull requests with task descriptions via `workflow_dispatch` event
- **Auto Code Generation**: GitHub Copilot automatically implements the task
- **Comment Updates**: Update code by commenting on pull requests to trigger Copilot revisions

## Installation

### New repository

Click the [<kbd>Use this template</kbd>](https://github.com/new?template_name=GitHub-Copilot-agent-task&template_owner=idea2app) button on the top of this GitHub repository's home page to create your own repository.

### Old repository

```shell
cd /path/to/your/git/repository/root

mkdir -p .github/workflows
cd .github/workflows
curl -O https://raw.githubusercontent.com/idea2app/GitHub-Copilot-agent-task/main/.github/workflows/copilot-agent.yml
cd ../..
```

## Usage

### Creating a new task

1. Go to the **Actions** tab in your repository
2. Select **GitHub Copilot Agent** workflow from the left sidebar
3. Click **Run workflow** button
4. Fill in the required fields:
   - **Title**: Brief title for your task (e.g., "Add user authentication")
   - **Description**: Detailed description of what you want to implement
5. Click **Run workflow** to start

The workflow will:
- Create a new branch automatically
- Create a pull request with your task description
- Tag GitHub Copilot to implement the task

### Updating code via comments

1. Open the pull request created by the workflow
2. Add a comment mentioning `@github-copilot` with your feedback or update request
3. GitHub Copilot will respond and update the code based on your comment

Example comment:
```
@github-copilot please add input validation for email format and add error messages for empty fields
```

## Example

**Title**: `Add login page`

**Description**:
```
Create a login page with the following features:
- Email and password input fields
- Remember me checkbox
- Submit button
- Form validation
- Error message display
```

GitHub Copilot will analyze the description and generate the necessary code in the pull request.

## Requirements

- GitHub Copilot enabled in your repository
- GitHub Actions enabled
- Appropriate permissions for the workflow (contents: write, pull-requests: write, issues: write)

## License

This project is licensed under the terms specified in the LICENSE file.