# Atomist Open Source FAQ

We want the Atomist open source projects to be used as broadly as
possible, by as many people as possible. We also want these projects
to be able to grow to support new uses that we haven't even conceived
of, but you have. The best way to support those goals is to make these
projects open source.

We are no strangers to open source, having created and shepherded
the [Spring Framework][spring]. Of course, we also use quite a bit of
open source in building and operating Atomist. So, we understand the
desire and need for open access to technologies.

[spring]: https://en.wikipedia.org/wiki/Spring_Framework (Spring Framework)

## What does the GPL licensing mean to me as a user?

While most Atomist-created open source software is licensed under the
[Apache License, Version 2.0][asl], certain open source code is made
available under [GPLv3 with the Classpath Exception][gpl]. We chose
GPL because it embodies the free and open access we intend for these
components.

*   If you use these GPL-licensed projects to write your code, e.g.,
    as dependencies in your project, it's pretty simple. Just see the
    ["Classpath Exception"][cp] below.
*   If you're making modifications to and/or distributing these
    GPL-licensed projects, you'll need to open source the
    modifications under the same license and preserve license and
    copyright notices (see the [LICENSE][gpl] for full details).

[asl]: https://www.apache.org/licenses/LICENSE-2.0 (Apache License, Version 2.0)
[gpl]: licenses/GPLv3cp (GPLv3 with Classpath Exception)
[cp]: #what-is-the-classpath-exception

## What is the "Classpath Exception"

If you haven't seen it before, we inlcude the classpath exception to
clarify that code you write that "links" to any of the GPL code is
exempted from the GPL obligations. In plain English, it means that
things you write remain your property to license and do with as you
choose. Obviously, we don't intend to require you to open source the
projects you write for your own or your company's use. This exception
makes that clarification and was originally [introduced in Java
SE/EE][cpe] for the same purpose.

[cpe]: https://en.wikipedia.org/wiki/GPL_linking_exception#The_classpath_exception (Classpath Exception)

## How can I contribute?

Thanks for considering contributing to Atomist open source projects!
Please see our [Contribution Guidelines][contrib].

[contrib]: CONTRIBUTING.md (Contributing to Atomist Open Source Projects)

## How do I report bugs?

If you think you have found a bug in an Atomist open source project,
you can either head over to the [Atomist Community Slack][slack]
`#support` channel and let us know or you can file an issue on the
appropriate GitHub repository. The [contributing guidelines][contrib]
provide more detailed instructions, but in short, if you are unsure
about the nature of the bug or where to create an issue, your best bet
is the `#support` channel in the Atomist Community Slack. If you have
the detail needed to create an issue in the right repository, review
the open issues and make sure you are on the latest version before
creating an issue.

[slack]: https://join.atomist.com (Atomist Community Slack)

## How do I report bad behavior?

We strive to foster a diverse and welcoming community at Atomist, both
in our company and our larger community. We provide what we hope is a
clear [Code of Conduct][conduct] and take all violations of this code
seriously. If you witness or are a victim of any behavior from anyone
that violates this Code of Conduct, please report it to us immediately
at [code-of-conduct@atomist.com][email].

[conduct]: CODE_OF_CONDUCT.md (Atomist Code of Conduct)
[email]: mailto:code-of-conduct@atomist.com

## Other Questions?

We'll continue updating this document as new questions come in. Please
join the [Atomist Community Slack][slack] to search and post questions
there. Thanks for using Atomist open source and helping make it
better!
