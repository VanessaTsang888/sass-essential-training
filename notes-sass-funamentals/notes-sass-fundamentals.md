SASS Syntax:

The SASS Format is the indented format and has No punctuations. whitespace are meaningful so you end up indenting with tabs or spaces whenever you would type in braces, and don't need semi-colon we normally use. 

The SCSS Format: .scss -> also known as the Sassy format. CSS compatible: If we have existing CSS code, we can just copy & past in to our code base and that past will be 100% compactable. With regular SASS we would have to delete all the punctuation and indent everything accordingly. This is the most common/popular format. 

The DS don't use the SASS format but the SCSS format.

Using Variables:

VAriables allow us to create placeholders for values and then use them to apply them in different places. 

How variables work:
Summary:
    Top Level -> Global
    Braces -> Local
    Shadowing.

1. Begin with a dollar sign and then a variable name: $NAME
2. The format is similar to a CSS declaration: <variable> : <expression> this means we can use formulars and more complex statements rather than just a simple assignment. The main difference between sass and a regular css variable is that the sass variable will always be converted to css which is what the browser can use.
3. Scope: variables normally have a gloal scope so we can define them once at the top of our styles and they'll be available everywhere. Can also create variables inside braces and they become local variables instead. Local variables can have the same name as global variables and this is known as 'shadowing' - I need to understand this behaviour and how it works.

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

Global Flag:
1. Redefine globals.
2. Not for new vars.

We can redfine a global variable by using a the global flag at end of a definition:
Here we are redefining the value of the primary color. Can only redfine on existing variables. Below, the global flag has redefined the p text as yellow so everything gets the yellow color.

    h1 {
        $primary-color: yellow; !global;
        color: $primary-color;
    }

    p {
        color: $primary-color;
    }

Underscores Vs Hyphens:
Both are the same. The h1 will be yellow as we are redefining the variable to be yellow.

     $primary-color: red;
     $primary-color: yellow;

    h1 {
        color: $primary-color;
    }

Nesting:

SASS allows us to place rules inside of other rules. This is known as nesting.