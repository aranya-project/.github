# How To Contribute To Aranya

Thank you for your interest in contributing to Aranya!

SpiderOak is looking forward to contributions from the open-source community.

## Project Documentation

Before contributing, we recommend that you spend some time getting familiar with the Aranya project documentation:
[README.md](README.md)
[overview.md](docs/overview.md)
[walkthrough.md](docs/walkthrough.md)

Aranya is primarily written in Rust.
We recommend that contributors learn Rust first:
- Overview: https://www.rust-lang.org/learn
- "The Book": https://doc.rust-lang.org/book/
- Standard Library API: https://doc.rust-lang.org/std/index.html
- Rust by Example: https://doc.rust-lang.org/stable/rust-by-example/
- Playground (test and share snippets): https://play.rust-lang.org/
- Async: https://rust-lang.github.io/async-book/
- Useful third-party libraries: https://blessed.rs

## Our Roadmap

Coming soon.

The development roadmap will be a way for SpiderOak to share planned future changes with the development community.

## Project Management

SpiderOak uses an Agile development process to develope Aranya.

This GitHub project contains a SCRUM board that plans effort in 2-week sprints:
https://github.com/orgs/aranya-project/projects/1

## Development Environment Setup

Install Rust:
https://www.rust-lang.org/tools/install

Install `cargo make`:
`cargo install cargo-make`

Keep your toolchain updated by periodically running:
`rustup update`

Install your favorite IDE to edit the source code.

If using VSCode, we recommend these settings to automatically format and lint saved files:
```
// Automatically format when saving, for all languages
"editor.formatOnSave": true,
// Or just format for Rust.
"[rust]": { "editor.formatOnSave": true },

// Use nightly rustfmt so we can use unstable config options.
"rust-analyzer.rustfmt.extraArgs": ["+nightly"],

// Enable clippy linter for extra warnings in-editor
"rust-analyzer.check.command": "clippy",
```

## How To Report A Security Bug

Refer to [SECURITY.md](SECURITY.md) for reporting security bugs.

## How To Report A Bug

Create a new issue here for the bug:
https://github.com/aranya-project/aranya/issues

More information on creating GitHub issues can be found here:
[Creating A GitHub Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/creating-an-issue)

Add the `bug` label to the issue.

The team will now be able to view and respond to the bug report.

## How To Request A Feature

To share an idea for a new feature, create a discussion here:
https://github.com/orgs/aranya-project/discussions/categories/ideas

Once the development community has shown interest in the idea, it's time to create an issue.

Create a new issue here for the feature request:
https://github.com/aranya-project/aranya/issues

More information on creating GitHub issues can be found here:
[Creating A GitHub Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/creating-an-issue)

Add any relevant labels to the issue.

If you're planning to open a pull request for the feature, assign yourself to the issue.

## How To Submit Changes

First, clone the repository:
`git clone https://github.com/aranya-project/aranya`
or
`git clone git@github.com:aranya-project/aranya.git`

Create a new branch for your changes:
`git checkout -b <branch>`

You can alternatively create a development branch directly from an existing issue:
[Creating branch from existing issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/creating-a-branch-for-an-issue)

Make some changes using your favorite IDE.

Before pushing commits, you can run a few commands to see if the changes are good before running them on the CICD pipeline:
```
cargo make fmt
cargo make build
cargo make unit-tests
cargo make correctness
```

Commit the changes to the branch:
```
git add .
git commit -m "commit message"
git push
```

Note: when pushing commits for the first time, you may need:
`git push --set-upstream origin <branch>`

Open a pull request here for your branch:
https://github.com/aranya-project/aranya/pulls

More information on opening pull requests can be found here:
[Pull Requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)

Request code review from relevant code owners [CODEOWNERS.md](CODEOWNERS.md).

More information on code owners can be found here:
[Code Owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)

The following criteria are used to determine if a pull request can be merged into the protected `main` branch:
- Code has been properly formatted (`cargo make fmt`)
- Lint checks are passing
- Code can be compiled
- Unit tests are passing (`cargo make unit-tests`)
- Integration tests are passing
- All GitHub Actions CICD (Continous Integration Continous Delivery) jobs have passed.
- All discussions on the pull request have been addressed and resolved
- Pull request has been reviewed and approved by relevant code owners on the development team at SpiderOak [CODEOWNERS.md](CODEOWNERS.md).

