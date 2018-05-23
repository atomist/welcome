# Get started with Atomist

Atomist is here to help you smooth your development flow.  Start with
our web console; see consolidated event notifications. Add ChatOps
with Slack if you have it. Spawn your own software delivery machine,
and integrate with other tools as you choose.

This page describes enrollment with Atomist.

## Prerequisites

You must have a Git source code management account, either GitHub.com,
GitHub Enterprise (GHE), or BitBucket.  If you want to use Atomist
with GHE or BitBucket, please [contact
Atomist](mailto:support@atomist.com).  The remainder of these
instructions assume you have a GitHub.com account.  If you do not
already have a GitHub.com account, you can [create
one][github-create].

For the whole shebang, it helps to have a GitHub organization and a
Slack team.  You can create these for free and have full admin powers,
if you want to experiment.

[github-create]: https://github.com/join (Join GitHub)

## Hello Atomist

Visit [atomist.com][www] and click "Sign Up."  You'll be asked to
authenticate with GitHub.

Once you've authenticated, you'll create a new Atomist workspace.
Associate a GitHub organization or some repositories with the Atomist
workspace to start getting events.  Atomist will ask your permission
to create the needed webhook(s).

The Atomist web dashboard will show you events, e.g., new commits and
issue and pull request activity, from GitHub.

[www]: https://atomist.com/ (Atomist - How Teams Deliver Software)

## Add Slack (optional)

Atomist has a powerful [Slack][slackhq] application, allowing you to
see and act on your development activity right in Slack.  Slack is not
a requirement for using Atomist, but if you try it, you'll probably
like it.  If you do not have access to a Slack team, it is easy to
[create your own][slack-team].

Click the "Add to Slack" button to get the Atomist bot in your Slack
team.

<p align="center">
 <a href="https://atm.st/2wiDlUe">
  <img alt="Add to Slack" height="50" width="174" src="https://platform.slack-edge.com/img/add_to_slack@2x.png" />
 </a>
</p>

Once you do that, the Atomist bot will greet you and walk you through
linking channels to GitHub repositories for notifications.  You can
also run chat commands in any channel if you `/invite @atomist`.

<p align="center">
 <img alt="Atomist Bot Message" height="232" width="595" src="https://raw.githubusercontent.com/atomist/welcome/master/images/bot-message.png" />
</p>

[slackhq]: https://slack.com/ (Slack)
[slack-team]: https://slack.com/get-started#create (Create a Slack Team)

<!-- TODO: invite your friends -->

## Make it your own

Respond to your own events and commands by creating your Software
Delivery Machine: type `@atomist create sdm` in Slack.  See the
[running an SDM][run] documentation to learn how to run your own Software
Delivery machine!

<p align="center">
 <img alt="Software Delivery Machine Lifecycle" height="833" width="541" src="https://raw.githubusercontent.com/atomist/welcome/master/images/sdm.png" />
</p>

[run]: run.md (Atomist - Running a Software Delivery Machine)
