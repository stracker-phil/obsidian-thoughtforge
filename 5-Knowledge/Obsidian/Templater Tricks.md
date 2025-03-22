# Templater Tricks

## Cursor Usage

Insert the cursor (or multiple cursors) into a template after rendering it:

```md
<% tp.file.cursor(1) %> some content <% tp.file.cursor(1) %>
```

I can also define a series of cursors, that can be navigated by using `⌘ ⏎`:

```md
Topic: <% tp.file.cursor(1) %>
Location: <% tp.file.cursor(2) %>  %% Use CMD+Return to navigate here %%
```

To use `tp.file.cursor` I need to enable the plugin setting **Automatic jump to cursor**
