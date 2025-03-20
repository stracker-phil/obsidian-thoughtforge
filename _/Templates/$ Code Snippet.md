<%*
const theName = tp.file.title.replace(/^\$/, '')
const prefix = "$"
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
