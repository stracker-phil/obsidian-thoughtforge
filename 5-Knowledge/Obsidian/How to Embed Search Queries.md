# How to Embed Search Queries

This feature is built into Obsidian's core and works when the **core plugin "Search"** is active.

## Embed Search Results

I like this solution, because it's plain-text representation is clean and concise:

````md
```query
Search term
```
````

The content of the code block is a single line that uses the same syntax as the search field in Obsidian.

## Link Search Results

It's also possible to create a link that opens the search results in the sidebar, instead of embedding the results by using the URL `obsidian://search?query=`

> [!note] Sample:
> Search for ["The query"](obsidian://search?query="Getting%20Started")

**Notes**
- The query must be URL-encoded
- Use `%20` for space, not `+`!

## Search Queries

### Simple Search

Search globally by keywords:

````
```query
Search Term
```
````

Use quotes to search for exact terms:

````
```query
"Search Term"
```
````

Search for keywords that appear _on the same line_ or _in the same section_.

- `line`: Find lines that contain all terms
- `section`: Find sections that contain all terms; sections are separated by headers

````
```query
line:(Started Getting)
```

```query
section:(Started Getting)
```
````

Live test for [line search](obsidian://search?query=line:(search%20word)) and for [section search](obsidian://search?query=section:(search%20word)).

### Filter by Path or Filename

- `file:"name.md` .. Only search files with that name
- `-file:"name.md"` .. Exclude all files with that name
- `path:"/0-Inbox"` .. Only search the path
- `-path:"/1-Journal"` .. Do not search the provided path

````
```query
"Search Term" -file:"README.md"
```
````

### Conditions

- `AND` or `OR` cam combine filters
- Use `()` to group conditions

This sample excludes all README.md files, except for the root folder README.md:

````
```query
Started (-file:"README.md" OR path:"/README.md")
```
````

## Test the Query

Just open the search sidebar and enter the query. If it works in the sidebar, it also works in the embedded search results and link.