## Github Issue Creation Guidelines

Create a new issue here for the feature request:
https://github.com/aranya-project/aranya/issues

More information on creating GitHub issues can be found here:
[Creating A GitHub Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/creating-an-issue)

Try to fill out as much information as possible when creating an issue:
- Title
- Description
- Assignee(s)
- Labels
- Project(s)
- Milestone (if applicable)
- Development branch(es)
- Status (e.g. backlog)
- Story point estimate
- Links to other relevant issues, discussions, or documentation

Here are some suggestions for how to write good user stories in issue descriptions:
https://www.easyagile.com/blog/how-to-write-good-user-stories-in-agile-software-development/

Here are some guidelines for adding story point estimates to issues:
| Story Point Estimate | Amount of Effort Required | Estimated Time Needed                    | Example scenarios                          |
| -------------------- | ------------------------- | ---------------------------------------- | ------------------------------------------ |
| 0                    | Tiny                      | Minutes to hours                         | Task in review or typos to fix             |
| 1                    | Minimum effort            | A day or less                            | Small bug or fixes from review comments    |
| 2                    | Slight effort             | 2-3 days                                 | Bug fix, cleanup, test                     |
| 3                    | Mild effort               | A week or less                           | Small feature                              |
| 5                    | Moderate effort           | A sprint or less                         | Regular feature                            |
| 8                    | High effort               | More than a sprint. A few weeks.         | Implementing features of a multi-part spec |
| 13                   | Maximum effort            | Too high to know. Requires more research | Design and implementation of a new feature |

## Pull Request Review Guidelines

Please keep pull request reviews professional and informative.

We encourage developers to open draft PRs early in the development cycle.
This allows other developers to be aware of changes and start providing feedback.
Once a PR is ready for more formal review, it can be marked as "Ready For Review".

A PR can typically be marked as "Ready For Review" when it meets the following criteria:
- Code is formatted.
- Code is compiling.
- Lints have been resolved.
- CICD tests are passing.
- Intended functionality as been implemented.
- Relevant unit and/or integration tests have been added.
- Relevant documentation has been updated.

The purpose of reviewing PRs is to:
- Improve code quality (functionality, maintainability, readability, thread-safety, etc.).
- Catch potential security bugs before they are introduced.
- Allow developers with knowledge of various parts of the project or various domain knowledge to provide feedback.
- Verify that CICD tests/builds are passing.
- Ensure that the implementation aligns with the intended vision for the issue.
- Distribute knowledge of various system components across the team.
- Determine whether a specification needs to be written before merging the implementation.
- Ensure that coding standards are followed.
- Encourage more documentation where needed.
- Evaluate architectural properties (performance, scalability, reliability, modularity, etc.).

We differentiate between various types of feedback:
- Requesting a change (must be changed before approving a PR).
- Comments. Suggestions for improving the PR.
- Nitpick. A minor issue or preference. Will not prevent a PR from being merged. Nitpick comments are prefaced with a "nit:".

In general, reviewers are assigned to a PR based on the following criteria:
- Relevant domain/language knowledge.
- Past experience working on similar issues.
- Past experience working on a particular part of the codebase.
- Interest in working on or learning about a particular part of the codebase.
- It is not practical for every team member to review every PR. And too many reviewers could cause the review cycle to take too much time. Generally, 1 primary reviewer and 1 other person to check for obvious errors or funny business is recommended. Feel free to read PRs you are not assigned as a reviewer on and comment with questions/feedback.

## Testing

To run the unit tests:
`cargo make unit-tests`

Note: if unit tests are not passing, a pull request cannot be merged.

## Code Of Conduct

Here's a link to our code of conduct:
[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)

## Style Guide And Coding Conventions

We use `rustfmt` to automatically format code:
https://github.com/rust-lang/rustfmt

Run this command to format code before pushing code to a development branch:
`cargo make fmt`

## Asking For Help

Our development team would be happy to assist with any questions you may have.

Please open a Q&A discussion for any general questions:
https://github.com/orgs/aranya-project/discussions/categories/q-a

You can also ask for help in a PR comment or in a discussion on the associated GitHub issue.
