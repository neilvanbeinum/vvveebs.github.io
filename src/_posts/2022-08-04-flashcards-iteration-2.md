---
layout: post
title: "Flashcards App - Iteration 2"
date: 2022-08-04 13:03:57 +0300
header_image: /images/flashcards-2-banner.jpg
---
### What

This post outlines the second "iteration" of a Flashcards app.

This iteration actually works compared to the [previous toy version](/2022/08/04/flashcards/index.html). You can create a deck of flashcards, and then test yourself on each card, flipping it between front and back.

The state of your card deck is saved for your next visit.

### Implementation

I wanted to stick to a minimal, vanilla Javascript implementation.

I chose to use the [Shoelace](https://shoelace.style/) web components library. Web components allow developers to create custom tags, for example a `<my-button>` element, with associated CSS and JS, scoped to that component. No framework is required.

The following additional tools were used:
- [Local Storage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
- [ParcelJS](https://parceljs.org/) JS build tool
- [Cypress](https://www.cypress.io/) end-to-end testing
- [Jest](https://jestjs.io) unit testing
- [dompurify](https://github.com/cure53/DOMPurify) to sanitize user input

### Result

<div class="gallery">
  <img src="/images/flashcard-edit-front.jpg" alt="" />
  <img src="/images/flashcard-edit-back.jpg" alt="" />
  <img src="/images/flashcards-test.jpg" alt="" />
</div>

- [Flashcards app](https://vvveebs.github.io/flashcards/)
- [Code repo](https://github.com/vvveebs/flashcards)
