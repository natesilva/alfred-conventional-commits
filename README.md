# alfred-conventional-commits

> Build Git commit messages according to the Conventional Commits format

## Install

-   You need to have [Alfred](https://www.alfredapp.com) installed with the Powerpack enbled.

Download the workflow from the [Release Page](https://github.com/natesilva/alfred-conventional-commits/releases) and double-click.

## What is this?

[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) is a way to write Git messages in a standard format that makes it easier to read for humans _and_ computers.

You can optionally use a publishing system like [semantic-release](https://semantic-release.gitbook.io/semantic-release/), which uses the commit messages to build a changelog and can increment version numbers and publish your NPM module automatically.

We use the [Angular “flavor”](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type) of Conventional Commits.

## How do I use it?

1. Start the workflow.
    - By default you can invoke Alfred and then type `conv`. See [Settings](#settings) for other ways to run the workflow.
2. You’ll be guided step-by-step to write your commit message.
3. The final message will be on the clipboard. Paste it into your Git application and commit!

## Examples

Each message begins with a **type**. We support the [Angular types](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#type): `build`, `ci`, `docs`, `feat`, `fix`, `perf`, `refactor`, `style`, and `test`.

Then there’s a **scope** in parentheses that identifies the component or part of your code that was modified. This is optional.

Then there may be an `!` exclamation point, which indicates that this is a _breaking change_. If you are using [semantic-release](https://semantic-release.gitbook.io/semantic-release/) this can trigger a major version number bump.

Then there’s a `:` colon, followed by the description (your commit message).

Any commit message can be prefixed with a standard **emoji**. This is **optional**. If you never want emoji, they can be turned of (see [Settings](#settings)).

Some examples of commit messages are:

-   `refactor!: update to use a new version of Node`
    -   A breaking change
-   `refactor(widget)!: ♻️ update to use a new version of Node`
    -   A breaking change to the widget component (with optional emoji)
-   `feat: ✨ add support for unicorns`
    -   Add a new feature (with optional emoji)
-   `fix: reticulate splines correctly`
    -   Fix a bug

## Settings

To customize the workflow, open Alfred’s preferences and select Workflows. Then select the Conventional Commits workflow. Here are the things you can customize:

Click the **[x]** button in the upper-right corner of Alfred to set the following:

-   **useEmoji** can be set to `ask`, `always`, or `never`.
    -   `ask` will ask each time if you want an emoji
    -   `always` will always add an emoji
    -   `never` will never add an emoji
-   **useScope** can be set to `yes` or `no`.
    -   `yes` will show the scope prompt. You can leave it blank if you don’t want a scope for this particular commit message.
    -   `no` will skip the scope prompt. This is useful if your organization never uses the scope feature.

Double-click the following boxes to configure them:

-   **Keyword**: The default Alfred keyword to trigger the workflow is `conv`.
-   **Hotkey**: Use this to set a hotkey that triggers the workflow.
-   **Snippet**: Use this to configure a [snippet trigger](https://www.alfredapp.com/help/workflows/triggers/snippet/). For example, if you set the snippet keyword to `conv` and the trigger to `\\`, then the workflow will be triggered when you type `\\conv` **in any text field in any application**, such as within the message field of your Git application.
