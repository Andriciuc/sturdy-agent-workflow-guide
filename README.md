# sturdy-agent-workflow-guide
This repo focuses on testing workflow pipelines using agents and actions. It's a learning repo, expect it to be messy.

## Docs style review

When a pull request changes `.md` files in `docs`, a Claude agent reviews the changes against the [Percona documentation style guide](https://github.com/percona/doc-style-guide). It posts inline comments with suggested fixes and one summary comment.

- Workflow: `.github/workflows/docs-style-review.yml`
- Reviewer instructions: `.github/docs-style-review.md`
- Sample pages to change in test pull requests: `docs/`

The review runs when a pull request is opened, reopened, or marked as ready for review. To run it again after you push changes, remove and add the `style-review` label.

### Set up the review

1. Install the [Claude GitHub app](https://github.com/apps/claude) on this repository.
2. Run `claude setup-token` with a Claude Pro or Max account, and add the token as a `CLAUDE_CODE_OAUTH_TOKEN` secret in **Settings** > **Secrets and variables** > **Actions**. Reviews count toward your plan's usage limits.
3. Create a `style-review` label in **Issues** > **Labels**.

## Link check

When a pull request changes `.md` files in `docs` or the README, [lychee](https://github.com/lycheeverse/lychee-action) checks every link and fails the check if one is broken. It runs again on every push to the pull request. To skip a link, add a pattern to `.lycheeignore`.

- Workflow: `.github/workflows/link-check.yml`
