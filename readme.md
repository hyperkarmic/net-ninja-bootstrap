bootstrap course
##lecture 2
this is getting silly!!!! a test

#more colors - no jumbotron

#necessary education manouveres change everything!!!!

from lecture 19s - youtube - to correct it!!!!!
//
FOR EVERYONE HAVING PROBLEMS WITH THE CUSTOM COLORS NOT CHANGING

Someone already said this but you can add the following under your map-merge function (for example):

```
$theme-colors: map-merge($theme-colors, $custom-theme-colors); // You should already have this, so no need to copy this part.

// Start copying at the line below
$theme-colors-rgb: map-loop($theme-colors, to-rgb, "$value");
$utilities-colors: map-merge(
  $theme-colors-rgb,
  (
    "black": to-rgb($black),
    "white": to-rgb($white),
    "body":  to-rgb($body-color)
  )
);

$utilities-text-colors: map-loop($utilities-colors, rgba-css-var, "$key", "text");
$utilities-bg-colors: map-loop($utilities-colors, rgba-css-var, "$key", "bg");
// Stop copying at the line above

@import "../node_modules/bootstrap/scss/bootstrap"; // You should already have this as well, so no need to copy this part.
//
```
