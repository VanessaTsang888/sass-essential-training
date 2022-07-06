# Rich Color Functions lecture

Ways to modify colours in SASS. 

## Resources

[SASS official docs - Rich color functions](https://sass-lang.com/documentation/modules/color)

### What?
This is a feature or concept in SASS for us to modify colors.

### How?

To use the rich color function feature we need to add the color modules. 

- ``` @use "sass:color" ```

- The color rules include:

``` color.adjust()  darken()  lighten()  transparentize() ```

Then we can add any (multiple) colour rules, above are some examples. they are all on the official docs. 
Example, we can change the transparency values. See below:
Creating the color variable and then we can call any one of these other methods. 

```
@use "sass:color";
$color: cyan;
 #{ color.adjust($color, $lightness: -20, $alpha: .4)} 
 #{transparentize($color, .9)} 
 #{lighten($color, 30%)} 
 #{darken($color, 20%)} 

```

[SASS official docs - Rich color functions](https://sass-lang.com/documentation/modules/color)

We feed in the original color then we can modify the red, green and blue channels. As well as the hue, whiteness and alpha channels.

```
color.adjust($color,
  $red: null, $green: null, $blue: null,
  $hue: null, $saturation: null, $lightness: null,
  $whiteness: null, $blackness: null,
  $alpha: null)
adjust-color(...) //=> color 

```

Not only we can modify how color works but we can get info on colors by using for example:
``` color.alpha($color) ``` // return the alpha channel of $color as a number between 0 and 1.
``` color($color) ```
``` opacity($color) ``` //=> number



