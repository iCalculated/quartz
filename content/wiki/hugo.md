---
title: "Hugo"
---

# [Hugo](https://gohugo.io)

## [Frontmatter](https://gohugo.io/content-management/front-matter/)

Title is required.

## Hugo Obsidian 

Used to generate graph and interactive links:

```shell
hugo-obsidian -input=content -output=data
```

## Run

Can server locally with

```shell
hugo server
```

## [Templates](https://gohugo.io/templates/introduction/)

Based on Go, templates are HTML files with references to [variables](https://gohugo.io/variables/) and [functions](https://gohugo.io/functions/) indicated via `{{ }}`. 

## Markdown

Can add custom attributes by including the following after a title or block:

```
#Title
{.className}
 ```