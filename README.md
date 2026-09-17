# Frontend Mentor - Fylo data storage component solution

This is a solution to the [Fylo data storage component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/fylo-data-storage-component-1dZPRbV5n). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
  - [AI Collaboration](#ai-collaboration)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot

[Screenshot](./images/screenshot.jpg)

### Links

- Solution URL: [Frontend Mentor Solution](https://www.frontendmentor.io/solutions)
- Live Site URL: [Fylo Data Storage Component](https://github.com/OMS-Create/flyo-data-storage-component)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- Google Fonts (Raleway)

### What I learned

Working through this challenge helped reinforce mobile-first layout design, custom progress bar styling, and absolute positioning techniques for speech bubble badges.

#### Progress Bar & Knob Indicator
Using Flexbox on the filled track made it seamless to dock the circular white indicator dot at the end of the bar regardless of percentage completion:

```html
<div class="progress-bar" role="progressbar" aria-valuenow="700" aria-valuemin="0" aria-valuemax="1000" aria-label="Storage space used">
  <div class="progress-fill" style="width: 70%;">
    <span class="progress-indicator"></span>
  </div>
</div>
CSS
.progress-fill {
  background: linear-gradient(to right, var(--clr-gradient-start), var(--clr-gradient-end));
  height: 100%;
  border-radius: 0.5rem;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding-inline-end: 0.125rem;
}
Speech Bubble Tail (::after Pseudo-element)
For the desktop layout, the floating remaining storage badge transforms into a speech bubble using a CSS border triangle trick:

CSS
.remaining-badge::after {
  content: '';
  position: absolute;
  bottom: -1.375rem;
  right: 0;
  border-width: 1.375rem 1.375rem 0 0;
  border-style: solid;
  border-color: var(--clr-white) transparent transparent transparent;
}
Continued development
In future iterations, I plan to:

Add a smooth CSS width transition or keyframe animation to animate the progress fill on initial page load.

Connect the component to a lightweight JavaScript state to dynamically update used storage values based on user input.

Useful resources
MDN Web Docs: ARIA progressbar role - Guided the accessible markup implementation for screen readers.

A Complete Guide to Flexbox (CSS-Tricks) - Useful reference for aligning the progress indicator dot.

AI Collaboration
Tool Used: Gemini AI

Usage: Collaborated on refining HTML semantic markup, implementing proper ARIA roles for accessibility, fine-tuning the CSS progress indicator alignment, and structuring the design for mobile responsiveness.

Author
Frontend Mentor - [@OMichaels](https://www.frontendmentor.io/OMS-Create)
