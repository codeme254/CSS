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
  - [CSS borders](#css-borders)
    - [border-style](#border-style)
    - [border-width](#border-width)
    - [border-color](#border-color)
    - [Individual border sides](#individual-border-sides)
    - [border shorthand property](#border-shorthand-property)
    - [border-radius](#border-radius)
  - [CSS Margins](#css-margins)
  - [CSS padding](#css-padding)
  - [CSS Height and Width](#css-height-and-width)
    - [max-width](#max-width)
    - [min-width](#min-width)
    - [max-height](#max-height)
    - [min-height](#min-height)
  - [CSS Box Model](#css-box-model)
  - [CSS Outline](#css-outline)
    - [outline-style](#outline-style)
    - [outline-width](#outline-width)
    - [outline-color](#outline-color)
    - [Outline shorthand](#outline-shorthand)
    - [outline-offset](#outline-offset)
  - [CSS text](#css-text)
    - [color](#color)
    - [text alignment](#text-alignment)
      - [text-align-last](#text-align-last)
    - [text direction (direction property)](#text-direction-direction-property)
    - [text decoration](#text-decoration)
      - [text-decoration-line](#text-decoration-line)
      - [text-decoration-color](#text-decoration-color)
      - [text-decoration-style](#text-decoration-style)
      - [specify the thickness of the decoration line](#specify-the-thickness-of-the-decoration-line)
      - [the shorthand](#the-shorthand)
    - [text transformation](#text-transformation)
    - [text spacing](#text-spacing)
      - [text-indent](#text-indent)
      - [letter-spacing](#letter-spacing)
      - [line-height](#line-height)
      - [word-spacing](#word-spacing)
    - [Text shadow](#text-shadow)
  - [CSS Fonts](#css-fonts)
    - [Generic font families](#generic-font-families)
    - [CSS font-family property](#css-font-family-property)
    - [Web Safe Fonts](#web-safe-fonts)
    - [font-style](#font-style)
    - [font-weight](#font-weight)
    - [font-variant](#font-variant)
    - [font-size](#font-size)
      - [Setting font size with em](#setting-font-size-with-em)
      - [Responsive font sizes](#responsive-font-sizes)

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

## CSS borders
The CSS border properties will allow you to specify the style, width and color of an element's border.

### border-style
Allows you to specify what kind of border to display.  
- dotted - defines a dotted border.  
- dashed - defines a dashed border.
- solid - defines a solid border.
- double - defines a double border.
- groove - defines a 3D grooved border
- ridge - defines a 3D ridged border.
- inset - defines a 3D inset border.
- outset - defines a 3D outset border.
- none - defines no border.
- hidden - defines a hidden border.

The border-style property can have from one to four values for the top border, right border, bottom border and the left border respectively.

```css
p.dotted {border-style: dotted;}
p.dashed {border-style: dashed;}
p.solid {border-style: solid;}
p.double {border-style: double;}
p.groove {border-style: groove;}
p.ridge {border-style: ridge;}
p.inset {border-style: inset;}
p.outset {border-style: outset;}
p.none {border-style: none;}
p.hidden {border-style: hidden;}
/* 4 values */
p.mix {border-style: dotted dashed solid double;}
```

### border-width
Specifies the width (thickness) of the four borders.  
The width can be set as a specific size (px, pt, cm, em).  
You can also pass one of the predefined values. (```thin, medium or thick```)
```css
.element1 {
    border-style: solid;
    border-width: 5px;
}
.element2 {
    border-style: solid;
    border-width: thick;
}
.element3 {
    border-style: solid;
    border-width: thin;
}
.element4 {
    border-style: solid;
    border-width: medium;
}
```
### border-color
This property sets the color of the four borders.
```css
.element {
    border-style: solid;
    border-color: red;
}
```

### Individual border sides
There are also properties for specifying each of the borders (top, right, bottom, left).  
```css
#element1 {
    border-top-style: dotted;
    border-right-style: solid;
    border-bottom-style: dotted;
    border-left-style: dashed;
}
```
### border shorthand property
It is possible to specify all the individual border properties in one property.  
The border property is a shorthand for the following individual border properties.  
- border-width
- border-style
- border-color  
example
```css
#element1 {
    border: 3px solid red;
}
```
You can also specify these properties for just one side.  
```css
#element1 {
    border-left: 3px solid red;
    border-right: 3px solid green;
    border-bottom: 3px solid purple;
    border-top: 3px dashed yellow;
}
```
### border-radius
The border-radius property is used to add rounded borders to an element.  
```css
p {
    border-radius: 5px;
}
```

## CSS Margins
Margins are used to create space around elements, outside of any defined borders.
```css
#element{
    margin: 30px;
}
```
This will set a margin of 30 pixels to the top, right, bottom and left of the element.  
You can also specify margin for each side of an element.
```css
#element{
    margin-top: 20px;
    margin-right: 50px;
    margin-bottom: 80px;
    margin-left: 55px;
}
```
To shorten the code, it is possible to specify all the margin properties in one property in a clockwise manner (top, right, bottom, left) using the margin property.
```css
#element {
    margin: 20px 50px 80px 55px;
}
```
We can shorten the code further by supplying two values where the first value will represent top and bottom margin and the second value will represent the left and right margin.
```css
#element {
    margin: 20px 50px;
}
```
When we use the ```auto``` keyword on the horizontal, the element will be centered horizontally within its container.
```css
#element {
    margin: auto;
}
```

## CSS padding
Padding is used to create space around an element's content, inside any defined borders.  
We can specify padding for each side of an element.  
```css
#element {
  padding-top: 50px;
  padding-right: 30px;
  padding-bottom: 50px;
  padding-left: 80px;
}
```
To shorten the code, we can specify all the properties in one padding property in a clockwise manner (top, right, bottom, left).
```css
#element {
  padding: 25px 50px 75px 100px;
}
```
We can shorten this further to pass only 2 values where the first value will represent the top and bottom padding and the second value will represent the left and right padding.  
```css
#element {
  padding: 25px 50px;
}
```
If all the four sides have the same padding, we can pass one value which will represent the padding on all the four sides.  
```css
#element {
  padding: 25px;
}
```
## CSS Height and Width
The height and width properties are used to set the height and width of an element.  
```css
#element {
    height: 200px;
    width: 50%;
}
```
### max-width
It is used to set the maximum width of an element (the element cannot have a width more than the max-width regardless of the amount of content).
```css
#element {
    max-width: 500px;
}
```
### min-width
it is used to set the minimum width of an element. The element cannot shrink past this width.
```css
#element {
    min-width: 200px;
}
```
### max-height
it is used to set the maximum height of an element, the element cannot grow vertically past this height.
```css
#element {
    max-height: 500px;
}
```
### min-height
it is used to set the minimum height of an element. The element cannot shrink past this size.
```css
#element {
    min-height: 500px;
}
```

## CSS Box Model
The CSS box model is essentially a box that wraps around every element.  
It consists of content, padding, borders and margins as shown in the image below.  
![Box model illustration](./images/box-model.png)
- **Content** - The content of the box, where text and images appear.
- **Padding** - Clears and area around the content/an area around the content.
- **Border** - The line that surrounds an element providing a visual boundary that can be customized in terms of style, width and color.
- **Margin** - An area outside the defined borders of an element.

## CSS Outline
An outline is a line drawn outside the element's border to make the element stand out.  
CSS has the following outline properties:
- outline-style
- outline-color
- outline-width
- outline-offset
- outline

### outline-style
It specifies the style of the outline and it can have the following values:  
- dotted - Defines a dotted outline
- dashed - Defines a dashed outline
- solid - Defines a solid outline
- double - Defines a double outline
- groove - Defines a 3D grooved outline
- ridge - Defines a 3D ridged outline
- inset - Defines a 3D inset outline
- outset - Defines a 3D outset outline
- none - Defines no outline
- hidden - Defines a hidden outline
```css
p.dotted {outline-style: dotted;}
p.dashed {outline-style: dashed;}
p.solid {outline-style: solid;}
p.double {outline-style: double;}
p.groove {outline-style: groove;}
p.ridge {outline-style: ridge;}
p.inset {outline-style: inset;}
p.outset {outline-style: outset;}
```
### outline-width
This property defines the width of the outline, and can have one of the following value:
- thin
- medium
- thick
- a specific value in px, cm, em e.t.c
```css
.element {
    outline-style: solid;
    outline-width: 5px;
}
.element2 {
    outline-style: solid;
    outline-width: thin;
}
```
### outline-color
It is used to set the color of the outline.
```css
.element {
    outline-style: solid;
    outline-width: 5px;
    outline-color: red;
}
```
### Outline shorthand
It is used to set the following individual outline properties:
- outline-width
- outline-style
- outline-color

The properties are set in the order above.
```css
#element {
    outline: thick ridge pink;
}
```
### outline-offset
It adds space between an outline and the edge/border of an element. This space is transparent.
```css
p {
  margin: 30px;
  border: 1px solid black;
  outline: 1px solid red;
  outline-offset: 15px;
}
```

## CSS text
CSS has a lot of properties for formatting text.
### color
The color property is used to set the color of text.
```css
.text {
    color: blue;
}
```
### text alignment
The text-align property is used to set the horizontal alignment of text.  
The accepted values are ```left, right, center or justify```.
```css
h1 {
    text-align: center;
}
p {
    text-align: left;
}
.text {
    text-align: justify;
}
.h4 {
    text-align: right;
}
```

#### text-align-last
This property specifies how to align the last line of a text.
```css
p {
    text-align-last: left;
}
```
### text direction (direction property)
The direction and unicode-bidi properties can be used to change the text direction of an element.  
```css
p {
    direction: rtl;
    unicode-bidi: bidi-override;
}
```
### text decoration
#### text-decoration-line
This property is used to add a decoration line to text.  
The line can either be ```overline, line-through, underline```.
```css
h1 {
  text-decoration-line: overline;
}
h2 {
  text-decoration-line: line-through;
}
h3 {
  text-decoration-line: underline;
}
p {
  text-decoration-line: overline underline;
}
```

#### text-decoration-color
It is used to set the color of the decoration line
```css
h1 {
  text-decoration-line: overline;
  text-decoration-color: red;
}
```
#### text-decoration-style
Used to set the style of the decoration line. This can be ```solid, double, dotted, ridge, dashed, wavy```
```css
h1 {
  text-decoration-line: overline;
  text-decoration-color: red;
  text-decoration-style: wavy;
}
```
#### specify the thickness of the decoration line
The text-decoration-thickness property is used to set the thickness of the decoration line.
```css
h1 {
  text-decoration-line: overline;
  text-decoration-color: red;
  text-decoration-style: wavy;
  text-decoration-thickness: 10px;
}
```
#### the shorthand
The text-decoration property is shorthand for:
- text-decoration-line (required)
- text-decoration-color (optional)
- text-decoration-style (optional)
- text-decoration-thickness (optional)

In that order
```css
p {
  text-decoration: underline red double 5px;
}
```
### text transformation
Used to specify the uppercase and lowercase letters in a text.  
Can be used to turn everything into uppercase or lowercase or capitalize the first letter of each word.

```css
.uppercase {
  text-transform: uppercase;
}
.lowercase {
  text-transform: lowercase;
}
.capitalize {
  text-transform: capitalize;
}
```
### text spacing
#### text-indent
It is used to specify the indentation of the first line of text.
```css
p {
    text-indent: 50px;
}
```
#### letter-spacing
This property is used to specify the space between the characters in a text.
```css
p {
    letter-spacing: 8px;
}
```
#### line-height
This property specifies the space between lines.  
Does not take any units.
```css
p {
    line-height: 8;
}
```
#### word-spacing
Used to specify the space between words in a text.
```css
p {
    word-spacing: 10px;
}
```
### Text shadow
The text-shadow property adds shadow to text.  
In it's simplest form, you only specify the horizontal shadow and the vertical shadow respectively.  
```css
h1 {
    text-shadow: 2px 3px;
}
```
We can then add a color
```css
h1 {
    text-shadow: 2px 3px red;
}
```
We can then add a blur effect
```css
h1 {
    text-shadow: 2px 3px 5px red;
}
```

## CSS Fonts
### Generic font families
In CSS, there are five generic font families:
1. **Serif** - they have a small stroke at the edges of each letter. They create a sense of formality and elegance.
1. **Sans-Serif** - have clean lines (no small strokes attached). They create a modern and minimalistic look.
1. **Monospace** - here all the letters have the same fixed width. They create a mechanical look. 
1. **Cursive** - they look like human handwriting.
1. **Fantasy** - they are decorative and playful fonts.
![An image to differentiate Serif vs Sans serif](./images/serif-v-sansserif.png)

### CSS font-family property
In CSS, we use the font-family property to specify the font of a text.
```css
.parapgraph {
    font-family: "Times New Roman", Times, Serif;
}
```
Times New Roman is the font we want to use, Times and Serif are fallback fonts for systems that are not compatible with our Times New Roman font.

### Web Safe Fonts
These are fonts that are universally installed across all browsers and devices.  
Here is a list of web safe fonts for HTML and CSS:  
- BArial (sans-serif)
- BVerdana (sans-serif)
- BTahoma (sans-serif)
- BTrebuchet MS (sans-serif)
- BTimes New Roman (serif)
- BGeorgia (serif)
- BGaramond (serif)
- BCourier New (monospace)
- Brush Script MT (cursive)

### font-style
It is mostly used to specify italic text.  
It has three values:  
- normal: the text is shown normally.
- italic: the text is shown in italics.
- oblique: the text is shown in italic but a bit thicker.

```css
.paragraph {
    font-style: italic;
}
.paragraph2 {
    font-style: normal;
}
```
### font-weight
It specifies the weight of the font.
```css
.paragraph {
    font-weight: normal;
}
.paragraph2 {
    font-weight: bold;
}
```
### font-variant
Specifies whether or not a text should be displayed in a small-caps font.  
In a small-caps font, all lowercase letters are converted to uppercase letters. However, the converted uppercase letters appears in a smaller font size than the original uppercase letters in the text.  

### font-size
It is used to set the size of the text.  
```css
.p {
    font-size: 40px;
}
```
#### Setting font size with em
To allow users to resize the text (in browser menu), many users use em instead of pixels.  
1em is equal to the current font size (16px).  
```1em = 16px```  
The size can be calculated from pixels to em using ```pixels/16```
```css
.p {
    font-size: 2.5em; /* 40px/16 = 2.5em*/
}
```
However, in older versions of some browsers like Internet Explorer, the text becomes larger thant it should be when made larger by the user or smaller than it should be when made smaller by the user.  
The solution that works in all browsers is to set a default font-size in percent for the body element.
```css
body {
    font-size: 100%;
}

h1 {
    font-size: 2.5em;
}
```
And that solves the issue.

#### Responsive font sizes
The text size can be set with a ```vw``` unit which means the "viewport width". That way the text size will follow the size of the browser window.

```css
h1 {
    font-size: 10vw;
}
```