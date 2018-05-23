# Atomist Software Delivery Machine

An Atomist [Software Delivery Machine][sdm] is a development process
in a box.  An SDM automates all steps in the flow from commit to
production, and many other actions, using the consistent model
provided by the Atomist _API for software_.  An SDM reacts to events
in your software development flow, e.g., pushes, issue creation, and
pull request reviews, automating common and desirable parts of your
software delivery flow.  It is a Node.js package that uses the
[@atomist/automation-client][automation-client] to connect to the
Atomist API.

Run it yourself and make magic happen for your team!

[sdm]: https://github.com/atomist/sdm (Atomist Software Delivery Machine Node.js Package)
[automation-client]: https://github.com/atomist/automation-client-ts (Atomist Automation Client Node.js Package)

## Prerequisites

Before you can run your own Atomist SDM, you need a few prerequisites.

### Atomist Workspace

You must have an Atomist workspace.  If you do not already have one,
you can create one following the instructions in the [getting
started][enrollment] documentation.

[enrollment]: enrollment.md (Atomist - Getting Started)

### Git

You must have the [Git CLI installed][git-download].

[git-download]: https://git-scm.com/downloads

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

If Atomist is in your Slack team, you can say `@atomist create sdm` to
create your own Software Delivery Machine based on our seed SDM, and
then clone the resulting repository.  Otherwise you can clone the
Atomist sample-sdm directly.

```
$ git clone git@github.com:atomist/sample-sdm.git
$ cd sample-sdm
$ npm install
$ npm run build
```

If you've created your own SDM, replace its clone URL in the first
command above.

### Atomist CLI

Installing the Atomist command-line interface globally will give you
quick access to useful commands.

```
$ npm install -g @atomist/automation-client
```

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

The second command does two things: records what Atomist
workspace/team you want your automations running in and creates a
[GitHub personal access token][token] with "repo" and "read:org"
scopes.

> The "read:org" scope is needed to register the SDM with Atomist,
> since Atomist needs to know what GitHub organizations you are a
> member of.  The "repo" scope is needed for the SDM to do things like
> create pull requests, make commits after auto-fixing code, comment
> on issues, etc.

The script will prompt you for your Atomist workspace/team ID, or you
can supply it using the `--team TEAM_ID` command-line option.  You can
get your Atomist team ID from the settings page for your Atomist
workspace or by typing `team` in a DM to the Atomist bot.

The script will prompt you for your GitHub credentials.  It needs them
to create the GitHub personal access token.  Atomist does not store
your credentials and only writes the generated token to your local
machine.

The Atomist API client authenticates using a GitHub personal access
token.  The Atomist API uses the token to confirm you are who you say
you are and are in a GitHub organization connected to the Slack team
in which you are running the automations.  In addition, it uses the
token when performing any operations that access the GitHub API.

If you prefer, you can also [configure manually][manual] using
environment variables.

[token]: https://github.com/settings/tokens (GitHub Personal Access Tokens)
[manual]: manual-configuration.md (Atomist - Manual Configuration)

## Starting the SDM

To start the SDM, run the following command:

```
$ atomist start
```

## Registration

The SDM automatically connects to the Atomist API, authenticates using
the token, and registers its automations.  If it works, you'll see a
banner with the name of your SDM and links to the Atomist dashboard.

Visit the dashboard URL displayed on startup to see information about
your SDM.  Click the name for a list of events and commands that your
automation will respond to.

When your automations are invoked, the log prints to your console so
you can see it go.

## Stop

Control-C will stop the client.  Restart it after code changes with
`atomist start` again.
