---
name: update-github-info
on:
  schedule: daily
  workflow_dispatch:
tools:
  edit:
  web-fetch:
network:
  allowed:
    - github.blog
    - github.com
safe-outputs:
  create-pull-request:
    allowed-files:
      - site/content/github-info.md
---

# Update GitHub information

Refresh the repository's GitHub information for Mona:

1. Read `notes/mona-notes.md` for Mona's requirements and context.
2. Use web fetch to read `https://github.blog/latest/`.
3. Use web fetch to read `https://github.blog/changelog/`.
4. Update only `site/content/github-info.md` with relevant, current information from those sources while preserving the file's existing style and structure.
5. If the file does not need any changes, report a successful no-op.
6. If the file changes, use the `create_pull_request` safe output to open a pull request with a concise summary and verification notes for Mona to review. Do not write directly to the default branch.
