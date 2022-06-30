SASS Syntax:
The SASS Format:
Summary:
1. .scss (indented everything accordingly)
2. No punctuation, e.g. don't need the ending semicolons that we would normally use.
3. Meaningful whitespace
Example: no braces, use indentations instead.
// The Code:
$bg: #ead2a8

body
    background: $bg

The SASS Format - Summary:
1. .scss (Sassy).
2. CSS compatible.
3. Most popular.
Example: can past normal css code and use them within Sassy code. The variable names start with a dollar sign:
// The Code:
$bg: #ead2a8;

body {
    background: $bg;
}

The SASS Format is the indented format and has No punctuations. whitespace are meaningful so you end up indenting with tabs or spaces whenever you would type in braces, and don't need semi-colon we normally use. 

The SCSS Format: .scss -> also known as the Sassy format. CSS compatible: If we have existing CSS code, we can just copy & past in to our code base and that past will be 100% compactable. With regular SASS we would have to delete all the punctuation and indent everything accordingly. This is the most common/popular format. 

The DS don't use the SASS format but the SCSS format.

Using Variables:

Variables allow us to create placeholders for values and then use them to apply them in different places. 
How variables work. 
Summary:
1. Start with a dollar sign: $NAME
2. They have a format similar to a CSS property declaration meaning we can use formulars and more complex statements: <variable> : <expression>
3. A SASS variable will always be converted into CSS that is shorter than with regular CSS: Complile to CSS.

Example:
$bg: #ead2a8;

body {
    background: $bg;
}

    Scope: 
Example Code:
    $primary-color: red;

    h1 {
        $primary-color: yellow;
        color: $primary-color;
    }

    p {
        color: $primary-color;
    }

The heading 1 will be yellow and the paragraph text will be red.

Summary:
1. Top Level (Global)
2. Braces (Local)
3. Shadowing.

Variables normally have a gloal scope so we can define them once at the top of our styles (e.g. $primary-color) and they'll be available everywhere.
Can also create variables inside braces and they become local variables (e.g. inside of h1).
Local variables can have the same name as global variables and this is known as 'shadowing' - I need to understand this behaviour and how it works.

 

Global Flag:
Example Code:

$primary-color: red;

h1 {
    $primary-color: yellow !global;
    color: $primary-color;
}

Above:
We are redefining the value of the primary color -> to red which is the value of the global variable. This is know as redefines globals.

1. We can redfine a global variable by using the global flag at end of a definition: !global

2. Not for new vars. Can only redfine on existing variables. 

Underscores Vs Hyphens:
In variable names: underscores are the same as hyphens. 
The h1 will be yellow as we are redefining the variable to be yellow eventhough the style in the body of the h1
is hyphenated rather than using a underscore because the latest declaration is the variable that has the yellow
stored inside it.

     $primary-color: red;
     $primary_color: yellow;

    h1 {
        color: $primary-color;
    }

Nesting:

SASS allows us to place rules inside of other rules. This is known as nesting. Makes organising complex rules a lot easier. One of the best features in SASS.

Example Code:
.box {
    padding: 1em 2em;
    h1 {
        color: red;
    }
}

Nesting combines rules and helps us organise things better.
Becareful as a lot of nesting will create a lot of extra css which can get complex. Try to keep rules simple.
Since SASS is compiled, this means the css will take longer to generate - Bandwidth.
so try to keep our rules as simple as possible.

Summary:
1. combines rules.
2. Extra CSS.
3. Bandwidth.


Partilas:
Another key feature in sass is the ability to create separate files with snippets of code that can easily imported into other files.
These are known as Partilas. We create partials to help us organise things a lot better than we can in CSS.
We can create different files with different pieces of your code. So we can have a file _variables.scss and this can contain our basic 
variables:
// _variables.scss
    $bg: #ead2a8;
    $primary: SlateBlue;

This is a common pattern as well.
We can have another file with all of the basic code that we set up our page with, e.g. a body selector with background variables.
// _base.scss
    @use "variables";
    body { background: varialbes.$bg; ... }

