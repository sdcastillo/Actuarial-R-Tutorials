---
layout: default
title: Add a note
description: How people working on Actuarial R Tutorials add a tutorial and their name.
samwiki: true
permalink: /contributing/
---

<p class="sw-intro">The 2019 GLM-to-Excel note stays as it is. New work is added beside it. The home page reads two lists, so a new tutorial or a new name shows up without editing the layout.</p>

<h2>Add a tutorial</h2>
<ol>
  <li>Branch from <code>master</code>.</li>
  <li>Put the rendered page, source, and any workbook or figure in the repository. Keep filenames stable once they are linked.</li>
  <li>Append an entry to <code>_data/tutorials.yml</code> with a title, a short description, a language label, and a site path that starts with <code>/</code>. Use <code>style: live</code> for the filled button and <code>style: source</code> for the outline button.</li>
  <li>Open a pull request. GitHub Pages publishes the default branch from the repository root.</li>
</ol>

<h2>Add your name</h2>
<p>Append an entry to <code>_data/people.yml</code> with your name and what you are working on. A link is optional. The home page lists everyone in that file.</p>

<h2>Leave the existing math alone</h2>
<p>The prettydoc, the notebook, <code>Convert R GLM to Excel.Rmd</code>, <code>R GLM in Excel.xlsx</code>, and the two Excel figures are the original tutorial. Corrections to that note belong in a pull request that shows the change. Session files (<code>debug.log</code>, the RStudio project file) stay out of the published site.</p>
