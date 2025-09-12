# CSS Guide 🎨

Welcome to your complete guide to CSS (Cascading Style Sheets)! This guide will teach you everything you need to know to start styling beautiful web pages.

## Table of Contents
- [What is CSS?](#what-is-css)
- [How to Add CSS](#how-to-add-css)
- [CSS Syntax](#css-syntax)
- [Selectors](#selectors)
- [Colors and Backgrounds](#colors-and-backgrounds)
- [Typography](#typography)
- [Box Model](#box-model)
- [Layout and Positioning](#layout-and-positioning)
- [Flexbox](#flexbox)
- [Grid Layout](#grid-layout)
- [Responsive Design](#responsive-design)
- [Animations and Transitions](#animations-and-transitions)
- [Pseudo-classes and Pseudo-elements](#pseudo-classes-and-pseudo-elements)
- [CSS Variables](#css-variables)
- [Best Practices](#best-practices)
- [Practice Exercises](#practice-exercises)

---

## What is CSS?

CSS stands for **Cascading Style Sheets**. It's the language used to style and layout web pages. While HTML provides the structure and content, CSS makes your web pages look beautiful and responsive.

### Key Points:
- CSS controls the **appearance** of HTML elements
- It separates content (HTML) from presentation (CSS)
- CSS follows a **cascading** order of priority
- One CSS file can style multiple HTML pages

### What CSS Can Do:
- Change colors, fonts, and sizes
- Create layouts and positioning
- Add animations and effects
- Make websites responsive to different screen sizes
- Create beautiful user interfaces

---

## How to Add CSS

There are three ways to add CSS to your HTML:

### 1. Inline CSS (Not Recommended)
```html
<p style="color: red; font-size: 18px;">This text is red and 18px.</p>
```

### 2. Internal CSS
```html
<head>
    <style>
        p {
            color: blue;
            font-size: 16px;
        }
    </style>
</head>
```

### 3. External CSS (Best Practice)
```html
<!-- In your HTML file -->
<head>
    <link rel="stylesheet" href="styles.css">
</head>
```

```css
/* In your styles.css file */
p {
    color: green;
    font-size: 14px;
}
```

---

## CSS Syntax

CSS follows a simple pattern:

```css
selector {
    property: value;
    property: value;
}
```

### Example:
```css
h1 {
    color: blue;
    font-size: 24px;
    text-align: center;
}
```

### Breaking it down:
- `h1` - **Selector** (what element to style)
- `{}` - **Declaration block** (contains the styles)
- `color: blue;` - **Declaration** (property + value + semicolon)
- `color` - **Property** (what to change)
- `blue` - **Value** (how to change it)
- `;` - **Semicolon** (ends each declaration)

---

## Selectors

Selectors tell CSS which HTML elements to style:

### Element Selectors
```css
p { color: red; }           /* All paragraphs */
h1 { font-size: 32px; }     /* All h1 headings */
div { background: gray; }   /* All div elements */
```

### Class Selectors
```css
.highlight { background: yellow; }    /* Elements with class="highlight" */
.button { padding: 10px; }            /* Elements with class="button" */
```

```html
<p class="highlight">This paragraph is highlighted</p>
<button class="button">Click me</button>
```

### ID Selectors
```css
#header { background: navy; }         /* Element with id="header" */
#sidebar { width: 300px; }            /* Element with id="sidebar" */
```

```html
<div id="header">Header content</div>
<div id="sidebar">Sidebar content</div>
```

### Attribute Selectors
```css
input[type="text"] { border: 1px solid gray; }
a[href^="https"] { color: green; }
img[alt] { border: 2px solid blue; }
```

### Combination Selectors
```css
/* Descendant selector */
div p { color: red; }           /* p inside div */

/* Child selector */
div > p { font-weight: bold; }  /* p directly inside div */

/* Adjacent sibling */
h1 + p { margin-top: 0; }       /* p immediately after h1 */

/* Multiple selectors */
h1, h2, h3 { color: navy; }     /* All h1, h2, and h3 elements */
```

### Universal Selector
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```

---

## Colors and Backgrounds

### Color Values
```css
/* Named colors */
color: red;
color: blue;
color: lightgray;

/* Hexadecimal */
color: #ff0000;    /* Red */
color: #00ff00;    /* Green */
color: #0000ff;    /* Blue */

/* RGB */
color: rgb(255, 0, 0);        /* Red */
color: rgb(0, 255, 0);        /* Green */

/* RGBA (with transparency) */
color: rgba(255, 0, 0, 0.5);  /* Semi-transparent red */

/* HSL */
color: hsl(0, 100%, 50%);     /* Red */
color: hsl(120, 100%, 50%);   /* Green */
```

### Background Properties
```css
.box {
    /* Background color */
    background-color: lightblue;
    
    /* Background image */
    background-image: url('image.jpg');
    
    /* Background properties */
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    
    /* Shorthand */
    background: lightblue url('image.jpg') no-repeat center/cover;
}
```

### Gradients
```css
/* Linear gradient */
background: linear-gradient(to right, red, blue);
background: linear-gradient(45deg, #ff0000, #0000ff);

/* Radial gradient */
background: radial-gradient(circle, red, blue);
```

---

## Typography

### Font Properties
```css
.text-style {
    /* Font family */
    font-family: Arial, sans-serif;
    font-family: 'Times New Roman', serif;
    font-family: 'Courier New', monospace;
    
    /* Font size */
    font-size: 16px;        /* Pixels */
    font-size: 1.2em;       /* Relative to parent */
    font-size: 1.2rem;      /* Relative to root */
    font-size: 120%;        /* Percentage */
    
    /* Font weight */
    font-weight: normal;    /* 400 */
    font-weight: bold;      /* 700 */
    font-weight: 300;       /* Light */
    font-weight: 900;       /* Extra bold */
    
    /* Font style */
    font-style: normal;
    font-style: italic;
    
    /* Text decoration */
    text-decoration: none;
    text-decoration: underline;
    text-decoration: line-through;
    
    /* Text alignment */
    text-align: left;
    text-align: center;
    text-align: right;
    text-align: justify;
    
    /* Text transform */
    text-transform: uppercase;
    text-transform: lowercase;
    text-transform: capitalize;
    
    /* Line height */
    line-height: 1.5;
    line-height: 24px;
    
    /* Letter spacing */
    letter-spacing: 2px;
    
    /* Word spacing */
    word-spacing: 5px;
}
```

### Web Fonts (Google Fonts)
```html
<!-- In HTML head -->
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
```

```css
body {
    font-family: 'Roboto', sans-serif;
}
```

---

## Box Model

Every HTML element is a rectangular box with four parts:

```
┌─────────────────────────────────────┐
│             Margin                  │
│  ┌───────────────────────────────┐  │
│  │           Border              │  │
│  │  ┌─────────────────────────┐  │  │
│  │  │        Padding          │  │  │
│  │  │  ┌───────────────────┐  │  │  │
│  │  │  │     Content       │  │  │  │
│  │  │  └───────────────────┘  │  │  │
│  │  └─────────────────────────┘  │  │
│  └───────────────────────────────┘  │
└─────────────────────────────────────┘
```

### Box Model Properties
```css
.box {
    /* Content area */
    width: 300px;
    height: 200px;
    
    /* Padding (inside the element) */
    padding: 20px;                    /* All sides */
    padding: 10px 20px;              /* Top/bottom, Left/right */
    padding: 10px 15px 20px 25px;    /* Top, Right, Bottom, Left */
    padding-top: 10px;
    padding-right: 15px;
    padding-bottom: 20px;
    padding-left: 25px;
    
    /* Border */
    border: 2px solid black;
    border-width: 2px;
    border-style: solid;              /* solid, dashed, dotted, double */
    border-color: black;
    border-radius: 10px;              /* Rounded corners */
    
    /* Margin (outside the element) */
    margin: 20px;                     /* All sides */
    margin: 10px auto;                /* Top/bottom 10px, Left/right centered */
    margin-top: 10px;
    margin-right: 15px;
    margin-bottom: 20px;
    margin-left: 25px;
}
```

### Box Sizing
```css
/* Default box sizing */
.box1 {
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 300 + 40 + 10 = 350px */
}

/* Border-box sizing (recommended) */
.box2 {
    box-sizing: border-box;
    width: 300px;
    padding: 20px;
    border: 5px solid black;
    /* Total width = 300px (includes padding and border) */
}

/* Apply to all elements */
* {
    box-sizing: border-box;
}
```

---

## Layout and Positioning

### Display Property
```css
/* Block elements (full width, new line) */
div { display: block; }

/* Inline elements (only content width, same line) */
span { display: inline; }

/* Inline-block (content width, but can have width/height) */
img { display: inline-block; }

/* Hide elements */
.hidden { display: none; }

/* Flex container */
.flex-container { display: flex; }

/* Grid container */
.grid-container { display: grid; }
```

### Position Property
```css
/* Static (default) */
.static { position: static; }

/* Relative (relative to normal position) */
.relative {
    position: relative;
    top: 20px;
    left: 30px;
}

/* Absolute (relative to positioned parent) */
.absolute {
    position: absolute;
    top: 50px;
    right: 100px;
}

/* Fixed (relative to viewport) */
.fixed {
    position: fixed;
    bottom: 20px;
    right: 20px;
}

/* Sticky (combination of relative and fixed) */
.sticky {
    position: sticky;
    top: 0;
}
```

### Float (Legacy Layout)
```css
.left { float: left; }
.right { float: right; }
.clearfix::after {
    content: "";
    display: table;
    clear: both;
}
```

---

## Flexbox

Flexbox is perfect for one-dimensional layouts (rows or columns):

### Flex Container
```css
.container {
    display: flex;
    
    /* Direction */
    flex-direction: row;          /* Default: left to right */
    flex-direction: column;       /* Top to bottom */
    flex-direction: row-reverse;  /* Right to left */
    flex-direction: column-reverse; /* Bottom to top */
    
    /* Wrap */
    flex-wrap: nowrap;           /* Default: single line */
    flex-wrap: wrap;             /* Multiple lines */
    
    /* Justify content (main axis) */
    justify-content: flex-start; /* Default: start */
    justify-content: center;     /* Center */
    justify-content: flex-end;   /* End */
    justify-content: space-between; /* Space between items */
    justify-content: space-around;  /* Space around items */
    justify-content: space-evenly;  /* Equal space */
    
    /* Align items (cross axis) */
    align-items: stretch;        /* Default: full height */
    align-items: flex-start;     /* Top */
    align-items: center;         /* Center */
    align-items: flex-end;       /* Bottom */
    
    /* Gap between items */
    gap: 20px;
}
```

### Flex Items
```css
.item {
    /* Flex grow (how much to grow) */
    flex-grow: 1;               /* Grow equally */
    flex-grow: 2;               /* Grow twice as much */
    
    /* Flex shrink (how much to shrink) */
    flex-shrink: 1;             /* Default */
    flex-shrink: 0;             /* Don't shrink */
    
    /* Flex basis (initial size) */
    flex-basis: auto;           /* Default */
    flex-basis: 200px;          /* Fixed width */
    
    /* Shorthand */
    flex: 1;                    /* flex-grow: 1, flex-shrink: 1, flex-basis: 0 */
    flex: 0 0 200px;            /* Don't grow/shrink, 200px width */
    
    /* Align individual item */
    align-self: center;
}
```

### Common Flexbox Patterns
```css
/* Center content */
.center {
    display: flex;
    justify-content: center;
    align-items: center;
}

/* Navigation bar */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

/* Card layout */
.cards {
    display: flex;
    gap: 20px;
    flex-wrap: wrap;
}
.card {
    flex: 1 1 300px; /* Grow, shrink, min 300px */
}
```

---

## Grid Layout

CSS Grid is perfect for two-dimensional layouts:

### Grid Container
```css
.grid-container {
    display: grid;
    
    /* Define columns */
    grid-template-columns: 200px 1fr 200px;        /* Fixed, flexible, fixed */
    grid-template-columns: repeat(3, 1fr);          /* 3 equal columns */
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); /* Responsive */
    
    /* Define rows */
    grid-template-rows: auto 1fr auto;              /* Header, content, footer */
    grid-template-rows: repeat(3, 200px);           /* 3 rows of 200px each */
    
    /* Gap between grid items */
    gap: 20px;
    grid-gap: 20px; /* Older syntax */
    
    /* Named grid lines */
    grid-template-columns: [start] 250px [main-start] 1fr [main-end] 250px [end];
}
```

### Grid Items
```css
.grid-item {
    /* Position by line numbers */
    grid-column-start: 1;
    grid-column-end: 3;
    grid-row-start: 1;
    grid-row-end: 2;
    
    /* Shorthand */
    grid-column: 1 / 3;     /* Spans from line 1 to 3 */
    grid-row: 1 / 2;        /* Spans from line 1 to 2 */
    
    /* Span syntax */
    grid-column: span 2;    /* Spans 2 columns */
    grid-row: span 3;       /* Spans 3 rows */
    
    /* Area shorthand */
    grid-area: 1 / 1 / 2 / 3; /* row-start / col-start / row-end / col-end */
}
```

### Named Grid Areas
```css
.grid-layout {
    display: grid;
    grid-template-columns: 200px 1fr 200px;
    grid-template-rows: auto 1fr auto;
    grid-template-areas:
        "header header header"
        "sidebar main ads"
        "footer footer footer";
    gap: 20px;
}

.header { grid-area: header; }
.sidebar { grid-area: sidebar; }
.main { grid-area: main; }
.ads { grid-area: ads; }
.footer { grid-area: footer; }
```

---

## Responsive Design

### Media Queries
```css
/* Mobile first approach */
.container {
    width: 100%;
    padding: 10px;
}

/* Tablet and up */
@media (min-width: 768px) {
    .container {
        max-width: 750px;
        margin: 0 auto;
        padding: 20px;
    }
}

/* Desktop and up */
@media (min-width: 1024px) {
    .container {
        max-width: 1200px;
        padding: 40px;
    }
}

/* Print styles */
@media print {
    .no-print {
        display: none;
    }
}
```

### Flexible Units
```css
.responsive {
    /* Relative units */
    width: 50%;              /* Percentage of parent */
    font-size: 1.2em;        /* Relative to parent font size */
    font-size: 1.2rem;       /* Relative to root font size */
    
    /* Viewport units */
    width: 100vw;            /* 100% of viewport width */
    height: 100vh;           /* 100% of viewport height */
    font-size: 4vw;          /* 4% of viewport width */
    
    /* Modern units */
    width: clamp(300px, 50%, 800px); /* Min 300px, preferred 50%, max 800px */
    font-size: clamp(16px, 4vw, 24px);
}
```

### Responsive Images
```css
img {
    max-width: 100%;
    height: auto;
}

/* Responsive background images */
.hero {
    background-image: url('mobile.jpg');
    background-size: cover;
    background-position: center;
}

@media (min-width: 768px) {
    .hero {
        background-image: url('desktop.jpg');
    }
}
```

---

## Animations and Transitions

### Transitions
```css
.button {
    background: blue;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    
    /* Transition properties */
    transition: background-color 0.3s ease;
    transition: all 0.3s ease-in-out;
}

.button:hover {
    background: darkblue;
    transform: scale(1.1);
}
```

### Transforms
```css
.transform-examples {
    /* 2D Transforms */
    transform: translate(50px, 100px);    /* Move */
    transform: rotate(45deg);             /* Rotate */
    transform: scale(1.5);                /* Scale up */
    transform: skew(10deg, 20deg);        /* Skew */
    
    /* 3D Transforms */
    transform: rotateX(45deg);
    transform: rotateY(45deg);
    transform: translateZ(100px);
    
    /* Multiple transforms */
    transform: translate(50px, 100px) rotate(45deg) scale(1.2);
}
```

### Keyframe Animations
```css
/* Define animation */
@keyframes slideIn {
    0% {
        transform: translateX(-100%);
        opacity: 0;
    }
    50% {
        opacity: 0.5;
    }
    100% {
        transform: translateX(0);
        opacity: 1;
    }
}

/* Apply animation */
.slide-in {
    animation: slideIn 1s ease-in-out;
}

/* Animation properties */
.animated {
    animation-name: slideIn;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: 0.5s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    animation-fill-mode: forwards;
    
    /* Shorthand */
    animation: slideIn 2s ease-in-out 0.5s infinite alternate forwards;
}
```

---

## Pseudo-classes and Pseudo-elements

### Pseudo-classes
```css
/* Link states */
a:link { color: blue; }          /* Unvisited links */
a:visited { color: purple; }     /* Visited links */
a:hover { color: red; }          /* Mouse over */
a:active { color: orange; }      /* Being clicked */
a:focus { outline: 2px solid blue; } /* Keyboard focus */

/* Form states */
input:focus { border-color: blue; }
input:valid { border-color: green; }
input:invalid { border-color: red; }
input:disabled { opacity: 0.5; }

/* Structural pseudo-classes */
li:first-child { font-weight: bold; }
li:last-child { margin-bottom: 0; }
li:nth-child(odd) { background: #f0f0f0; }
li:nth-child(3n) { color: red; }        /* Every 3rd item */

/* Other pseudo-classes */
p:empty { display: none; }
input:checked + label { color: green; }
```

### Pseudo-elements
```css
/* Before and after */
.quote::before {
    content: '"';
    font-size: 2em;
    color: gray;
}

.quote::after {
    content: '"';
    font-size: 2em;
    color: gray;
}

/* First letter and line */
p::first-letter {
    font-size: 3em;
    font-weight: bold;
    float: left;
}

p::first-line {
    font-weight: bold;
    color: navy;
}

/* Selection */
::selection {
    background: yellow;
    color: black;
}
```

---

## CSS Variables

CSS Variables (Custom Properties) allow you to reuse values:

```css
:root {
    /* Define variables */
    --primary-color: #3498db;
    --secondary-color: #2ecc71;
    --font-size-large: 24px;
    --font-size-medium: 18px;
    --font-size-small: 14px;
    --border-radius: 8px;
    --shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

/* Use variables */
.button {
    background: var(--primary-color);
    color: white;
    font-size: var(--font-size-medium);
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
}

.button:hover {
    background: var(--secondary-color);
}

/* Variables with fallbacks */
.element {
    color: var(--text-color, black); /* Use black if --text-color is not defined */
}

/* Local variables */
.dark-theme {
    --primary-color: #2c3e50;
    --text-color: white;
}
```

---

## Best Practices

### 1. Use External CSS
```html
<!-- Good -->
<link rel="stylesheet" href="styles.css">

<!-- Avoid -->
<p style="color: red;">Text</p>
```

### 2. Organize Your CSS
```css
/* 1. Reset/Normalize */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* 2. Base styles */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

/* 3. Layout */
.container {
    max-width: 1200px;
    margin: 0 auto;
}

/* 4. Components */
.button {
    /* Button styles */
}

/* 5. Utilities */
.text-center { text-align: center; }
.hidden { display: none; }
```

### 3. Use Meaningful Class Names
```css
/* Good */
.navigation-menu { }
.product-card { }
.call-to-action-button { }

/* Bad */
.red-text { }
.big-box { }
.thing1 { }
```

### 4. Keep Specificity Low
```css
/* Good */
.button { }
.button--primary { }

/* Bad */
div.container .content .button.primary { }
```

### 5. Use CSS Reset or Normalize
```css
/* Simple reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Or use normalize.css */
```

### 6. Mobile-First Approach
```css
/* Mobile styles first */
.container {
    width: 100%;
    padding: 15px;
}

/* Then add desktop styles */
@media (min-width: 768px) {
    .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 30px;
    }
}
```

---

## Practice Exercises

### Exercise 1: Style a Simple Blog
Create CSS for a blog with:
- Header with navigation
- Main content area
- Sidebar
- Footer
- Responsive design

### Exercise 2: Create a Card Component
Style a card component with:
- Image at the top
- Title and description
- Action buttons
- Hover effects
- Shadow and rounded corners

### Exercise 3: Build a Navigation Menu
Create a responsive navigation that:
- Horizontal on desktop
- Hamburger menu on mobile
- Dropdown submenus
- Hover and focus states

### Exercise 4: Design a Form
Style a contact form with:
- Proper spacing and alignment
- Custom styled inputs
- Focus states
- Validation styling
- Submit button with hover effect

---

## Quick Reference Cheat Sheet

| Property | Purpose | Example |
|----------|---------|---------|
| `color` | Text color | `color: red;` |
| `background` | Background color/image | `background: blue;` |
| `font-size` | Text size | `font-size: 16px;` |
| `margin` | Outside spacing | `margin: 20px;` |
| `padding` | Inside spacing | `padding: 10px;` |
| `border` | Element border | `border: 1px solid black;` |
| `width` | Element width | `width: 300px;` |
| `height` | Element height | `height: 200px;` |
| `display` | Display type | `display: flex;` |
| `position` | Positioning method | `position: relative;` |

### Common Values
| Unit | Description | Example |
|------|-------------|---------|
| `px` | Pixels (absolute) | `font-size: 16px;` |
| `%` | Percentage of parent | `width: 50%;` |
| `em` | Relative to parent font | `font-size: 1.2em;` |
| `rem` | Relative to root font | `font-size: 1.2rem;` |
| `vw` | Viewport width | `width: 100vw;` |
| `vh` | Viewport height | `height: 100vh;` |

---

## Resources for Further Learning

- [MDN CSS Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS) - Comprehensive CSS reference
- [CSS-Tricks](https://css-tricks.com/) - Tips, tricks, and tutorials
- [Flexbox Froggy](https://flexboxfroggy.com/) - Interactive Flexbox game
- [Grid Garden](https://cssgridgarden.com/) - Interactive CSS Grid game
- [Can I Use](https://caniuse.com/) - Browser support tables
- [CSS Validator](https://jigsaw.w3.org/css-validator/) - Validate your CSS
- [Coolors](https://coolors.co/) - Color palette generator
- [Google Fonts](https://fonts.google.com/) - Free web fonts

---

**Remember**: CSS is all about practice and experimentation. Don't be afraid to try different properties and values to see what happens!

Happy styling! ✨
