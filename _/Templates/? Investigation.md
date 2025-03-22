<%*
/*
This template simply logs my debugging steps. Often, a bug or incorrect behavior tends to repeat after a while or in certain situations. These logs help me to document my discovery journey, and build on past insights when encountering an issue again.

Usage:
- Create a new file with the topic name (like "Card payment issues.md")
- Hit `⌘ ⇧ N` to select this template

Note: This template renames the note, and adds the prefix "? "
*/
const theName = tp.file.title.replace(/^\W+/, '')
const prefix = "? "
await tp.file.rename(prefix + theName)
_%>

# <% theName %>

## Context

%% Which project, feature, environment, website or configuration is affected? %%<% tp.file.cursor(1) %>

## Symptoms

- %% what do you see, what happens? Include some alternative descriptions to help me find this note again in the future %%

## Investigation

### Attempt 1
Steps: 
Notes and result

### Attempt 2
Steps: 
Notes and result

## Solution

```shell
How I solved the issue
```

## References

- %% Slack, GitHub, other notes, ... whenever I relate to this note, I want to add a reference to the relevant journal note here as an evidence that this investigation is still current and valid %%
