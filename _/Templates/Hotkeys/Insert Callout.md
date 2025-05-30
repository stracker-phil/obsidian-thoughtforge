<%*
/*
This hotkey template is used by the Templater plugin to provide an UI for generating callouts. Adjust the configuration flags, and extend the list of callouts below to change callout-types to choose from.

Default hotkey: ⌘ ⇧ J
Reference: https://github.com/SilentVoid13/Templater/discussions/922

How to add new Callouts:
1. Open the "Settings > Callout Manager" page
2. Create a new callout on that page
3. Update the "callouts" configuration below, by adding the name and a label for the callout
*/

// Set to true to sort the list by callout name.
// Set to false to display callouts in the same order as defined below.
const sortAlphabetically = false;

// Set to true to add a "1. " number prefix to each item (keyboard control).
const addNumberPrefix = true;

// True will convert the callout type to uppercase.
// Sample for uppercase vs default: [!NOTE] or [!note]
const uppercaseType = true;

const callouts = {
    //  Callout name  |  Prompt Label    |  Personal Description

    // Red - Critical/Error group
    "bug":            "🟥 🪳 Bug",        // Bug icon
    "danger":         "🟥 ⚡️ Danger",      // Lightning Bolt icon
    "error":          "🟥 ⚡️ Error",       // Lightning Bolt icon
    "fail":           "🟥 ❌ Fail",       // 'X' mark icon
    "failure":        "🟥 ❌ Failure",    // 'X' mark icon
    "missing":        "🟥 ❌ Missing",    // 'X' mark icon
    
    // Orange - Warning group
    "attention":      "🟧 ⚠️ Attention",  // Exclamation Sign icon
    "caution":        "🟧 ⚠️ Caution",    // Exclamation Sign icon
    "warning":        "🟧 ⚠️ Warning",    // Exclamation Sign icon
    "help":           "🟧 ❓ Help",       // Question Mark in Circle icon
    "faq":            "🟧 ❓ FAQ",        // Question Mark in Circle icon
    "question":       "🟧 ❓ Question",   // Question Mark in Circle icon
    
    // Green - Success group
    "done":           "🟩 ✅ Done",       // Green Checkmark icon
    "check":          "🟩 ✅ Check",      // Green Checkmark icon
    "success":        "🟩 ✅ Success",    // Green Checkmark icon
    
    // Blue - Information group
    "info":           "🟦 ⓘ Info",       // 'i' in Circle icon
    "note":           "🟦 ✏️ Note",        // Pencil icon
    "abstract":       "🟦 📋 Abstract",   // Clipboard icon 
    "summary":        "🟦 📋 Summary",    // Clipboard icon  
    "tldr":           "🟦 📋 TL;DR;",     // Clipboard icon  
    "example":        "🟦 📑 Example",    // Outline icon (ish so a folder?)
    "hint":           "🟦 🔥 Hint",       // Flame icon
    "important":      "🟦 🔥 Important",  // Flame icon
    "tip":            "🟦 🔥 Tip",        // Flame icon
    "todo":           "🟦 ✅ Todo",       // Checkmark in Circle icon
    
    // White - Quotes
    "cite":           "⬜️ ⍘ Cite",        // Quotation Mark icon
    "quote":          "⬜️ ⍘ Quote",       // Quotation Mark icon
};

// ----- end of configuration, stop editing -----

const typeNames = [];
const typeLabels = [];
let orderedKeys = Object.keys(callouts)

if (sortAlphabetically) {
    orderedKeys = orderedKeys.sort()
}

orderedKeys.forEach((key, index) => {
    const prefix = addNumberPrefix ? `${index+1}. ` : '';
        
    typeNames.push(key);
    typeLabels.push(`${prefix}${callouts[key]}`);
});

let calloutType = await tp.system.suggester(
    typeLabels,
    typeNames,
    false,
    "Select callout type (use numbers 1-" + typeLabels.length + " to select)"
);

// Stop here when the prompt was cancelled (ESC).
if (!calloutType) {
    return;
}

// Extract the main name from the label to pre-fill the header.
const defaultTitle = callouts[calloutType].split(' ').pop();

const title = await tp.system.prompt("Callout Header:", defaultTitle);

const foldState = await tp.system.suggester(
    ["1. Static", "2. Expanded", "3. Collapsed"],
    ["", "+", "-"],
    false,
    "Select callout folding option (use numbers 1-3 to select)"
);

let formattedContent = '';
const content = await tp.file.selection();

if (content) {
    // Format each line of content to be part of the callout
    formattedContent = `\n` + content
        .trim()
        .split('\n')
        .map(line => `> ${line}`)
        .join('\n');
}

if (uppercaseType) {
    calloutType = calloutType.toUpperCase();
}
_%>

> [!<% calloutType %>]<% foldState %> <% title %><% formattedContent %> <%* tp.file.cursor() %>