Finally, we can create references to those other partials by making use of the @use parameter and then typein the name of the file 
that want to import. We don't have to put the underscore before the name and the file extension. The underscore in file name is so 
the parser knows its a file name and not to convert to other css file as the style.scss file will auto be converted into a styles.css
file when SASS outputs the final files, but the above two will NOT be generated as separate .css files:
// style.scss
    @use "variables" as var;
    @use "base";
    h1 { color: var.$primary; }

Summary:
1. start with an underscore _
2. @use copies code - create a reference to other partials e.g. _variables.scss with this property.
3. Namespaced variable, e.g. variables.$bg
4. Use as shortcut, e.g.  @use "variables" as var;
Snippects of code that can be easily imported into other files. We can create different files with different pieces of our code:

Parent Selector:
https://codepen.io/planetoftheweb/pen/JjrqpBV?editors=1100

The parent selctor lets us easily work with nested styles to choose the parent of a current class.
    How It Works:
        1. to specify we are asking for the parent, we use the ampersand & symbol. Examploe, inside of the btn class, we targeting the hover state of that button class to make the button have a different background color 
whenever the user roll over it. This creates a style that targets the parent and then adds whatever isto the right of this. It will copy the code from the parent and insert it in this new style. This means I can also use it to create a suffix by using the Ampersand &:
    &-primary

I can even specify that i want to create another class that has a prefix before it: .container & 
So in this case I would be looking for a button class that is inside a container class and align things to the right.

    SUMMARY:
    -> Ampersand &
    -> Copies parent
    -> Use as a suffix: &-primary
    -> Target parent present: .container &

Mixins: 
https://sass-lang.com/documentation/at-rules/mixin

They allow us to define styles thaat can be re-used through our stylesheets. They make it easy to avoid using non-semantic classes like .float-left, and to distribute collections of styles in libraries.

They are defined using the @mixin at-rule, which is written @mixin <name> {...}

They are similar to Javascript functions but does not return anything and can not be assigned to variables. 

Start by adding a @mixin.

A mixin's name can be any sass identifier and it can contain any statement other than top-level statements. they can be used to encapsulate styles that can be dropped into a single style rule; they can contain style rules of their own that can be nested in other rules or included at the top level of the stylesheet; or they6 can just serve to modify variables.

They are included into the current context using the @include at-rule, which is written @include <name> @include <name> (<arguments...>), with the name of the mixin being included.

Summary:
1. Create with @mixin
2. Pass arguments (can pass multiple arguments as we need, using commas)
3. Set defaults (arguments -> can pass default value)
4. Use @include rule (to use a mixin and the name of the mixin).

Fun fact:
Mixin names, like all Sass identifiers, treat hyphens and underscores as identical. This means that reset-list and reset_list both refer to the same mixin. This is a historical holdover from the very early days of Sass, when it only allowed underscores in identifier names. Once Sass added support for hyphens to match CSS’s syntax, the two were made equivalent to make migration easier.

@extend
Official docs: https://sass-lang.com/documentation/at-rules/extend

There are often cases when designing a page when one class should have all the styles of another class, as well as its own specific styles. For example, the BEM methodology encourages modifier classes that go on the same elements as block or element classes. But this can create cluttered HTML, it's prone to errors from forgetting to include both classes, and it can bring non-semantic style concerns into your markup.

<!-- HTML:
<div class="error error--serious">
  Oh no! You've been hacked!
</div>

 -->

<!--  CSS:
.error {
  border: 1px #f00;
  background-color: #fdd;
}

.error--serious {
  border-width: 3px;
}

-->

Sass’s @extend rule solves this. It’s written @extend <selector>, and it tells Sass that one selector should inherit the styles of another.

<!-- SCSS:

.error {
  border: 1px #f00;
  background-color: #fdd;

  &--serious {
    @extend .error;
    border-width: 3px;
  }
}

 -->


