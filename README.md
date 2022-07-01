# Frontend Mentor - Interactive rating component solution

This is a solution to the [Interactive rating component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/interactive-rating-component-koxpeBUmI). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the app depending on their device's screen size
- See hover states for all interactive elements on the page
- Select and submit a number rating
- See the "Thank you" card state after submitting a rating

### Screenshot

[Screenshot](./images/screenshot.png)

### Links

- This solution on Frontend Mentor: [Add solution URL here](https://your-live-site-url.com)
- Live site: [Interactive rating component](https://mightycoyote.github.io/interactive-rating-component-main/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Both inline and referenced SVGs

### What I learned

Selecting a single option between 1 and 5 is functionally a set of radio buttons, even though this design doesn't use the default dot-and-circle button. The radio button label already works as part of the button by default, so I suspected it would be possible to hide the &#9737; and style the labels. I did some research to see if this was a good solution and the best way to go about it if so.

Styling the labels based on _pseudo-classes_ of the buttons requires some somewhat fancy selectors:

```
.radios input[type="radio"]:checked + label {
    color: white;
    background-color: var(--medium-grey);
}

.radios input[type="radio"]:hover + label, .radios input[type="radio"]:focus + label {
    color: white;
    background-color: var(--orange);
}
```

...so I'm glad I looked this up instead of trying to reinvent the wheel.

Otherwise I feel this was a good solution since I did not have to write Javascript to make numbered circles behave like radio buttons. The DOM knows where the radio button group is _and_ which one has been selected.

```
const radioGroup = document.forms[0].elements['rating'];
```

```
`<span>You selected ${radioGroup.value} out of 5</span>`
```

### Useful resources

- [Customize Radio Button Appearance with CSS](https://markheath.net/post/customize-radio-button-css)
- [RadioNodeList.value on MDN](https://developer.mozilla.org/en-US/docs/Web/API/RadioNodeList/value)

## Author

- Website - [Sarah Wilkes](https://mightycoyote.github.io/)
- Frontend Mentor - [@mightycoyote](https://www.frontendmentor.io/profile/mightycoyote)

