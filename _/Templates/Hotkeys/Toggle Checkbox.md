<%*
/*
This hotkey template is used by the Templater plugin to provide an UI to toggle/change a checkbox: After selecting the appropriate state, the script will update the current line or list item to display the chosen checkbox.

Default hotkey: ⌘ ⇧ L
*/

// List of all defined checkbox states. Adjust to match your setup.
const states = {
    ' ': 'Unchecked | Pending',
    'x': 'Checked | Done',
    '>': 'Rescheduled',
    '<': 'Scheduled',
    '!': 'Important',
    '-': 'Cancelled',
    '/': 'In Progress',
    '?': 'Question | Unclear',
    '*': 'Star',
    'n': 'Note',
    'l': 'Location',
    'i': 'Information',
    'I': 'Idea',
    'S': 'Amount | Price | Money',
    'p': 'Pro | Good',
    'c': 'Con | Bad',
    'b': 'Bookmark',
    '"': 'Quote',
    'u': 'Up | Like',
    'd': 'Down | Dislike',
    'w': 'Win',
    'k': 'Key',
    'f': 'Fire | Hot',
    '': 'Clear Checkbox | Reset'
}

// Whether to show the new-state input dialog.
// When set to false, the checkbox loops though all defined states.
const promptUser = true

// This state is used, if the current line is no checkbox yet, or if
// it's current state is unknown.
// Default: Undone checkbox (Space).
const defaultState = ' '

// ----- end of configuration, stop editing -----

// Helper functions.
const getLabel = key => (key ? `[${key}] ` : '') + `${states[key]}`
const stateByListType = (listNumber, key) => key
    ? (listNumber ? `${listNumber} [${key}] ` : `- [${key}] `)
    : ''
const setState = (key, line) => line.replace(
    /^(\s*)(-|\*|(\d\.))?(\s+\[.\])?\s*/,
    (...match) => match[1] + stateByListType(match[3], key)
)

// Prepare vars, inspect current editor line.
const stateKeys = Object.keys(states)
const editor = app.workspace.activeEditor.editor
const cursor = editor.getCursor('from')
const currentLine = editor.getLine(cursor.line)
const stateMatch = currentLine.match(/^[\s-\*]+\s\[(.)\]\s/)
const currentState = stateMatch?.[1] || ''
let newState = defaultState

// We found a valid checkbox state. Let's find the next state in the queue.
if (currentState) {
    let nextIndex = stateKeys.indexOf(currentState) + 1
    if (nextIndex >= stateKeys.length) {
        nextIndex = 0
    }
    newState = stateKeys[nextIndex]
}

// Optional branch: Let the user choose the new state.
if (promptUser) {
    // Display the "next state" as first option, so it's auto-selected.
    const suggestLabels = [getLabel(newState)]
    const suggestKeys = [newState]

    stateKeys.map(key => {
        if (key === newState) {
            return;
        }
        suggestLabels.push(getLabel(key))
        suggestKeys.push(key)
    })

    newState = await tp.system.suggester(
        suggestLabels,
        suggestKeys,
        false,
        "Select new checkbox state"
    )
}

if ('string' !== typeof newState) {
    return
}

editor.setLine(cursor.line, setState(newState, currentLine))
editor.setCursor(cursor)
%>