---
layout: post
title: "Flashcards App - Iteration 1"
date: 2022-08-04 13:03:57 +0300
header_image: /images/flashcards-banner.jpg
---
### What

This post outlines a simple app which lets you test your recall with flashcards - index cards with a test phrase written on one side with an answer on the reverse.

In this first iteration, I totally ignored implementation of a set of cards and instead focused on trying to make the card look "realistic".

The result is totally useless for revision because there's no ability to save your card - you can make one card on each visit only.

!["Flashcards front"](/images/flashcard-css-front.jpg)
### Why

Just [For fun](https://syntax.fm/show/491/how-to-spark-your-imagination-and-get-excited-about-coding).
### Implementation

#### Images and Fonts

I found a [free stock image of wood](https://www.pexels.com/photo/brown-wooden-surface-139306/) to use as the background.

I used [Inkscape](https://inkscape.org/) to create an [SVG image of an index card](https://github.com/vvveebs/flashcards_css/blob/master/flashcard.svg) to use as a background to the card `<div>`.

I found a handwriting-y font I didn't recognise called [‘Patrick Hand’](https://fonts.google.com/specimen/Patrick+Hand) to use for the card "writing".

#### 3D Transformation

I wanted to give the impression of the card being flipped by using a 3D CSS transform along the Y (up-down) axis.

Users with vestibular motion disorders can be affected by apps making use of transformations like these. The [`prefers-reduced-motion`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion) media feature should be used to reduce or remove motion for browsers with this setting applied. Here's an example:

```
@media (prefers-reduced-motion) {
  .card {
    transition: none;
  }
}
```

The "flipping" implementation has a few steps and uses some unusual CSS declarations. Important parts of the implementation are below:

- Using a `<div>` to represent the card with two `<input>` child elements to represent the writing.
- Applying absolute positioning and centering of the `<input>` elements, each with a rotation applied set so they "stick" to the front or back of the card and occupy the same central position on their face.
- Styling both `<input`> elements so they do not show when facing away from the viewer, using `backface-visibility: hidden`
- Toggling a class on the card, which has a transformation rule applied to it, when a button is clicked
- Setting `transform-style` on a containing `<div`> to `preserve-3d` so that child elements respect 3D space
- Setting a suitable `perspective` value on the container give a sense of depth as the card goes through the transition. (Low values give strange distorted effects.)

### Result

- [Flashcards app](https://vvveebs.github.io/flashcards_css/)
- [Code repo](https://github.com/vvveebs/flashcards_css)
