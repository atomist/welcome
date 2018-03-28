# Configuring the automation client

Locally, we recommend `atomist config`. 

### Manual Configuration

When you deploy the SDM, or yif you don't want to use `atomist config`, set these environment variables:

- `ATOMIST_TEAM`: A single Atomist workspace this automation will serve. For example, `export ATOMIST_TEAM="A5964N9B7"`.

Alternatively ,you can subscribe to events from multiple workspaces with `ATOMIST_TEAMS`. 
For example: `ATOMIST_TEAMS="A5964N9B7,A29E48P34"` 
If an `ATOMIST_TEAMS` environment variable is specified, it will always take precedence and other
named workspaces will be ignored.

The workspace id of your Atomist workspace can be obtained from the dashboard running at: https://app.atomist.com. Once
logged in, visit the Settings page of your selected workspace. Make sure to copy the Atomist workspace id, not the Slack 
workspace id.

- `ATOMIST_TOKEN`: A GitHub personal access token with `read:org` scope. For local runs you'll want `repo` scope as well, as many of the automations will happen with this token when running locally.