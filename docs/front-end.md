
## CSS Selectors - Tags, IDs, and Classes

In this reading, we will delve into three key types of CSS selectors: Tags, IDs, and Classes. These selectors provide a powerful way to target specific HTML elements and apply styles accordingly.

Cascading Style Sheets (CSS) play a crucial role in styling web pages and understanding the role of CSS selectors for controling how styles are applied.

CSS Selectors Overview
What are CSS Selectors?

CSS selectors are patterns used to select and style HTML elements.
They define the relationship between HTML elements and the styles applied to them.
Why are Selectors Important?

Selectors allow precise targeting of specific elements.
They enable the creation of consistent and visually appealing designs.
Tag Selectors
Tag selectors target HTML elements based on their tag names. They apply styles to all instances of a particular tag.

### Syntax for Tag Selector:
```CSS
1 tagName {
2     /* Styles for the elements with the specified tag name */
3 }
```
Replace tagName with the actual HTML tag name you want to style.

### Example: Styling Headings

```
h1 { 
    /* Styles for h1 elements */ 
    color: #3366cc; 
    font-size: 24px; 
}
```

* This CSS rule targets all '<h1>' elements.
* Applies blue color and a font size of 24 pixels to all <h1> headings.

# ID Selectors
ID selectors target a specific HTML element using its unique ID attribute. The ID attribute is assigned to an HTML element to provide a unique identifier for that element within the document. ID selectors are denoted by a hash symbol '(#)' followed by the ID.

Syntax for ID Selector:
```
#yourID {
    /* Styles for the element with the specified ID */
}
```

Replace yourID with the actual ID assigned to the HTML element.

### Example: Styling a Unique Element
```
#header {
    /* Styles for the element with id="header" */ 
    background-color: #f0f0f0; 
    padding: 10px; 
}
```

* This CSS rule targets an element with the ID header
* Applies a light gray background and 10 pixels of padding to the element.

# Class Selectors
Class selectors target HTML elements with a specific class attribute. Multiple elements can share the same class. Class selectors are denoted by a period (.) followed by the class name.

Syntax for Class Selector:
```
.className {
    /* Styles for the elements with the specified class */
}
```
Replace className with the actual class name you want to style.

Example: Styling Multiple Elements
```
.highlight { 
    /* Styles for elements with class="highlight" */
    background-color: #ffd700; 
    color: #333; 
}
```
This CSS rule targets all elements with the class highlight
Applies a yellow background and dark text color to all elements with the class highlight
