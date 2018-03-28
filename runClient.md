# Running an Atomist automation client

An automation client contains functions that trigger based on events (like code push or repository creation) or commands (in Slack). 
It is a Node service that includes [@atomist/automation-client](https://github.com/atomist/automation-client-ts). It hooks up to the Atomist API. 

Run it locally, and make magic happen for your team!

## Prerequisites

- `git`

### Node.js

You will need to have [Node.js][node] installed.  To verify that the
right versions are installed, please run:

```
$ node -v
v8.4.0
$ npm -v
5.4.1
```

The `node` version should be 8 or greater and the `npm` version should
be 5 or greater.

[node]: https://nodejs.org/ (Node.js)

### Cloning the repository and installing dependencies

It's easiest to start from a sample automation client and modify it.

If Atomist is in your Slack team, you can say `@atomist create sdm` (for a full Software Delivery Machine). Then clone the repository it creates.

Or clone directly:

```
$ git clone git@github.com:atomist/github-sdm.git
$ cd github-sdm
$ npm install
$ npm run build
```

### Handy command line

Installing the client globally will give you quick access to useful shortcuts.

`npm install -g @atomist/automation-client`

### Configuring your environment

If this is the first time you will be running an Atomist API client
locally, you should first configure your system using the `atomist`
script:

```
$ atomist config
```

or if you didn't install it globally:

```
$ `npm bin`/atomist config
```

The script does two things: records what Slack team you want your
automations running in and creates
a [GitHub personal access token][token] with "repo" and "read:org"
scopes.

The script will prompt you for you Slack team ID, or you can supply it
using the `--slack-team TEAM_ID` command-line option.  You must run
the automations in a Slack team of which you are a member.  You can
get the Slack team ID by typing `team` in a DM to the Atomist bot.

The script will prompt you for your GitHub credentials.  It needs them
to create the GitHub personal access token.  Atomist does not store
your credentials and only writes the generated token to your local
machine.

The Atomist API client authenticates using a GitHub personal access
token.  The Atomist API uses the token to confirm you are who you say
you are and are in a GitHub organization connected to the Slack team
in which you are running the automations.  In addition, it uses the
token when performing any operations that access the GitHub API.

If you prefer, you can also [configure manually](manualConfiguration.md) with environment variables.

[token]: https://github.com/settings/tokens (GitHub Personal Access Tokens)


## Starting up the automation-client

To start the client, run the following command:

```
$ atomist start
```

## Registration

The client connects to the Atomist API. 
If it works, you'll see a banner with the name of your automation, and links to the Atomist dashboard.

Visit the Url displayed on startup, and see your automation client. Click on it for a list of event subscriptions and commands that your automation will respond to.

When your automations are invoked, the log prints to your console so you can see it go.

## Stop

Control-C will stop the client. Restart it after code changes with `atomist start` again. (Or `npm run build; npm start`)
