---
# A human-friendly name of your listing
title: CI Reporter
# A short description of what your app does
description: Pastes the error output of a failing build into the relevant PR.
# The slug of your hosted app on GitHub (https://github.com/apps/YOUR-SLUG)
slug: ci-reporter
# Include a few screenshots that show your app in action
screenshots:
- https://user-images.githubusercontent.com/10660468/36135324-78809222-1058-11e8-99cd-6cc100971066.png
# The GitHub usernames of anyone who authored the app
authors: [ JasonEtco ]
# The repository where the code is located
repository: JasonEtco/ci-reporter
# The address where this app is deployed
host: https://ci-reporter-etc.herokuapp.com
---
## Usage

Simply [install the app](https://github.com/apps/ci-reporter) and watch the magic happen as your Pull Requests trigger failure statuses.

## How it works

When a build fails, the CI provider will tell GitHub (via a status). GitHub then tells **ci-reporter** about a failed status, and it'll find the part of the build that failed, then comment back on the PR.



## Configuration

You don't need any configuration for this to work in your project but you can customize a few things to fit your needs. You can create a `.github/ci-reporter.yml` file:

```yml
# Set to false to create a new comment instead of updating the app's first one
updateComment: true

# Use a custom string, or set to false to disable
before: "✨ Good work on this PR so far! ✨ Unfortunately, the [{{ provider }} build]({{ targetUrl }}) is failing as of {{ commit }}. Here's the output:"

# Use a custom string, or set to false to disable
after: "I'm sure you can fix it! If you need help, don't hesitate to ask a maintainer of the project!"
```

If you need more configuration, please [let me know in a new issue](https://github.com/JasonEtco/ci-reporter/issues/new?title=[Config]&body=Can%20you%20please%20add%20the%20___%20config%20option).



## Does it work with _____?

**ci-reporter** currently supports TravisCI and CircleCI. If you're interested in seeing support for another CI tool, please [open an issue](https://github.com/JasonEtco/ci-reporter/issues/new)!