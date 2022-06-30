Interpolation:

Is an insertion and allows us to interpolate sass expressions into a simple sass or css code meaning we can define selector name, property name, css at-rules, quoted or unquoted strings etc as a variable.

Interpolation can be used almost anywhere in a Sass stylesheet to embed the result of a SassScript expression into a chunk of CSS. Just wrap an expression in #{} in any of the following places:

Selectors in style rules
Property names in declarations
Custom property values
CSS at-rules
@extends
Plain CSS @imports
Quoted or unquoted strings
Special functions
Plain CSS function names
Loud comments

So to interpolate an expression we need to wrap the expression using #{}
Syntax: .....#{$variable_name}.....

Example:

@mixin corner-icon($name, $top-or-bottom, $left-or-right) {
  .icon-#{$name} {
    background-image: url("/icons/#{$name}.svg");
    position: absolute;
    #{$top-or-bottom}: 0;
    #{$left-or-right}: 0;
  }
}

@include corner-icon("mail", top, left);

So interpolation lets us work with variables that are defined by expressions: 
#{expression}
#{$variable + '--btn'}

Can use to these to perform calculations, e.g. loops etc

Can be used in number of different place e.g. use them with mixins, comments, function names, extends at-rules etc.
Using interpolation to determin the name of the button that has a class of btn. This will allow me to call this with the @include btn command  and create a button with the styles in the body:

@mixin btn($name: "", $bg: #444, $col: white) {
    // creating a button name:
    .btn #{$name} {
    background: $bg;
    color: $col;
    }
}
// call the interpolation above and create a button with whatever properties are in the body.
@include btn;
@include btn("-primary", #3ab5e9)

Good to use Interpolation when writing advance sass.
Interpolation feature is useful in SASS, we will use more and more in advance SASS.
