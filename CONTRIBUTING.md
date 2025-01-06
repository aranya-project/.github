# How To Contribute To Aranya

Thank you for your interest in contributing to Aranya!

SpiderOak is looking forward to contributions from the open-source community.

## Project Documentation

Before contributing, we recommend that you spend some time getting familiar with the Aranya project documentation:
[README.md](README.md)
[overview.md](docs/overview.md)
[walkthrough.md](docs/walkthrough.md)

Aranya is primarily written in Rust. For useful references on learning Rust, see the [Resources](#resources) section.

## Project Management

SpiderOak uses an Agile development process to develop Aranya.

This GitHub project contains a SCRUM board that plans effort in 2-week sprints:
https://github.com/orgs/aranya-project/projects/1

## Development Environment Setup

Install Rust:
https://www.rust-lang.org/tools/install

Install `cargo make`:
`cargo install cargo-make`

Keep your toolchain updated by periodically running:
`rustup update`

The Minimum Supported Rust Version (MSRV) can be found by opening a repository's top-level `Cargo.toml` file and looking for the following line:
`rust-version = "<Rust version>"`

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

A bug reporting template has been created to make it easier to submit bug reports:
[Bug template](.github/ISSUE_TEMPLATE/bug_template.yml)

The team will now be able to view and respond to the bug report.

## How To Request A Feature

To share an idea for a new feature, create a discussion here:
https://github.com/orgs/aranya-project/discussions/categories/ideas

Once the development community has shown interest in the idea, it's time to create an issue.

Create a new issue here for the feature request:
https://github.com/aranya-project/aranya/issues

More information on creating GitHub issues can be found here:
[Creating A GitHub Issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/creating-an-issue)

A feature request template has been created to make it easier to request new features:
[Feature request template](.github/ISSUE_TEMPLATE/feature_template.yml)

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

A pull request template has been created to make it easier to open new pull requests:
[Pull request template](.github/PULL_REQUEST_TEMPLATE/pull_request_template.yml)

Request code review from relevant code owners [CODEOWNERS.md](CODEOWNERS.md).

More information on code owners can be found here:
[Code Owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)

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

## Resources

Rust Resources:
- Overview: https://www.rust-lang.org/learn
- "The Book": https://doc.rust-lang.org/book/
- Standard Library API: https://doc.rust-lang.org/std/index.html
- Rust by Example: https://doc.rust-lang.org/stable/rust-by-example/
- Playground (test and share snippets): https://play.rust-lang.org/
- Async: https://rust-lang.github.io/async-book/
- Useful third-party libraries: https://blessed.rs
