# Contributing to OS-Climate
**Thank You for Contributing to OS-Climate!**

**This guide explains how to:** 

* Ensure your changes are accepted
* Work on the OS-Climate code base and/or contribute data
* Get help if you encounter trouble

## Before you start

Before starting to work on a feature or a bug fix, please open an issue to discuss the use case or bug with us. This can save everyone a lot of time and frustration.

For any non-trivial change, we need to be able to answer these questions:

* Why is this change done? What's the use case?
* For user facing features, what will the API look like?
* What test cases should it have? What could go wrong?
* How will it roughly be implemented? We'll happily provide code pointers to save you time.

We may ask you to answer these questions directly in the GitHub issue or (for large changes) in a shared Google Doc.

### Security vulnerabilities

Do not report security vulnerabilities to the public issue tracker. Send an email to security@os-climate.org. Follow our [Security Vulnerability Disclosure Policy](To be provided)

### Follow the Code of Conduct

Contributors must follow the Code of Conduct outlined at [https://lfprojects.org/policies/code-of-conduct/](https://lfprojects.org/policies/code-of-conduct/).

### Additional help

If you run into any trouble, please reach out to us on the issue you are working on or via slack: join os-climate.slack.com https://join.slack.com/t/os-climate/shared_invite/zt-14d7z1q78-gf68YdWxcaDcB2gKnVJDvg.

## Setting up your development environment
To be provided

## Making your change

### Code change guidelines

All code contributions should contain the following:

* Create unit tests using XXX for new classes or methods that you introduce.
* Create integration tests that exercise a build for the bug/feature. 
* Annotate tests that correspond to a bug on GitHub.
* Add documentation to the appropriate Docs folder
* For new features, the feature should be mentioned in the [Release Notes](to be provided).

### Creating commits and writing commit messages

The commit messages that accompany your code changes are an important piece of documentation. Please follow these guidelines when creating commits:

* [Write good commit messages.](https://cbea.ms/git-commit/#seven-rules)
* [Sign off your commits](https://git-scm.com/docs/git-commit#Documentation/git-commit.txt---signoff) to indicate that you agree to the terms of [Developer Certificate of Origin](https://developercertificate.org/). We can only accept PRs that have all commits signed off.
* Keep commits discrete. Avoid including multiple unrelated changes in a single commit.
* Keep commits self-contained. Avoid spreading a single change across multiple commits. A single commit should make sense in isolation.

### Testing changes

After making changes, you can test your code:

1. Run tests (steps to be provided)

2. Install locally and try out a change in behavior manually (steps to be provided. 

Run XXX before submitting your change because this will help catch code style issues.

### Submitting Your Change

After you submit your pull request, a OS-Climate developer will review it. It is normal for this to take several iterations, so don't get discouraged by change requests. They ensure the high quality that we all enjoy.

## Useful tips

### Debugging

To be provided.

### Fixing DCO failures/Signing Off Commits After Submitting a Pull Request

You must agree to the terms of [Developer Certificate of Origin](https://developercertificate.org/) by signing off your commits. We automatically verify that all commit messages contain a `Signed-off-by:` line with your email address. We can only accept PRs that have all commits signed off.

If you didn't sign off your commits before creating the pull request, you can fix that after the fact.

To sign off a single commit:

`git commit --amend --signoff`

To sign off one or multiple commits:

`git rebase --signoff origin/master`

Then force push your branch:

`git push --force origin test-branch`

### Useful tools to make doing DCO signoffs easier
There are a number of great tools out there to manage DCO signoffs for developers to make it much easier to do signoffs.

* DCO command line tool, which let's you do a single signoff for an entire repo ( https://github.com/coderanger/dco )
* GitHub UI integrations for adding the signoff automatically ( https://github.com/scottrigby/dco-gh-ui )
* Chrome - https://chrome.google.com/webstore/detail/dco-github-ui/onhgmjhnaeipfgacbglaphlmllkpoijo
* Firefox - https://addons.mozilla.org/en-US/firefox/addon/scott-rigby/?src=search

## Our thanks

We deeply appreciate your effort toward improving OS-Climate! You work is vital towards overcoming data & analytics barriers which block investments needed to meet Paris Climate Accord goals! For any contribution, large or small, you will be immortalized in the release notes for the version you've contributed to.

