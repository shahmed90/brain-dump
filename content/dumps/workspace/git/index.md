---
title: "Git"
date: 2023-07-05T14:13:32+02:00
---

## Configuration

- Don't merge when pulling: `git config --global pull.ff only`
- Config based on directory:
  ```toml
  [includeIf "gitdir:~/work/"]
    path = .gitconfig-work
  ```
- Alias
  ```toml
  [alias]
    ls = log --oneline --graph --decorate
    ll = log --relative-date --pretty=format:'%h %Cblue%ad%Creset %an %Cgreen%s%Creset'
    co = checkout
  ```
- Template repo:
  - Config:
    ```toml
    [init]
      templateDir = ~/.git-template
    ```
  - Create contents in that directory as it would be `.git`
    - Set default pre-commit hooks in `~/.git-template/hooks/pre-commit`


## Helpers

### diff-so-fancy
- Repo: [so-fancy/diff-so-fancy](https://github.com/so-fancy/diff-so-fancy)
- Configure git to use it: `~/.gitconfig`
  ```toml
  [core]
    pager = diff-so-fancy | less --tabs=4 -RFX
  ```
