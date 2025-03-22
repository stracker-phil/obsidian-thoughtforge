<%*
/*
I found myself frequently doing the same research every few months. To remember why I made a decision, or what options I did consider in the research, I created this template.

Usage:
- Create a new file with the topic name (like "Switch to TypeScript.md")
- Hit `⌘ ⇧ N` to select this template

Note: This template renames the note, and adds the prefix "! "
*/
const theName = tp.file.title.replace(/^\W+/, '')
const prefix = "! "

let theDecision = await tp.system.prompt(
  'Which decision did you make?',
  theName
)
await tp.file.rename(prefix + theDecision)
_%>

# Decision: <% theDecision %>

## Context

%% Explain the context, environment, project, team, feature, etc %%<% tp.file.cursor(1) %>

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
