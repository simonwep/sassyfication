<br>
<h3 align="center">
   <img width="500px" src="https://user-images.githubusercontent.com/30767528/55688316-64e1a300-5977-11e9-9e6d-280b6a41b545.png" alt="Logo">
   <h5 align="center">Write less, do more.</h5>
</h3>

<br>
<p align="center">
   <a href="https://www.npmjs.com/package/sassyfication">
       <img alt="Current version" src="https://img.shields.io/badge/version-0.1.1-536dc6.svg?style=popout-square">
   </a>
   <a href="https://www.npmjs.com/package/sassyfication">
       <img alt="NPM Downloads" src="https://img.shields.io/npm/dm/sassyfication.svg?style=popout-square&color=C6538C">
   </a>
   <a href="https://www.patreon.com/simonwep">
       <img alt="Support me" src="https://img.shields.io/badge/patreon-support%20me-9f53c6.svg?style=popout-square">
   </a>
</p>
<br>

Sassyfication is a SASS library with mixins which merge frequently combined css attributes into one.

### Setup

Install via npm:
```bash
$ npm install sassyfication
```
Install via yarn:

```bash
$ yarn add sassyfication
```

### Utilities
1. [position](#positiontop-right-bottom-left)
2. [pseudo](#pseudoposition-absolute-content-)
3. [font](#fontfont-weight-font-size-letter-spacing)
4. [white-space-overflow](#whitespaceoverflowwhite-space-nowrap-overflow-hidden-text-overflow-ellipsis)
5. [stroke](#strokestroke-stroke-width-stroke-linecap-stroke-dasharray-stroke-dashoffset)
6. [flex](#flexflex-direction-align-items-justify-content)
7. [inline-flex](#inline-flexflex-direction-align-items-justify-content)
8. [flex-self](#flex-selfalign-self-center-justify-self-align-self)
9. [animate](#animateprops)
10. [sequential-animation-delay](#sequentialanimationdelaychild-count-multiplier)
11. [order](#orderlist)
12. [size](#sizewidth-auto-height-width)
13. [width](#widthwidth-min-width-max-width)
14. [height](#heightheight-min-height-max-height)
15. [fixed-width](#fixed-widthwidth)
16. [fixed-height](#fixed-heightheight)
17. [fixed-size](#fixed-sizewidth-auto-height-width)

There are also [breakpoints](#breakpoints), adapted from bootstrap.

#### position($top, $right, $bottom, $left)
Shorthand for `top`, `right`, `bottom`, `left` props.
```scss
// Example
.element { 
    @include position(10px, 20px, 30px, 40px);
}

// CSS Output
.element {
    top: 10px;
    right: 20px;
    bottom: 30px;
    left: 40px;
}
```

#### pseudo($position: absolute, $content: '') 
Simplifies pseudo-element initialization.
```scss
// Example
.element {
    @include pseudo();
}

// CSS Output
.element {
   position: absolute;
   content: '';
}
```

#### font($font-weight, $font-size, $letter-spacing) 
One-liner for font styling.
```scss
// Example
.element {
    @include font(600, 1.2em, 0.05em);
}

// CSS Output
.element {
    font-weight: 600;
    font-size: 1.2em;
    letter-spacing: 0.05em;
}
```

#### white-space-overflow($white-space: nowrap, $overflow: hidden, $text-overflow: ellipsis) 
One-liner for text related overflow handling.
```scss
// Example
.element {
    @include white-space-overflow();
}

// CSS Output
.element {
    overflow: hidden; 
    white-space: nowrap; 
    text-overflow: ellipsis;
}
```

#### stroke($stroke, $stroke-width, $stroke-linecap, $stroke-dasharray, $stroke-dashoffset) 
One-liner for SVG stroke styles.
```scss
// Example
.element {
    @include stroke(red, 2px, round, 123, 150);
}

// CSS Output
.element {
    stroke: red;
    stroke-width: 2px;
    stroke-linecap: round;
    stroke-dasharray: 123;
    stroke-dashoffset: 150;
}
```

#### flex($flex-direction, $align-items, $justify-content, $flex-wrap) 
One-liner for flex container.
```scss
// Example
.element {
    @include flex(column, center, flex-start, wrap);
}

// CSS Output
.element {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    flex-wrap: wrap;
}

```
#### inline-flex($flex-direction, $align-items, $justify-content, $flex-wrap) 
One-liner for inline-flex container.
```scss
// Example
.element {
    @include inline-flex(column, center, flex-start, wrap);
}

// CSS Output
.element {
    display: inline-flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    flex-wrap: wrap;
}
```

#### flex-self($align-self: center, $justify-self: $align-self) 
One-liner for flex-items position.
```scss
// Example
.element {
    @include flex-self(flex-start, flex-end);
}

// CSS Output
.element {
    align-self: flex-start;
    justify-self: flex-end;
}
```

#### animate($props) 
Props are used for the animation property, @content as keyframes. Generates a random id which is used as name.
```scss
// Example
.element {
    @include animate('1s ease-in-out forwards') {
        from {
            opacity: 0;
        }
        to {
            opacity: 1;
        }
    }
}

// CSS Output
@keyframes [random-id] {
    from {
        opacity: 0;
    }
    to {
        opacity: 1;
    }
}

.element {
   animation: [random-id] 1s ease-in-out forwards;
}
```

#### sequential-animation-delay($child-count, $multiplier) 
Useful to animate a specific amount of childrens successive.
```scss
// Example
.element {
    @include sequential-animation-delay(3, 200ms);
}

// CSS Output
.element:nth-child(0) {
   animation-delay: 0ms;
}

.element:nth-child(1) {
   animation-delay: 200ms;
}

.element:nth-child(2) {
   animation-delay: 400ms;
}
```

#### order($list) 
Receives a list with selectors and order-index for flex elements. Accepts a list or map with indecies.
```scss
// Example
.element {
    @include order(('.a', '.b', '.c'));
}

// CSS Output
.element .a {
   order: 1;
}

.element .b {
   order: 2;
}

.element .c {
   order: 3;
}

```

// Width and height
#### size($height: auto, $width: $height) 
One-liner for width and height.
```scss
// Example
.element {
    @include size(20px, 30px);
}

// CSS Output
.element {
    height: 20px;
    width: 30px;
}
```
#### width($width, $min-width, $max-width) 
One-liner for max-, min- width (and width).
```scss
// Example
.element {
    @include width(10px, 5px, 20px);
}

// CSS Output
.element {
    width: 10px;
    min-width: 5px;
    max-width: 20px;
}
```
#### height($height, $min-height, $max-height) 
One-liner for max-, min- height (and height).
```scss
// Example
.element {
    @include height(10px, 5px, 20px);
}

// CSS Output
.element {
    height: 10px;
    min-height: 5px;
    max-height: 20px;
}
```
#### fixed-width($width) 
Applies the same value to max, min-width and width.
```scss
// Example
.element {
    @include fixed-width(10px);
}

// CSS Output
.element {
    width: 10px;
    min-width: 10px;
    max-width: 10px;
}
```
#### fixed-height($height) 
Applies the same value to max, min-height and height.
```scss
// Example
.element {
    @include fixed-height(10px);
}

// CSS Output
.element {
    height: 10px;
    min-height: 10px;
    max-height: 10px;
}
```
#### fixed-size($height: auto, $width: $height) 
One-liner for fixed-width and fixed-height.
```scss
// Example
.element {
    @include fixed-size(20px, 40px);
}

// CSS Output
.element {
    height: 20px;
    min-height: 20px;
    max-height: 20px;
    width: 40px;
    min-width: 40px;
    max-width: 40px;
}
```

### Breakpoints
```scss
@include mq-phones {} // Small devices (landscape phones, 576px and up)
@include mq-tablets {} // Medium devices (tablets, 768px and up)
@include mq-desktop {} // Large devices (desktops, 992px and up)
@include mq-large-desktop {} // Extra large devices (large desktops, 1200px and up)
