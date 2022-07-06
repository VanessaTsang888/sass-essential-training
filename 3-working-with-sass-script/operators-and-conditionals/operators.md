# Operators
Intro:
Programming languages has a series of operators and math functions to help us take care of places where we need to do calculations. In addition SASS has some special operators that can help us compare and make decisions within our code.

## Resources
[Operators](https://sass-lang.com/documentation/operators)

[math](https://sass-lang.com/documentation/modules/math)

[Conditionals: if-else at-rules](https://sass-lang.com/documentation/at-rules/control/if#else)

### What is it?
SASS has traditional operators we would from 'math', such as the addition, subtraction, division, equals and modules operators:

``` +, -, /, =, % ```

However, the division oporator is strange in SASS. Sometimes it refers to a list, and sometimes it refers to a division and it does good job of figuring out when we want to do either. However this operator will be replaced by ``` math.div() ``` example ``` math.div(2,4) ``` 

There is also away to add a slash will be treated as a slash by using this ``` list.slash() ```  method.

- smart calculations
Smart at doing calculations. Here are samples of calculations that is will perform for use:
    
``` #{4px * 6} - 24px ```

<!-- This will be treated as two elements and a list. This looks like a division but its actually a list. -->
``` #{1em/2em} - 1em/2em ```

``` #{1px + 4px} - 5px ```

90% SASS can figure out our calculations but sometimes we need to force them. 
[math](https://sass-lang.com/documentation/modules/math)

Just like other programming language there are tones of math functions, example to round up an number we use the
 ``` math.ceil() ``` method -> ``` math.ceil(4.2) ``` // 5
To round down a number us the ``` math.floor() ``` method. There is a math function that will create random numbers.



### Why we use this?
Operators and math functions to help us take care of places where we need to do calculations. In addition SASS has some special operators that can help us compare and make decisions within our code.

### How It Works?
We write our numbers inside of the parenthesis like this:
 ``` math.ceil(4.2) ``` // this math function will return the number 5