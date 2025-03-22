<%*
/*
Setup guides document processes that are non-obvious or need some personalization. As noted in my core principles: I write those guides for myself, using my personal setup and configuration. The goal is to document technical processes for personal reusability.

Usage:
- Create a new file with the project name (like "Customer Site.md")
- Hit `⌘ ⇧ N` to select this template
*/

const theName = tp.file.title.replace(/^\W+/, '')

const projectName = await tp.system.prompt(
  'Which project or environment did you set up?',
  theName
);
_%>

# <% projectName %> Setup

## Source

- %% GitHub Repo, Confluence pages, Slack conversations, ... %%<% tp.file.cursor(1) %>

## Setup Steps

```shell
# Clone the repo
cd ~/Coding/
git clone project
cd project

# Installation ...
```

## Verification 

```shell
# How can I verify the setup was successful?
```

## Related Notes

- %% Decisions, Investigations, Journal entries, ... %%
