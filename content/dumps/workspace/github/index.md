---
title: "GitHub"
date: 2023-07-05T13:53:36+02:00
---

## Authentication

- Install [gh](https://github.com/cli/cli#installation) cli
- Setup: `gh auth login --hostname github.company.com`
- Configure git to use it: `~/.gitconfig`
  ```toml
  [credential "https://github.company.com"]
    helper = !/usr/bin/gh auth git-credential
  ```

## Helpers

### GH Dash
- Repo: [dlvhdr/gh-dash](https://github.com/dlvhdr/gh-dash)
- `GH_HOST=github.com gh extension install dlvhdr/gh-dash` + Nerdfont
- <details><summary>Config</summary>

  ```yaml
  # file location: ~/.config/gh-dash/config.yml
  prSections:
  - title: "Dev: me"
    filters: is:open author:@me
  - title: "Maintain: Me"
    filters: is:open user-review-requested:@me -label:wip
  - title: "Maintain: TEAM"
    filters: is:open team-review-requested:ORG/TEAM -label:wip
  - title: Involved
    filters: is:open involves:@me -author:@me
  issuesSections:
  - title: My Issues
    filters: is:open author:@me
  - title: Assigned
    filters: is:open assignee:@me
  - title: Specific repo
    filters: is:open repo:ORG/REPO
  - title: Involved
    filters: is:open involves:@me -author:@me
  defaults:
    preview:
      open: true
      width: 50
    prsLimit: 20
    issuesLimit: 20
    view: prs
    layout:
      prs:
        repo:
            width: 30
        author:
            width: 15
        updatedAt:
            hidden: true
        state:
            hidden: true
        assignees:
            hidden: true
        base:
            hidden: true
        lines:
            hidden: true
        reviewStatus:
            hidden: true
      issues:
        updatedAt:
            width: 7
        repo:
            width: 15
        creator:
            width: 10
        assignees:
            width: 20
            hidden: true
        reviewStatus:
            hidden: true
    refetchIntervalMinutes: 30
  keybindings:
    issues: []
      prs:
        - key: B # b for bulldoze, a/A are taken, uppercase to not hit by mistake
          command: gh pr review {{.PrNumber}} --approve --repo {{.RepoName}}
    repoPaths: {}
    pager:
      diff: ""
  ```
  </details>
