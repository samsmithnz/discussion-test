# discussion-test

This repository contains a GitHub Action workflow that automatically creates discussions with the current date and time as the title.

## GitHub Action: Create Daily Discussion

The workflow file `.github/workflows/create-discussion.yml` creates a new discussion with the current date and time as the title.

### Features

- **Automatic Scheduling**: Runs daily at midnight UTC
- **Manual Trigger**: Can be triggered manually via GitHub's workflow dispatch
- **Dynamic Title**: Uses current date and time in format `YYYY-MM-DD HH:MM:SS UTC`
- **Error Handling**: Validates repository and discussion category existence
- **Security**: Uses GraphQL variables to prevent injection vulnerabilities

### Prerequisites

Before the workflow can run successfully:

1. **Enable Discussions**: Go to Settings > General > Features and enable Discussions for this repository
2. **Create a Category**: At least one discussion category must exist in the repository

### How to Use

#### Manual Trigger

1. Go to the "Actions" tab in your repository
2. Select "Create Daily Discussion" workflow
3. Click "Run workflow"
4. Select the branch and click "Run workflow"

#### Automatic Schedule

The workflow automatically runs daily at midnight UTC (00:00 UTC).

### Customization

You can customize the workflow by editing `.github/workflows/create-discussion.yml`:

- **Schedule**: Modify the `cron` expression to change when the workflow runs
- **Title Format**: Update the `date` command in the "Get current date and time" step
- **Discussion Body**: Change the body text in the "Create discussion" step
- **Category Selection**: Modify the GraphQL query to select a specific category instead of the first one

### Permissions

The workflow requires the following permissions:
- `discussions: write` - To create discussions
- `contents: read` - To access repository information