---
layout: default
title: Add a note
description: How to add a tutorial, a video, or your name.
samwiki: true
permalink: /contributing/
---

The 2019 GLM-to-Excel note stays as it is. New work is added beside it. The home page reads three lists, so a new tutorial, video, or name shows up without editing the layout.

The header and footer stay on the shared SamWiki links: Home, Running, About, Code, Hire, GitHub, and Linktree. Leave `_includes/samwiki-nav.html` on that set. Linktree stays `https://linktr.ee/samuel.castillo`.

## Add a tutorial

1. Branch from `master`.
2. Put the rendered page, source, and any workbook or figure in the repository. Keep a filename once it is linked.
3. Append an entry to `_data/tutorials.yml`.
4. Open a pull request. GitHub Pages publishes `master` from the repository root.

Each tutorial entry needs:

- `title`
- `description`
- `lang`, a short label such as HTML, R, or Excel
- `href`, a site path that starts with `/`
- `action`, the button label, such as Open, Source, or Download
- `style`, either `live` for the filled button or `source` for the outline button
- `badge`, optional

## Add a video

Append `_data/videos.yml` with `title`, `url`, and `host`. Set `embed` to a player URL when the home page should show it. The YouTube GLM link and the Rumble data-manipulation link already live in that file.

## Add your name

Append `_data/people.yml` with `name` and `role`. `url` and `url_label` are optional.

## Leave the existing math alone

The prettydoc, the notebook, `Convert R GLM to Excel.Rmd`, `R GLM in Excel.xlsx`, and the Excel figures are the original tutorial. A correction to that note belongs in a pull request that shows the change. `debug.log` and the RStudio project file stay out of the published site.
