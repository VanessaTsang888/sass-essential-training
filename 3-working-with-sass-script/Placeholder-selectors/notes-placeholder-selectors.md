PLCCEHOLDER SELECTORS:

Sometimes we may want to create a class that is not something that we want to complie, but only something we want to extend. In this case we can use Placeholder Selectors. 

They look like any other class definitin, but they begin with a percentage sign instead. Then add the name of the class:   
     %btn
When you want to extend the class, you use the @extend at-rule and then the name of the placeholder:
    @extend %btn;
This allows us to create the button primary and the button secondary, but not have a btn class by itself.

Sass has a special kind of selector known as a “placeholder”. It looks and acts a lot like a class selector, but it starts with a % and it's not included in the CSS output. In fact, any complex selector (the ones between the commas) that even contains a placeholder selector isn't included in the CSS, nor is any style rule whose selectors all contain placeholders.

%btn {
  background: #444;
  color: white;
  // ...
}

.btn-primary {
  @extend %btn;
  background: #3ab5e9;
}
.btn-secondary {
  @extend %btn;
  background: orange;
}