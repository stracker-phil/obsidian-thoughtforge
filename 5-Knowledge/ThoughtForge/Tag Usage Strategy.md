# Journal-First Tag Strategy

> [!info] Getting Started
> This approach focuses on using tags primarily in journal entries as markers for future organization. Review this note to understand the tag strategy in ThoughtForge, adjust naming conventions if you like.

## Core Principle

In my vault, tags serve a specific purpose: **marking content in journal entries for future refactoring into dedicated notes**. This aligns with my [[Core Principles of This Vault#Create First, Organize Later|Create First, Organize Later]] principle.

## How I Use Tags

I only use **inline tags** in my [[1-Journal/README|daily notes]], not in structured notes or other files. This approach:

1. Creates clear refactoring paths from daily notes to proper locations
2. Prevents redundant metadata: A note in the `5-Knowledge/AI` folder doesn't need an `#ai` tag!

## Tag Naming Convention

I use hierarchical namespaces that align with my folder structure:

| Tag Pattern     | Purpose                                                           | Example              |
| --------------- | ----------------------------------------------------------------- | -------------------- |
| `#topic`        | When the topic maps to a clear knowledge folder                   | `#ai` or `#obsidian` |
| `#project/name` | Work or quest-related items. Prefix is a customer or project name | `#acme/checkout`     |
| `#doc/type`     | Items that should become part of a [[Setup Guide]]                | `#doc/wp`            |
| `#decide`       | A decision that's been made, usually in [[Daily Meeting Notes]]   | `#decide`            |
| `#private`      | Content that should stay in journal                               | `#private`           |

These are examples rather than strict rules. Since tags are transient markers meant to be removed after refactoring, their exact structure is less critical than their usefulness to you.

## Tag Workflow

1. I add tags **inline** in journal entries (not at file level)
2. During weekly reviews, I search for these tags
3. I refactor relevant content into dedicated notes in appropriate folders
4. Once content is moved, I remove the tag and add a link to the new note

## When Not To Use Tags

Outside the daily notes, tags prove to be less valuable and can create unnecessary maintenance overhead.

The [[0-Inbox/README|Inbox]] could be an exception, but these notes are typically easy to scan and organize directly. Journal entries, however, capture a variety of topics in a single note, making tags valuable for identifying content for refactoring.

In Obsidian, **links** provide more lasting value than tags. While tags offer temporary context for refactoring, links create permanent relationships between notes.

> [!summary] Conclusion
> Tags add short-term context and should be refactored. Links are long-term relations.
