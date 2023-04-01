<div align="center">
  <img 
    src="./sass techdoc bg.png"
    alt="Technical documentation page with guidance for how to add images and visual elements when writing in GitHub"
    height="350px">
</div>

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

I wanted to experiment with creating a responsive page using different types of positioned elements. I also wanted to figure out how to build a CSS-only mobile navigation menu. In my desktop design, the vertical navigation menu is fixed on the left side of the page. For the mobile design, I wanted the identical menu to slide in from the right side of the page. I hypothesized I could create a CSS-only sliding mobile menu using a checkbox input and this project was a good exercise to test my idea.

I also used this project to dig a little deeper into the capabilities of SASS, focusing on nesting rules and mixins.

<div align="center">
  <img
    src="./techdoc mobile-closed bg.png"
    alt="Mobile version of technical documentation page showing hamburger menu in upper right corner"
    height="350px">
  <img 
    src="./techdoc mobile-open bg.png"
    alt="Mobile version of technical documentation page showing visible navigation menu after clicking hamburger menu"
    height="350px">
  <p><em>Mobile design with menu closed (left) and open (right)<em></p>
</div>

### Links

- See it in the browser: [SASS Tech doc with mobile menu]()

## My process

### Built with

- Semantic HTML5 markup
- SASS
- CSS-only mobile hamburger menu
- Flexbox
- Responsive design


### What I learned

I explored a variety of positioning options to find the best fit for the design idea I had in my head and then experimented to find the best way to also keep the page responsive. My final build uses fixed positioning for the desktop design and absolute positioning for the mobile slide-in menu.

I created a CSS-only mobile hamburger menu using a checkbox input that updates the color of the hamburger icon, slides in the mobile navigation menu from right, and provides a darkened background overlay on click.

```scss
input {
  display: none;
  &:checked {
    + label {
      rect {
        fill: $neutral-white;
      }
    }
    ~ .mobile-menu {
      transform: translate(calc($space-base * -35.625), 0);
    }
    ~ .overlay {
      visibility: visible;
    }
  }
}
```

I focused on improving my SASS skills with mixins and nesting rules, along with variables and CSS functions to make my build responsive.

```scss
.mobile-menu {
  width: 85vw;
  max-width: calc($space-base * 17.8125);
  height: 100%;
  background-color: $neutral-white;
  @include box-shadow();
  @include position(absolute, 0, calc(100% + calc($space-base * 17.8125)));
  z-index: 10;
  @include transition(transform, 0.25s, ease);
}
```

### Continued development

I'm quite comfortable with the SASS syntax, and my goal now is to improve my skills and write more efficiently. 

### Useful resources

- [Alvaro Trigo responsive CSS hamburger menu](https://alvarotrigo.com/blog/hamburger-menu-css-responsive/) - On completing my initial build of the mobile menu, I realized something was missing. This tutorial included an overlay that displays a dark background when the mobile menu slides into view, which provided a better visual than the white menu on white background. 

## Author

- Frontend Mentor - [@rileydevdzn](https://www.frontendmentor.io/profile/rileydevdzn)
