<%*
/*
I use this template to document interesting or noteworthy code snippets that I want to remember. The main goal is to build a collection of "well written code" in my vault.

Usage:
- Create a new file with the topic name (like "Card payment issues.md")
- Hit `⌘ ⇧ N` to select this template

Note: This template renames the note, and adds the prefix "$ "
*/
*/

const theName = tp.file.title.replace(/^\$/, '')
const prefix = "$ "
await tp.file.rename(prefix + theName)
_%>

<%*
// Front-matter properties.
tR += "---\n"
tR += "purpose: \n"
tR += "language: \n"
tR += "---\n\n"

// Note contents start here.
_%>

# <% theName %>

```
{{code}}
```

## Notes

%% Usage notes, links to documentation, PRs with usage samples, ... %%
