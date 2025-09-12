# HTML Guide for First-Year Students 🎓

Welcome to your complete guide to HTML (HyperText Markup Language)! This guide will teach you everything you need to know to start building web pages.

## Table of Contents
- [What is HTML?](#what-is-html)
- [Basic HTML Structure](#basic-html-structure)
- [HTML Elements and Tags](#html-elements-and-tags)
- [Text and Content Tags](#text-and-content-tags)
- [Links and Navigation](#links-and-navigation)
- [Images and Media](#images-and-media)
- [Lists](#lists)
- [Tables](#tables)
- [Forms and Input](#forms-and-input)
- [Semantic HTML](#semantic-html)
- [Block vs Inline Elements](#block-vs-inline-elements)
- [Common Attributes](#common-attributes)
- [Best Practices](#best-practices)
- [Practice Exercises](#practice-exercises)

---

## What is HTML?

HTML stands for **HyperText Markup Language**. It's the standard language used to create web pages. Think of HTML as the skeleton of a web page - it provides the structure and content, while CSS handles the styling and JavaScript adds interactivity.

### Key Points:
- HTML uses **tags** to mark up content
- Tags tell the browser how to display content
- HTML is not a programming language - it's a markup language
- Every web page you see is built with HTML

---

## Basic HTML Structure

Every HTML document follows the same basic structure:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My First Web Page</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is my first web page.</p>
</body>
</html>
```

### Breaking it down:

- `<!DOCTYPE html>` - Tells the browser this is an HTML5 document
- `<html>` - The root element that contains all other elements
- `<head>` - Contains metadata (information about the page that isn't displayed)
- `<title>` - The title that appears in the browser tab
- `<body>` - Contains all the visible content of the web page

---

## HTML Elements and Tags

### What are Tags?
Tags are keywords surrounded by angle brackets `< >`. Most tags come in pairs:
- **Opening tag**: `<tagname>`
- **Closing tag**: `</tagname>` (note the forward slash)

### Example:
```html
<h1>This is a heading</h1>
<p>This is a paragraph.</p>
```

### Self-Closing Tags
Some tags don't need a closing tag because they don't contain content:
```html
<br>      <!-- Line break -->
<img>     <!-- Image -->
<hr>      <!-- Horizontal rule -->
<input>   <!-- Form input -->
```

---

## Text and Content Tags

### Headings
HTML has 6 levels of headings, from largest to smallest:

```html
<h1>Main Heading (Largest)</h1>
<h2>Section Heading</h2>
<h3>Subsection Heading</h3>
<h4>Minor Heading</h4>
<h5>Small Heading</h5>
<h6>Smallest Heading</h6>
```

### Paragraphs and Text Formatting

```html
<p>This is a regular paragraph.</p>

<strong>This text is important (bold)</strong>
<em>This text is emphasized (italic)</em>
<b>This text is bold (visual only)</b>
<i>This text is italic (visual only)</i>
<u>This text is underlined</u>
<mark>This text is highlighted</mark>
<small>This text is smaller</small>
<del>This text is deleted (strikethrough)</del>
<ins>This text is inserted (underlined)</ins>

<br>   <!-- Line break -->
<hr>   <!-- Horizontal line -->
```

### Code and Preformatted Text

```html
<code>console.log("Hello World");</code>  <!-- Inline code -->

<pre>
    This text preserves
    spaces and line breaks
    exactly as written
</pre>

<blockquote>
    "This is a quote from someone important."
</blockquote>
```

---

## Links and Navigation

### Basic Links
```html
<a href="https://www.google.com">Visit Google</a>
<a href="about.html">About Page</a>
<a href="mailto:someone@email.com">Send Email</a>
<a href="tel:+1234567890">Call Us</a>
```

### Link Attributes
```html
<a href="https://example.com" target="_blank">Open in new tab</a>
<a href="https://example.com" title="Hover text">Link with tooltip</a>
```

### Internal Links (Anchors)
```html
<a href="#section1">Go to Section 1</a>

<!-- Later in the document -->
<h2 id="section1">Section 1</h2>
```

---

## Images and Media

### Images
```html
<img src="image.jpg" alt="Description of image">
<img src="https://example.com/image.png" alt="Remote image" width="300" height="200">
```

**Important**: Always include the `alt` attribute for accessibility!

### Audio and Video
```html
<audio controls>
    <source src="audio.mp3" type="audio/mpeg">
    Your browser doesn't support audio.
</audio>

<video controls width="400">
    <source src="video.mp4" type="video/mp4">
    Your browser doesn't support video.
</video>
```

---

## Lists

### Unordered Lists (Bullet Points)
```html
<ul>
    <li>First item</li>
    <li>Second item</li>
    <li>Third item</li>
</ul>
```

### Ordered Lists (Numbered)
```html
<ol>
    <li>First step</li>
    <li>Second step</li>
    <li>Third step</li>
</ol>
```

### Description Lists
```html
<dl>
    <dt>HTML</dt>
    <dd>HyperText Markup Language</dd>
    <dt>CSS</dt>
    <dd>Cascading Style Sheets</dd>
</dl>
```

---

## Tables

```html
<table>
    <thead>
        <tr>
            <th>Name</th>
            <th>Age</th>
            <th>City</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>John</td>
            <td>25</td>
            <td>New York</td>
        </tr>
        <tr>
            <td>Sarah</td>
            <td>30</td>
            <td>London</td>
        </tr>
    </tbody>
</table>
```

### Table Elements:
- `<table>` - The table container
- `<thead>` - Table header section
- `<tbody>` - Table body section
- `<tr>` - Table row
- `<th>` - Table header cell
- `<td>` - Table data cell

---

## Forms and Input

### Basic Form Structure
```html
<form action="/submit" method="POST">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <label for="message">Message:</label>
    <textarea id="message" name="message" rows="4"></textarea>
    
    <button type="submit">Send</button>
</form>
```

### Input Types
```html
<input type="text" placeholder="Enter text">
<input type="email" placeholder="Enter email">
<input type="password" placeholder="Enter password">
<input type="number" min="1" max="100">
<input type="date">
<input type="checkbox" id="agree">
<input type="radio" name="choice" value="yes">
<input type="file">
<input type="color">
<input type="range" min="0" max="100">
```

### Select Dropdown
```html
<select name="country">
    <option value="us">United States</option>
    <option value="uk">United Kingdom</option>
    <option value="ca">Canada</option>
</select>
```

---

## Semantic HTML

Semantic HTML uses tags that describe the meaning of content, not just appearance:

```html
<header>
    <nav>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a href="/about">About</a></li>
        </ul>
    </nav>
</header>

<main>
    <article>
        <h1>Article Title</h1>
        <p>Article content goes here...</p>
    </article>
    
    <aside>
        <h3>Related Links</h3>
        <ul>
            <li><a href="/related">Related Article</a></li>
        </ul>
    </aside>
</main>

<footer>
    <p>&copy; 2025 My Website</p>
</footer>
```

### Semantic Elements:
- `<header>` - Page or section header
- `<nav>` - Navigation links
- `<main>` - Main content area
- `<article>` - Self-contained content
- `<section>` - Thematic grouping of content
- `<aside>` - Sidebar content
- `<footer>` - Page or section footer
- `<figure>` - Self-contained content (images, diagrams)
- `<figcaption>` - Caption for figure

---

## Block vs Inline Elements

### Block Elements
Take up the full width available and start on a new line:
- `<div>`, `<p>`, `<h1>-<h6>`, `<ul>`, `<ol>`, `<li>`, `<header>`, `<footer>`, `<section>`

### Inline Elements
Take up only the space they need and don't start on a new line:
- `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<code>`

### Generic Containers
```html
<div>Block-level container</div>
<span>Inline container</span>
```

---

## Common Attributes

### Global Attributes (can be used on any element):
```html
<div id="unique-identifier">Unique ID</div>
<div class="style-class another-class">CSS classes</div>
<div title="Tooltip text">Hover for tooltip</div>
<div style="color: red;">Inline styles</div>
<div lang="es">Content in Spanish</div>
<div hidden>Hidden content</div>
```

### Form Attributes:
```html
<input required>           <!-- Field is required -->
<input readonly>           <!-- Cannot be edited -->
<input disabled>           <!-- Cannot be used -->
<input placeholder="hint">  <!-- Hint text -->
```

---

## Best Practices

### 1. Use Proper Structure
```html
<!-- Good -->
<h1>Main Title</h1>
<h2>Section Title</h2>
<h3>Subsection Title</h3>

<!-- Bad - skipping heading levels -->
<h1>Main Title</h1>
<h4>Section Title</h4>
```

### 2. Always Include Alt Text for Images
```html
<!-- Good -->
<img src="dog.jpg" alt="Golden retriever playing fetch in the park">

<!-- Bad -->
<img src="dog.jpg">
```

### 3. Use Semantic HTML
```html
<!-- Good -->
<nav>
    <ul>
        <li><a href="/">Home</a></li>
    </ul>
</nav>

<!-- Bad -->
<div>
    <div>
        <div><a href="/">Home</a></div>
    </div>
</div>
```

### 4. Indent Your Code
```html
<!-- Good -->
<html>
    <head>
        <title>My Page</title>
    </head>
    <body>
        <h1>Hello World</h1>
    </body>
</html>
```

### 5. Close Your Tags
```html
<!-- Good -->
<p>This paragraph is properly closed.</p>

<!-- Bad -->
<p>This paragraph is not closed.
```

---

## Practice Exercises

### Exercise 1: Personal Profile Page
Create an HTML page with:
- Your name as the main heading
- A paragraph about yourself
- A list of your hobbies
- A table with your favorite movies/books
- Contact information with email link

### Exercise 2: Recipe Page
Create a recipe page with:
- Recipe title
- Ingredients list (unordered)
- Instructions (ordered list)
- Cooking time and servings information
- Image of the finished dish

### Exercise 3: Simple Blog Post
Create a blog post with:
- Article title and subtitle
- Author and date information
- Multiple paragraphs with some text formatting
- A quote or highlighted section
- Related links at the bottom

---

## Quick Reference Cheat Sheet

| Element | Purpose | Example |
|---------|---------|---------|
| `<h1>-<h6>` | Headings | `<h1>Title</h1>` |
| `<p>` | Paragraph | `<p>Text here</p>` |
| `<a>` | Link | `<a href="url">Link</a>` |
| `<img>` | Image | `<img src="file.jpg" alt="desc">` |
| `<ul>/<li>` | Unordered list | `<ul><li>Item</li></ul>` |
| `<ol>/<li>` | Ordered list | `<ol><li>Step 1</li></ol>` |
| `<div>` | Block container | `<div>Content</div>` |
| `<span>` | Inline container | `<span>Text</span>` |
| `<strong>` | Important text | `<strong>Bold</strong>` |
| `<em>` | Emphasized text | `<em>Italic</em>` |

---

## Resources for Further Learning

- [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/HTML) - Comprehensive HTML documentation
- [W3Schools HTML Tutorial](https://www.w3schools.com/html/) - Interactive tutorials
- [HTML Validator](https://validator.w3.org/) - Check your HTML for errors
- [Can I Use](https://caniuse.com/) - Check browser support for HTML features

---

**Remember**: Practice makes perfect! Start with simple pages and gradually add more complex features as you become comfortable with the basics.

Happy coding! 🚀