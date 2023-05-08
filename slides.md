---
# try also 'default' to start simple
theme: "@doba16/slidev-theme-htw"
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# page transition
transition: slide-left
# use UnoCSS
css: unocss
image: /dots.png
---

# NP-Vollständigkeit von Two Dots

---

# NP-Vollständige Probleme

<div class="grid grid-cols-2 grid-rows-[170px_170px] np-complete-examples">

<img src="/uno.svg" style="height: 100%" />

<img src="/Graph.svg" style="height: 100%" />

<img src="/Sudoku.svg" style="height: 100%" />

<img src="/Dots.svg" style="height: 100%" />

</div>

---

# Dots Game

<DotsGame />

---

# Reduktion von Clique

<DotsGameReduction />

---

<div class="text-4xl mx-auto text-center mt-25 eurodata-text">
  Vielen Dank für Ihre Aufmerksamkeit
</div>

<div class="mt-10 shadow shadow-gray-500 shadow-2xl p-6">
<span class="text-2xl">Dominik Bastian</span>
<div class="grid grid-cols-1 w-full gap-3">


<span class="text-gray-500 dark:text-gray-400">
  <GitHubIcon />
  <span class="text-lg ml-1">https://github.com/doba16/np-complete-dots-game-slides</span>
</span>

<span class="text-gray-500 dark:text-gray-400">
  <GitHubIcon />
  <span class="text-lg ml-1">https://github.com/doba16/predictable-dots-game</span>
</span>

</div>
</div>