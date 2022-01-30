# Frontend Mentor - NFT preview card component solution

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

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
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](images/Screenshot 2022-01-30 at 12-06-45 Frontend Mentor NFT preview card component.png)

### Links

- Solution URL: [Add solution URL here](https://github.com/owi92/nft-preview-card-component-main)
- Live Site URL: [Add live site URL here](https://owi92.github.io/nft-preview-card-component-main/)

## My process

### Built with

- Basic CSS and HTML
- Mobile-first workflow

### What I learned

I tried different methods to center elements other than flexbox or grid (tho i am not proficient in using those either yet).

# first approach:

```css
parent {
  position: relative;
}
elementToCenter {
  position: absolute;
  top: 50%;
  left: 50%;
  transition: transform(-50%, -50%);
}
```

which works fine.

# Instead you can also do:

```css
parent {
  position: relative;
}
elementToCenter {
  position: absolute;
  inset: 0;
  margin: auto;
}
```

which seems a little cleaner.

Otherwise I "figured out" (through googling of course) a way to declare responsive font-sizes and widths without using media queries.

# Example:

```css
.main {
  background-color: hsl(216, 50%, 16%);
  border-radius: 15px;
  margin: auto;

  max-width: min(100%, 25ch);
  padding: min(4.6vw, 1.2rem);
}
```

Note the use of the min()-function for max-width and padding.
In using a variable size (like % or view-width) and a "static" one (i.e. ch, rem, px, etc), the function is responsive to screen size.

Futhermore I found that you need to declare the transition properties of class in the class itself and not its hover state for the "ease-out" part to work.

```css
.bottom-container__author {
  color: hsl(0, 0%, 100%);
  transition: color 0.3s ease-in-out; //do it here instead
}

.bottom-container__author:hover {
  color: hsl(178, 100%, 50%);
  cursor: pointer;
  /* transition: color 0.3s ease-in-out; */ //dont do it here
}
```

Through a comment on my first solution to this challenge I read about BEM-notation ("block element modifier) for html classes and decided to try it for the fist time. I am unsure whether I got it right, but I definitely like using a somewhat clear naming-convention.

In the process of debugging I found that I first need to check if the bug or error is caused by global styles which I forgot to overwrite. Also need to check if all "global" styles are necessary.

Lastly I decided to restructure and party rewrite my css-file. My first approach was quite messy and had a lot of unnecessary lines. For the redo I decided to structure the file to mirror the flow of the HTML-file with the exception of an additional section for Hover-states.

### Continued development

I plan to continually use BEM-notation and structuring of the css-file to mirror the html document flow.
For that I also want to look in some collections of "best practices" or likewise rescources for writing html and css.

In future projects I also want to use some frameworks and functionality through javascript.

### Useful resources

Unfortunately I did not save the google search results and stack-overflow pages I visited to build this project.

I did watch some css-specific videos from Kevin Powell on youtube, which are really awesome.

I also do like to listen to quiet background music while coding/researching.

- [Example resource 1](https://www.youtube.com/kepowob) - I find this to be a great rescource to learn new and old CSS-tricks and practices.
- [Example resource 2](https://www.youtube.com/watch?v=otJM19ChEYs&t=1s) - <3

## Author

- Website - [Ole](https://github.com/owi92)
- Frontend Mentor - [@owi92](https://www.frontendmentor.io/profile/owi92)

## Acknowledgments

Many thanks to @tymren608 on frontend mentor for commenting on my first solution. I was not aware of the problems in my design and their suggestions were quite helpful and helped me in my decision to redo the css-file (also because I did not expect anyone to look at my code beforehand).

There was a tiny overhang in one of my containers and I just could not figure out why it was there. After hours of bruteforcing I decided to have a look at @tymren608's solution. Even though their CSS-file is a little different to mine, I tried out some lines and it finally solved my issue (I had to include "font-size:0" in the troublesome div which did the job - still not entirely sure why tho)
