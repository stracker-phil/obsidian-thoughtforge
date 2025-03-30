# Which Plugins I Use and Why

A short documentation and reasoning for the plugins I use in this vault. I need to review this list before adding new plugins, and consider if those new plugins are a good fit. This vault should _change slowly_.

## Core Functionality

> The following plugins are required to run this vault and should not be disabled.

### Templater

Used to parse the template notes, allowing me to use JS logic to render the initial note content. Also provides some functions like prompting for an input value.

I maintain a list of useful practices in the [[Templater Tricks]] note.

### Folder Notes

Makes the `README.md` files available as folder-notes, which is [[Folder Notes|a core principle]] of this vault.

### Linter

This plugin enforces a consistent markdown format in my files. This ensures the notes are also looking well in other markdown editors and follow my personal formatting rules.

### Calendar

[[1-Journal/README|Daily Notes]] are the backbone of my vault, and the Calendar sidebar is a vital addition to navigate those notes.

### QuickSwitcher++

Drop-in enhancement for the default "Quick Switcher" (which just opens files). I heavily use the Symbol Search, which is mapped to `⌘ R` to navigate inside a note.

## Core Appearance

> Plugins that will impact the visual appearance of the vault or notes when they are deactivated. However, they are not required to use the ThoughtForge system.

### Callout Manager

I use this plugin to style and create Callout boxes to improve the visual appearance of rendered notes inside Obsidian.

### List Callouts

A nice addition to replace a list-item prefix with an icon. I pay attention to use meaningful prefixes: Rather than random characters like `§`, I prefer a short word like `url:` which ensures the list item also makes sense when reading it in a different editor.

### Supercharged Links

Helpful to customize note links application wide. This allows me to quickly recognize the type of a certain link. This plugin only adds HTML attributes to links, depending on some rules. The actual styling is done by the **Style Settings** plugin.

### Style Settings

Helps me to maintain a clean, minimalistic Obsidian UI. This plugin allows me to customize the following items:

- **Minimal**-theme
- **Supercharged Links**: Style the links with custom icons or colors.
- **List Callouts**: Customize global list-item appearance

## Convenience

> Plugins that are fully optional, yet helpful for my workflow.

### Mention Things

A quicker way to insert cross-links between certain note types. I extensively use the `@`-notation to mention people in all kind of notes.

### Paste Image Rename

Opens a modal whenever I copy-paste an image to the vault, allowing me to rename that image. I've configured to use a date-prefix as default name, to follow my [[File Types and Media|media-naming conventions]].

### Image Toolkit

In many cases I want to open a screenshot in a lightbox without distractions, or zoom-in to see more details. This plugin adds those basic features that are lacking in Obsidian.

### Virtual Linker

Links terms in my notes that match the title or alias of an existing note. These links are virtual, and do not appear in the note's Markdown source or in Obsidian's graph view; I use those virtual links (a) as a glossary, and (b) help me identify potential cross-links that I could add to the note.

### Rainbow-Colored Sidebar

The plugin gives each top-level folder in the sidebar a distinct color. This adds an additional visual cue helping me to quickly see which notes I'm seeing in the sidebar.

### Ninja Cursor

Animates the cursor movement, which makes it easier for me to follow the cursor movement. This is clearly a very personal and optional plugin.

---

## Considered

This section describes tools I used in the past and why I have removed them.

### Colored Tags

A simple plugin that gives each tag a different color. In case I would use tags more extensively, I would re-install this plugin, but my current [[Tag Usage Strategy]] does not justify this addition.

### Omnisearch and Text Extractor

The main selling point for this plugin-duo is the ability to search for text inside images and PDFs. After one year of usage, I noticed how I never needed to search for those details. The default search capacity of Obsidian is sufficient for my use case.

When I find the need to search PDF or image content, I'll likely re-install those two plugins.

### Dataview

Mainly used the JS API to create scripts. Since I've stopped using CustomJS, this plugin has no meaningful contribution at the moment.

I might use it in case I want to create more dynamic file lists inside my folder notes.

### CustomJS

Allowed me to write and execute JS code inside a code-block in my notes. This allowed me to add powerful features to Obsidian, but it polluted my notes with increasingly complex JS code, which turned out to be a bad practice.

Instead of using this plugin, I will write a custom Obsidian plugin when I need certain features. This plugin encourages mixing note-content with custom app-logic, which I want to avoid.
