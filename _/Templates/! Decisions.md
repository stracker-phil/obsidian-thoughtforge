<%*
const theName = tp.file.title.replace(/^!/, '')
const prefix = "! "
await tp.file.rename(prefix + theName)
_%>

# Decision: <% theName %>

## Context

%% Explain the context, environment, project, team, feature, etc %%

## Problem Statement

I explored the following options to solve ... for ...:

## Considered Options

### Option 1: {{Summary}}

Describe this option

- Pros:
- Cons:

### Option 2: {{Summary}}

Describe this option

- Pros:
- Cons:

## Decision

I chose **{{selected_option}}** because:
