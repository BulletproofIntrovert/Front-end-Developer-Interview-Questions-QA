## CSS Questions
==========

### Describe what a "reset" CSS file does and how it's useful.
It set default value for basice elements. it reduce browser inconsistence, like default line heights, margins and font sizes of headings, and so on.

### Describe Floats and how they work.
It make element horizonally be in a same level, instead of just appending down. When element is set to float: left/right. element following will move up.

### What are the various clearing techniques and which is appropriate for what context?
add a empty element `clear: both/left/right`: sematically too verbose
`overflow: hidden`: good one, but something, overflow is been used.
clearfix use :after psudo-class: require CSS3 support

### Explain CSS sprites, and how you would implement them on a page or site.
Concating small images into single large image to reduce request number. Using css background to show the right portion. 

### What are your favourite image replacement techniques and which do you use when?
use `text-index: 100%;` 
> http://css-tricks.com/examples/ImageReplacement/#leahy

### CSS property hacks, conditionally included .css files, or... something else?
```
_color: blue /* ie6 */
*color: blue /* ie6, ie7 */
color: blue\9 /* ie6, ie7, ie8 */
```
Conditional Stylesheets
```
<link rel="stylesheet" type="text/css" media="screen" href="css/style.css" />
<!--[if IE 7]><link rel="stylesheet" type="text/css" media="screen" href="css/ie7.css"  />< ![endif]-->
<!--[if IE 6]><link rel="stylesheet" type="text/css" media="screen" href="css/ie6.css"  />< ![endif]-->
```
better solution than Conditional Stylesheets
```
<!--[if lt IE 7]>      <html class="ie6"> <![endif]-->
<!--[if IE 7]>         <html class="ie7"> <![endif]-->
<!--[if IE 8]>         <html class="ie8"> <![endif]-->
<!--[if gt IE 8]><!--> <html>         <!--<![endif]-->
div.foo { color: inherit;}
.ie6 div.foo { color: #ff8000; }
```	

### How do you serve your pages for feature-constrained browsers?

### What techniques/processes do you use?

### What are the different ways to visually hide content (and make it available only for screen readers)?
negative margin 
display: none
opacity: 0.5;
visibility: hidden /* without changing the layout */

### Have you ever used a grid system, and if so, what do you prefer?
bootstrap grid system

### Have you used or implemented media queries or mobile specific layouts/CSS?
@media and , or not (min-width: 501px) (max-width: 1001px) 

### Any familiarity with styling SVG?
essentiallt same thing, fill for background-color

### How do you optimize your webpages for print?


### What are some of the "gotchas" for writing efficient CSS?

### What are the advantages/disadvantages of using CSS preprocessors? (SASS, Compass, Stylus, LESS)

### If so, describe what you like and dislike about the CSS preprocessors you have used.

### How would you implement a web design comp that uses non-standard fonts?

### Webfonts (font services like: Google Webfonts, Typekit etc.)

### Explain how a browser determines what elements match a CSS selector?

### Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.

### List as many values for the display property that you can remember.

### What's the difference between inline and inline-block?

### What's the difference between a relative, fixed, absolute and statically positioned element?