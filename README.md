<br>
<h3 align="center">
   <img width="500px" src="https://user-images.githubusercontent.com/30767528/55688316-64e1a300-5977-11e9-9e6d-280b6a41b545.png" alt="Logo">
   <h5 align="center">Write less, do more.</h5>
</h3>

<br>
<p align="center">
   <a href="https://www.npmjs.com/package/sassyfication">
       <img alt="Current version" src="https://img.shields.io/badge/version-0.0.2-536dc6.svg?style=popout-square">
   </a>
   <a href="https://www.npmjs.com/package/sassyfication">
       <img alt="NPM Downloads" src="https://img.shields.io/npm/dm/sassyfication.svg?style=popout-square&color=C6538C">
   </a>
   <a href="https://www.patreon.com/simonwep">
       <img alt="Support me" src="https://img.shields.io/badge/patreon-support%20me-9f53c6.svg?style=popout-square">
   </a>
</p>
<br>

### Setup

Install via npm:
```bash
$ npm install sassyfication
```
Install via yarn:

```bash
$ yarn add sassyfication
```

### Utils
```scss

// General
@mixin position($top, $right, $bottom, $left) // One-liner for left, right, bottom, left
@mixin pseudo($position: absolute, $content: '') // Mostly used group in pseudo-elements
@mixin font($font-weight, $font-size, $letter-spacing) // One-liner for font styling
@mixin whiteSpaceOverflow($white-space: nowrap, $overflow: hidden, $text-overflow: ellipsis) // One-liner for text related overflow
@mixin stroke($stroke, $stroke-width, $stroke-linecap, $stroke-dasharray, $stroke-dashoffset) // One-liner for SVG styles
@mixin flex($flex-direction, $align-items, $justify-content) // One-liner for basic flex initialization
@mixin inline-flex($flex-direction, $align-items, $justify-content) // One-liner for basic inline-flex initialization
@mixin animate($props) // Props are used for the animation property, @content as keyframes
@mixin sequentialAnimationDelay($child-count, $multiplier) // Useful to animate a specific amount of childrens in sequence
@mixin order($list) // Receives a list with selectors and order-index for flex elements. 

// Width and height
@mixin size($width: auto, $height: width) // One-liner for width and height
@mixin width($width, $min-width, $max-width) // One-liner for max-, min- width (and width)
@mixin height($height, $min-height, $max-height) // One-liner for max-, min- height (and height)
@mixin fixed-width($width) // Applies the same value to max, min-width and width
@mixin fixed-height($height) // Applies the same value to max, min-height and height
@mixin fixed-size($width: auto, $height: width) // One-liner for fixed-width and fixed-height
```

### Breakpoints
```scss
@mixin MQPhones {} // Small devices (landscape phones, 576px and up)
@mixin MQTablets {} // Medium devices (tablets, 768px and up)
@mixin MQDesktop {} // Large devices (desktops, 992px and up)
@mixin MQLargeDesktop {} // Extra large devices (large desktops, 1200px and up)
```

