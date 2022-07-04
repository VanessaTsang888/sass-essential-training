# The @for at-rule

This at-rule or statement allows us to iterate through a list of numbers.

- Count up or down
This can either count up or down a series of numbers 

## How
and format looks like this:
@for <var> to | through <expression> {...}

1. write the @for
2. specify the variable
3. Use either the to or the through keyword
4. with an expression

We use 'to' if we want it to NOT to include the last number, e.g. one, two, three will give us one. two but NOT three.
We use the 'through' keyword when we want it to go all the way to the end of the numbers, so include the last number.
Then we use something that evaluates to one expression.
Then a series of commands inside a set of braces.

Example how we can generate all the font sizes for our Headlines using the @for at-rule.

### Example of how this would work

// Create a list with all of these sizes for the headlines specified as arguments.

$font-size: (3rem, 2.5rem, 2rem);

// Using the at-rule to iterate through a temporary variable which will go from one through 
// the entire length of that list which includes the first, second and third elements in the 
// $font-size list.
// Then execute the code within the body of this rule. In this case we are using interpolation 
// to return the values or data that is stored in the $font-size variable.
// Then set the font size by using the value from each of the fields - above arguments passed into the
// $font-size variable.
// So whenever we have a numeric numbers we want to use, the @for at-rule is useful. 
@for $i from 1 through length($font-size) {
  h#{$i} {
    font-size: nth($font-size, $i);
  }
}
