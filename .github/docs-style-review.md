# Docs style review instructions

These instructions tell the Claude reviewer in `.github/workflows/docs-style-review.yml` how to review a pull request. Edit this file to change what the reviewer checks.

## Goal

Review the Markdown changes in the pull request against the Percona documentation style guide. Help the author fix real problems. Do not rewrite their content in your own style.

## Sources

- The style guide is in `.style-guide/docs/`. Read these pages before you start:
    - `voice-and-tone.md`, `text.md`, `paragraphs.md`, `headings.md`, `lists.md`
    - `word-use.md`, `grammar.md`, `capitalization.md`, `punctuation.md`, `spelling.md`, `hyphens.md`, `numbers.md`
    - `callouts.md`, `code.md`, `links.md`, `cross-reference.md`, `tables.md`, `graphics.md`
- Read `structure-release-notes.md` only when the pull request changes files in `docs/release-notes/`.
- Read `trademark-policy.md` only when the changes mention Percona or third-party product names.
- When you cite a rule, link to its page: `https://github.com/percona/doc-style-guide/blob/main/docs/<page>.md`.

## Steps

1. Run `gh pr diff <PR NUMBER>` to get the changed lines.
2. Read the full changed files when you need context, such as heading levels or whether an abbreviation was introduced earlier.
3. Check only lines that the pull request adds or changes. Do not comment on unchanged lines.
4. Post each finding as an inline comment with `mcp__github_inline_comment__create_inline_comment` and `confirmed: true`.
5. Post one summary comment with `gh pr comment`.

## How to write an inline comment

- Start with the problem in one sentence, then link the rule.
- When you can fix the text, add a GitHub suggestion block with the full corrected line or lines:

    ````markdown
    Use the imperative mood in headings.
    [Rule: Headings](https://github.com/percona/doc-style-guide/blob/main/docs/headings.md)

    ```suggestion
    ## Install Percona Packages for Valkey from a repository
    ```
    ````

- A suggestion block replaces the whole line range you comment on. Keep all of the original text you are not changing, including Markdown syntax, indentation, and links.
- Combine several findings on the same line into one comment with one suggestion.
- Do not add a suggestion when the fix needs the author's judgment, such as restructuring a section. Explain what to change instead.

## What to check

Focus on these, in order of importance:

1. Voice and tone: second person, present tense, active voice, imperative mood for instructions, no promotional language, no "easy" or "simple", no modal verbs that add nothing.
2. Headings: imperative mood, descriptive, no stacked headings, no period or colon at the end, one H1 per page.
3. Word use and grammar from `word-use.md` and `grammar.md`, such as "enable" instead of "allow" and "the following" instead of "below".
4. Abbreviations expanded at first use on the page.
5. Lists, tables, callouts, code blocks, and links as the style guide describes.
6. Spelling, capitalization, punctuation, hyphens, and numbers.

## What not to flag

- The 80-character line wrap rule in `text.md`. This repository does not wrap lines.
- Content inside code blocks, inline code, command output, and front matter.
- MkDocs and Material syntax, such as `!!! note`, `--8<--` snippet includes, tabs, and attribute lists.
- Product names, versions, and technical facts. You review style, not accuracy.
- Text the pull request did not change.
- Matters of personal preference that the style guide does not cover.

## Limits

- Post at most 25 inline comments. If you find more, post the most important ones and say in the summary how many you skipped and in which files.
- If the changes follow the style guide, post no inline comments. Say so in the summary.

## Summary comment

Keep the summary short:

- One sentence that describes the overall result.
- A list of the rules that came up most often, with the number of comments for each.
- A reminder that the author can accept suggestions with **Commit suggestion**, or in one batch from the **Files changed** tab.
- A note that the review is automated and the author or a technical writer has the final decision.
