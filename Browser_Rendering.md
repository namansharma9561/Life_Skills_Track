# How does a browser render HTML, CSS, and JavaScript?

A browser converts HTML, CSS, and JavaScript into a visible webpage through several steps involving the **Document Object Model (DOM)**, the **CSS Object Model (CSSOM)**, the render tree, layout, and painting.


## 1. Parsing HTML -> Building the DOM
- The browser receives HTML from the server.
- It **parses the HTML into tokens** (tags, attributes, text).
- These tokens are used to build a tree structure called the **DOM**.
- Each HTML element becomes a node, forming a parent–child hierarchy.


## 2. Parsing CSS -> Building the CSSOM
- At the same time, the browser processes CSS (external, internal, inline).
- It **parses CSS rules and builds the CSSOM**, another tree structure.
- The CSSOM contains all style rules applied to elements.


## 3. JavaScript Execution
- When the browser encounters a `<script>` tag:
  - It usually **pauses HTML parsing**
  - Downloads and executes the script
- This happens because JavaScript can modify the DOM and CSSOM.

### Script loading options:
- `async` -> executes as soon as downloaded  
- `defer` -> executes after HTML parsing completes  


## 4. Building the Render Tree
- The browser **combines the DOM and CSSOM** to create the Render Tree.
- Only visible elements are included (e.g., `<head>` is ignored).
- Each node contains styling information.


## 5. Layout (Reflow)
- The browser calculates:
  - size  
  - position  
  - spacing (margin, padding)  
- This determines how elements appear on the screen.


## 6. Painting
- The browser **draws pixels on the screen**:
  - colors  
  - text  
  - images  
  - borders  

<br>

This sequence transforms your code into the interactive visual experience you see when you visit a website. Changes to styles or the DOM after the initial render can trigger a recalculation of styles, layout, and painting (known as reflows and repaints), which can impact performance.

## References
[1] https://medium.com/jspoint/how-the-browser-renders-a-web-page-dom-cssom-and-rendering-df10531c9969

[2] https://www.browserstack.com/guide/dom-in-web-development

