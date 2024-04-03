<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [CSS](#css)
  - [How to add CSS](#how-to-add-css)
    - [Inline CSS](#inline-css)
    - [Internal CSS](#internal-css)
    - [External CSS](#external-css)
  - [CSS Syntax](#css-syntax)
  - [CSS selectors](#css-selectors)
    - [CSS element selector](#css-element-selector)
    - [CSS id selector (#)](#css-id-selector-)
    - [CSS class selector (.)](#css-class-selector-)
    - [Universal selector](#universal-selector)
    - [The CSS grouping selector](#the-css-grouping-selector)
  - [CSS Colors](#css-colors)
    - [Color names](#color-names)
    - [Using Hex values](#using-hex-values)
    - [Using rgb](#using-rgb)
    - [Using hsl](#using-hsl)
    - [using rgba](#using-rgba)
    - [using hsla](#using-hsla)
  - [CSS Backgrounds](#css-backgrounds)
    - [CSS background-color](#css-background-color)
    - [CSS background-image](#css-background-image)
    - [CSS background-repeat](#css-background-repeat)
      - [repeating horizontally](#repeating-horizontally)
      - [repeating vertically](#repeating-vertically)
      - [no-repeat](#no-repeat)
    - [CSS background-position property](#css-background-position-property)
    - [CSS background-attachment](#css-background-attachment)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# CSS
CSS is the language used to style an HTML document.  
CSS stands for Cascading Style Sheets.  
CSS was created by the World Wide Web Consortium (W3C).  
CSS is used to define styles for your web pages including the design, layout, and variations in display for different devices and screen sizes.  

## How to add CSS
When a browser reads a stylesheet, it will format the related HTML document according to the information  provided in the style sheet.  
There are three ways to insert CSS:
- Inline CSS
- Internal CSS
- External CSS

### Inline CSS
To use inline styles, we add the style attribute to the html element we want to style. This attribute can contain any css property.

```html
<h1 style="color:blue; text-align:center;">Hello, World</h1>
```

### Internal CSS
The internal style is defined inside the <style></style> tags inside the head section of the html document.
```html
<!DOCTYPE html>
<html>
<head>
<style>
    body {
    background-color: linen;
    }

    h1 {
    color: maroon;
    margin-left: 40px;
    }
</style>
</head>
<body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
</body>
</html>
```

### External CSS
Create an external stylesheet and write all the CSS there, then include a reference to this CSS file inside of HTML.

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" href="styles.css">
</head>
<body>
    <h1>This is a heading</h1>
    <p>This is a paragraph.</p>
</body>
</html>
```
and here is the styles.css file
```css
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

## CSS Syntax
A CSS rule consists of a selector and a declaration block.  
![Selector and declaration block](./images/css-img-1.png)

```h1``` is the selector.  
The declaration block is from the opening curly brace to the closing curly brace.  
```color: red``` is a declaration.   
```border: 3px solid red``` is a declaration.  
```color``` is a property.  
```red``` is a value.
```border``` is a property.  
```3px solid red``` is a value.  

```Selector```: points to the html element that you want to style.  
```declaration block```: contains one or more declarations separated by a semi-colon. It defines the styles that the element(s) is going to have.  
Each declaration includes a CSS property name and a value, separated by a semi-colon.  

## CSS selectors
A css selector selects HTML element(s) that you want to style.  
CSS selectors can be divided into 5 categories:  
- **Simple selectors** - select elements based on name, id and class.  
- **Combinator selectors** - select elements based on the relationship between them.
- **pseudo-class selectors** - select elements based on a certain state.  
- **attribute selectors** - select elements based on an attribute or attribute value.  

### CSS element selector
Selects an element based on the element name.  
```html
<p>Hello, world </p>
<p>How do you do, world</p>
```
```css
p {
    border: 3px solid red;
}
```

### CSS id selector (#)
Uses the id attribute of an element to select a specific element.  
Elements cannot share id, and id is only specific to one element.  
To select an element based on the id, we write the hash (#) character, followed by the id of the element that we want to select.  
```html
<h3 id="title1">Hello, world</h3>
```
```css
#title1 {
    color: crimson;
}
```

### CSS class selector (.)
Selects HTML elements with a specific class attribute.  
To select elements with a specific class, write a period (.) character, followed by the class name.  
```html
<h4 class="title4">why learn CSS</h4>
<h4 class="title4">advantages of CSS</h4>
```
```css
.title4 {
    text-align: center;
}
```
HTML elements can have more than 1 class
```html
<p class="red large center">CSS is fun</p>
```
```css
.red {
    color: red;
}

.large {
    font-size: 48px;
}

.center {
    text-align: center;
}
```

### Universal selector
The css universal selector selects all html elements.
```html
<h1>CSS</h1>
<h2 class="sub-title">Why Learn CSS</h2>
<p>To style HTML pages</p>
<p>Make pages responsive to all devices</p>
```
```css
*{
    text-align: center;
    color: black;
}
```

### The CSS grouping selector
The CSS grouping selector selects all the HTML elements with the same style definitions.  
In the code below, h1, h2 and p have same style definitions.  
```css
h1 {
    color: red;
    border: 2px solid green;
}

h2 {
    color: red;
    border: 2px solid green;
}

p {
    color: red;
    border: 3px solid green;
}
```

It would be better to group these selectors to minimize the code, to group these selectors, separate each selector with a comma.  
```css
h1, h2, p {
    color: red;
    border: 3px solid red;
}
```

## CSS Colors
Colors are defined using:
- Predefined color names
- rgb
- hex
- hsl
- rgba
- hsla

### Color names
A color can be specified by using a predefined color name.
```css
h1 {
    color: red;
}
```
### Using Hex values
A hexadecimal color is specified with ```#RRGGBB```  where RR (red), GG(green) and BB(blue) hexadecimal integers specify the components of the color.  
The highest is ff and lowest 00.
```css
h1 {
    color: #ff6347;
}
/* 3 digits hex values */
h2 {
    color: #f2a;
}
```
### Using rgb
A color can be specified as an rgb value using the formula:
```rgb(red, green, blue)```.  
Each parameter (red, green, blue) defines the intensity of the color between 0 and 255.
```css
h1 {
    color: rgb(255, 99, 71);
}
```
### Using hsl
Colors can also be specified using hue, saturation, andl lightness in the form ```hsl(hue, saturation, lightness)```.  
```hue``` is the a degree on the color wheel from 0 to 360 where 0 is red, 120 is green and 240 is blue.  
```saturation``` is a percentage value. 0% means a shade of gray and 100% is the full color.   
```lightness``` is also a percentage where 0% is black, 50% is neither light or dark, 100% is white.
```css
h1 {
    color: hsl(9, 100%, 64%);
}
```
### using rgba
rgba color values are an extension of the rgb color values with an alpha channel - which specifies the opacity for the color between 0 and 1.
```css
h1 {
    color: rgba(255, 99, 71, 0.5);
}
```
### using hsla
hsla color values are an extension of the hsl color values with an alpha channel - which specifies the opacity for a color.
```css
h1 {
    color: hsla(9, 100%, 64%, 0.5);
}
```

## CSS Backgrounds
CSS backround properties are used to add background effects for elements.  
The most common properties are:
- background-color
- background-image
- background-repeat
- background-attachment
- background-position
- background (shorthand property)

### CSS background-color
This property specifies the background-color of an element.  
It can accept any valid color name, a hex value or an rgb value.  
```css
body {
    background-color: red;
}
```
### CSS background-image
This property specifies an image to be used as the background of an element.  
The path to the image is supplied in the ```url()```
```css
body {
    background-image: url("world.png")
}
```
### CSS background-repeat
By default, the background image property repeats an image both horizontally and vertically.  
Some images should be repeated only horizontally or only vertically or should not be repeated at all, else they will look strange.  
#### repeating horizontally
```css
body {
    background-image: url("world.jpeg");
    background-repeat: repeat-x;
}
```
#### repeating vertically
```css
body {
    background-image: url("world.jpeg");
    background-repeat: repeat-y;
}
```
#### no-repeat
```css
body {
    background-image: url("world.jpeg");
    background-repeat: no-repeat;
}
```
### CSS background-position property
Used to specify the position of the background image.  
For example center, right, top, left, e.t.c
```css
body {
  background-image: url("world.png");
  background-repeat: no-repeat;
  background-position: right top;
}
```
### CSS background-attachment
This property specifies whether the image should scroll or be fixed (not scroll with the rest of the page).
```css
body {
  background-image: url("img_tree.png");
  background-attachment: fixed;
}
```
