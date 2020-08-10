A GitHub App that closes and locks new and existing issues or pull requests. It is used for repositories which do not accept issues or pull requests, such as forks or mirrors.

![](https://raw.githubusercontent.com/dessant/repo-lockdown-app/master/assets/screenshot.png)

## Supporting the Project

The continued development of Repo Lockdown is made possible thanks to the support of awesome backers. If you'd like to join them, please consider contributing with [Patreon](https://armin.dev/go/patreon?pr=repo-lockdown&src=app), [PayPal](https://armin.dev/go/paypal?pr=repo-lockdown&src=app) or [Bitcoin](https://armin.dev/go/bitcoin?pr=repo-lockdown&src=app).

## Usage

1. **[Install the GitHub App](https://github.com/apps/repo-lockdown)** for the intended repositories
2. Create `.github/lockdown.yml` based on the template below
3. New issues and/or pull requests will be handled as they are opened, while existing ones will begin to be processed within an hour

**If possible, install the app only for select repositories. Do not leave the `All repositories` option selected, unless you intend to use the app for all current and future repositories.**

#### Configuration

Create `.github/lockdown.yml` in the default branch to enable the app, or add it at the same file path to a repository named `.github`. The file can be empty, or it can override any of these default settings:

```yaml
# Configuration for Repo Lockdown - https://github.com/dessant/repo-lockdown-app

# Skip issues and pull requests created before a given timestamp. Timestamp must
# follow ISO 8601 (`YYYY-MM-DD`). Set to `false` to disable
skipCreatedBefore: false

# Issues and pull requests with these labels will be ignored. Set to `[]` to disable
exemptLabels: []

# Comment to post before closing or locking. Set to `false` to disable
comment: false

# Label to add before closing or locking. Set to `false` to disable
label: false

# Close issues and pull requests
close: true

# Lock issues and pull requests
lock: true

# Limit to only `issues` or `pulls`
# only: issues

# Optionally, specify configuration settings just for `issues` or `pulls`
# issues:
#   label: wontfix

# pulls:
#   comment: >
#     This repository does not accept pull requests, see the README for details.
#   lock: false

# Repository to extend settings from
# _extends: repo
```
