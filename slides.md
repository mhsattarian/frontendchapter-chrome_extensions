---
theme: bricks
# background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-right 
highlighter: shikiji
lineNumbers: false
download: false
exportFilename: 'frontendchapter-chrome_extensions'
favicon: https://www.frontchapter.ir/favicon.ico
author: Mohammad Hassan Sattarian
keywords: tech talk,extensions,chrome,add-on,plugin,frontend
info: |
  ## Chrome Extensions
  an Introduction!

  from the series of tech talks by Frontend Chapter 🥕
drawings:
  persist: false
transition: fade
title: Frontend Chapter - Chrome extensions
mdc: true
css: windicss
layout: center
---

<div class="flex justify-center items-center">
<img class="h-400px" src="/assets/20201028_104813.jpg" />
</div>


---
layout: cover
class: text-right 
---

# Chrome Extensions

A short introduction!

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: intro
transition: fade-out
---

<div class="flex flex-col items-center" >
<img src="https://avatars.githubusercontent.com/u/29674767?v=4" width="200" height="200" class="rounded-1/2" />

## Mohammad Hassan Sattarian
Frontend Developer


<div class="flex">
<a href="https://github.com/mhsattarian" target="_blank" alt="GitHub" title="profile in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>
</div>

---
layout: default
---

# Table of contents

<Toc maxDepth="1"></Toc>

---
layout: fact
---

## What are Extensions?

Extensions are small software programs that customize the browsing experience. They enable users to tailor browser functionality and behavior to individual needs or preferences. They are built on web technologies such as HTML, JavaScript, and CSS.

AKA: Plugins, Add-ons

---
layout: fact
---
<div class="flex justify-center items-center">
<img class="h-400px" src="/assets/what.webp" />
</div>


---
layout: quote
---

# How does an Extension Work?

---
layout: section
---

# Architecture

::right::

## Manifest

Specifys metadata about extension and it's functionalities

## Scripts

Content Script, Background Script, Page action, Browser Action

## UI Elements

Popup UI and Extension's icon

## Options Page

Extension's preferences and Options


---
layout: section
---

# User Interface

::right::

## Action

Control the display of an extension's icon in the toolbar.

## Menus

Add items to Google Chrome's context menu.

## Side panel

Use the `chrome.sidePanel` API to host content in the browser's side panel alongside the main content of a web page.


<!-- There is also omnibox extensions to control keywords and such! -->


---
layout: items
---

# Extension Action APIs

<br />

## Content Script

Files that run in the context of web pages

## Browser Action

Icons in the main toolbar + Badges + Popup

## Page Action

Toolbar Icons + Only for certain sites

---
layout: fact
---

# Browser Action

#### Add Icon in the main toolbar with badges and  popups

On browser tool bar

A browser action can have an icon, a tooltip, a badge, and a popup.

---
layout: fact
---

**Raindrop** bookmark manager

<div class="flex justify-center items-center">
<img class="h-400px" src="/assets/ex-browser-actions.png" />
</div>

---
layout: fact
---

# Page Action

#### Represent actions that can be taken on the <ins>current</ins> page

On address bar <sup>(not any more)</sup>

Can have popups

---
layout: fact
---

<div class="flex flex-col justify-center items-center gap-2">
<img class="" src="/assets/ex-page-action.jpeg" />
<img class="" src="/assets/ex-page-action2.jpeg" />
</div>

---
layout: fact
---

# Content Script

#### Inject CSS and JS

Limited access to some Chrome APIs

---
layout: items
transition: fade-out
---

<div class="flex justify-center items-center">
<img class="h-400px" src="/assets/ex-content-script.png" />
</div>

---
layout: blank
---

# Manifest
####
Use code snippets and get the highlighting directly, and even types hover![^1]

```json {all|2|7-9|10-14|19}
{
  "manifest_version": 3,
  "name": "My acme extension",
  "description" : "",
  "version": "0.1",
  "icons": { "64": "icon-1.png" },
  "background": {
    "service_worker": "background.js"
  },
  "content_scripts": [{
    "matches": ["https://500px.com/photo/*"],
     "js": ["content.js"],
     "run_at" : "document_end"
  }],
    "action": {
      "default_icon": "icon.png",
      "default_title": "Bring me the picture"
    },
  "permissions": ["scripting", "activeTab"]
}
```

[^1]: [Learn More](https://sli.dev/guide/syntax.html#line-highlighting)

<style>
.footnotes-sep {
  @apply mt-20 opacity-10;
}
.footnotes {
  @apply text-sm opacity-75;
}
.footnote-backref {
  display: none;
}
</style>



---
layout: quote
---

# Lets write one!
####

Add a download button to **Archillect** images!

---
layout: items
cols: 4
---

# But before that...

<!-- ::items:: -->


#### Make sure you turned on the Developer Mode

<div class="flex justify-center items-center mt-20">
<img class="h-400px" src="/assets/developer-mode.png" />
</div>



---
layout: quote
---

# Learn More

[Documentations](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/showcases.html)

---
layout: end
font: serif
---

## The creative adult is the child that has survived.

\- Ursula K. Le Guin


