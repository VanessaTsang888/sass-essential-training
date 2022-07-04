# The @each at rule  is also known as the each statement and a directive - interchangeable

## Summary

- Emit styles
Allows us to emit a number of styles based on a list or a map.

- @each <var> in <expression> {...}
We use an at rule with a variable to use for each statement which is normally a list or something that computes to a list, e.g. some of the methods in previous video.

- Destructuring
We can use destructuring (unpack) so we can create a series of variables a complex list. Example based on what we've been doing with buttons:

// Create a mixin to go through a button create it based on a name variable, a background variable with a value of a specific colour, a color variable with a value of white.

@mixin btn($name: "", $bg: #444, $col: white) {
  .btn#{$name} {
    background: $bg;
    color: $col;
    // ...
  }
}

// Create a list inside of a list: inside of the buttons list we have the primary list with two elements which are two different colors. Then the same with the secondary list.

$buttons:
  -primary #3ab5e9 hotpink,
  -secondary green yellow;

// Call with the @each at-rule and destructure the data that we are inputting from the each one of the lists (primary, secondary lists). So we taking each value from a list and storing it in each of the varialbes or data we need to destructure.

When we do that, then we create one of those variables as we loop through each of the elements in our button lists (primary, secondary lists).

Then we use or include the mixin btn and pass in the value for each one of those, e.g. an empty String, the background color and the text color of white.

@each $name, $bg, $col in $buttons {
  @include btn($name, $bg, $col);
}

## Why use the @each at-rule in this way?
This is a much simpler way to create a series of elements by feeding items from a list, destructuring it, and passing it along into an include statement.