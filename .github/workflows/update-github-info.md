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
    - awesome-copilot.github.com
safe-outputs:
  create-pull-request:
    allowed-files:
      - site/content/github-info.md
---

# Update GitHub information

Refresh the GitHub information on Mona's website and open a pull request for her to review.

1. Read `notes/mona-notes.md` for Mona's requirements and tone.
2. Read the current `site/content/github-info.md` so you preserve its existing style and structure.
3. Gather fresh, factual source material:
   - Use web fetch to read `https://github.blog/latest/` for recent GitHub Blog stories.
   - Use web fetch to read `https://github.blog/changelog/` for recent GitHub Changelog entries.
   - Read Awesome Copilot workflow examples from the `github/awesome-copilot` repository's `workflows/` directory. `https://awesome-copilot.github.com/workflows/` redirects to that repository, so use the GitHub repository API tools to list and read those workflow files instead of fetching the redirecting page or running shell/CLI commands.
4. Update only `site/content/github-info.md` with concise, practical highlights drawn from the sources you were able to read, preserving the file's style. Cite the source for each addition (GitHub Blog, GitHub Changelog, and Awesome Copilot workflows). Do not invent facts; use only what the sources show.
5. Make sure the update includes at least one practical Awesome Copilot workflow example with its source cited.
6. Use the `create_pull_request` safe output to open a pull request with a concise summary and verification notes for Mona. Do not write directly to the default branch.

Only skip the pull request if every source above is unreachable. If you can read any source, make a sourced update and open the pull request.
