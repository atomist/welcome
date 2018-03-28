# Get started with Atomist

Atomist is here to help you smooth your development flow.
Start with our web console; see consolidated event notifications. Add ChatOps with Slack if you have it. Spawn your own software delivery machine, and integrate with other tools as you choose. 

This page describes enrollment with Atomist.

## Prerequisites

You need a GitHub user, because we use GitHub authentication.

For the whole shebang, it helps to have a GitHub organization and a Slack team. (You can create these for free and have full admin powers, if you want to experiment.)

## Hello Atomist

Visit [atomist.com]() and click "Sign Up." You'll be asked to authenticate with GitHub.

Here, you'll create a new Atomist workspace. Associate a GitHub organization or some repositories
to start getting events; Atomist will ask your permission to create the webhook. <!-- @willgardella want to put more here? how about a picture? -->

The Atomist web dashboard will show you events from GitHub.

## Add Slack (optional)

Click "Add to Slack" <!-- @willgardella where is it? -->
to get the Atomist bot in your Slack team. Once you do that, the bot will greet you and walk you through linking channels to GitHub repositories for notifications. You can also run chat commands in any channel if you `/invite @atomist`.

<!-- TODO: picture of a great notification -->

<!-- TODO: invite your friends -->

# Make it your own

Respond to your own events and commands by creating your Software Delivery Machine: 
type `@atomist create sdm` in Slack, and see [the SDM reference implementation](https://github.com/atomist/github-sdm).