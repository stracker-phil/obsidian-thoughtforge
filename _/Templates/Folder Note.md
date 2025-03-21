<%*
/*
This template is used for folder notes, i.e "README.md" files.

Usage:
Right-click a folder, open "Folder note commands" and select "Create markdown folder note"
*/

const fullPath = tp.file.path(true);
const folderPath = fullPath.substring(0, fullPath.lastIndexOf('/'));
const folderName = folderPath.split('/').pop();
_%>

<%*
// Front-matter properties.
tR += "---\n"
tR += `aliases: "${ folderName }"\n`
tR += "---\n\n"

// Note contents start here.
_%>

# <% folderName %>

%% Describe the purpose of this folder, document specific conventions, how you intend to use it, and so on. This ensures you remember why you created this folder %%

This folder contains {{brief_description}}.

## Key Content

- [[link to important note 1]]
- [[link to important note 2]]
- [[link to important note 3]]

## How I Use This Section

I use this area for {{specific_purpose}}.