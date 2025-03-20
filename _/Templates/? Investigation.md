<%*
const theName = tp.file.title.replace(/^\?\s*/, '')
const prefix = "? "
await tp.file.rename(prefix + theName)
_%>

# <% theName %>

## Context

%% Which project, feature, environment, website or configuration is affected? %%

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
