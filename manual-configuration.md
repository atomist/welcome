# Manually Configuring an SDM

Locally, we recommend using `atomist config` to [configure your
SDM][sdm-configure], but if you prefer to manually configure your SDM,
follow these instructions.

[sdm-configure]: sdm.md#configuring-your-environment (Atomist - SDM Configuration)

## Prerequisites

### Atomist Workspace/Team ID

You can get your Atomist workspace/team ID from the settings page for
your Atomist workspace on the [Atomist dashboard][dashboard] or by
typing `team` in a DM to the Atomist bot.  Once logged in, visit the
Settings page of your selected workspace.  Make sure to copy the
Atomist workspace id, not the Slack workspace id.

[dashboard]: https://app.atomist.com/ (Atomist Dashboard)

### GitHub personal access token

You will need a [GitHub personal access token][token] with "repo" and
"read:org" scope.  If you do not already have one, you can [create
one][token-create].

> The "read:org" scope is needed to register the SDM with Atomist,
> since Atomist needs to know what GitHub organizations you are a
> member of.  The "repo" scope is needed for the SDM to do things like
> create pull requests, make commits after auto-fixing code, comment
> on issues, etc.

[token]: https://github.com/settings/tokens (GitHub Personal Access Tokens)
[token-create]: https://github.com/settings/tokens/new (GitHub - New personal access token)

## Configuration

When manually configuring Atomist, you can use either a user
configuration file or environment variables.  For manual configuration
to run locally, the user configuration file is recommended.  For
running in container environments, sometimes environment variables are
easier to provide.

### User configuration file

You can create a user configuration file at
`$HOME/.atomist/client.config.json` for POSIX-like systems like macOS
and GNU/Linux or `%USERPROFILE%\.atomist\client.config.json` on MS
Windows with the following contents:

```json
{
  "teamIds": [
    "WORKSPACE_ID"
  ],
  "token": "GITHUB_TOKEN"
}
```

replacing `WORKSPACE_ID` with your Atomist workspace/team ID and
`GITHUB_TOKEN` with your GitHub personal access token.

If you are on a shared system, you should make sure no one else can
access this file since the token it contains is sensitive information.
On POSIX-like systems, you can secure the file with the following
command.

```
$ chmod 600 $HOME/.atomist/client.config.json
```

### Environment variables

Prior to starting an SDM using `atomist start`, set the following
environment variables in the same shell.  Be sure to replace
`WORKSPACE_ID` with your Atomist workspace/team ID and `GITHUB_TOKEN`
with your GitHub personal access token.

```
$ export ATOMIST_TEAMS=WORKSPACE_ID
$ export ATOMIST_TOKEN=GITHUB_TOKEN
```

If you have multiple Atomist workspaces and want to run a single SDM
in multiple Atomist workspace, supply all of their IDs as a
comma-delimited list as the value of the `ATOMIST_TEAMS` environment
variable.

```
$ export ATOMIST_TEAMS=WORKSPACE_ID0,WORKSPACE_ID1,WORKSPACE_ID2
```

Once your environment variables are set, in the same shell you can
start the SDM as you normally would.

```
$ atomist start
```
