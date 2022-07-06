# Conditionals lecture
Conditionals is another set of operators. We use this with the if and else @rule to check if something is conditionally compared to something else. 

SUMMARY:

- ``` @if ``` ``` @else ``` at-rules

- ``` == ``` and ``` != ``` 
We can compare things with equal sign. 

- ``` >, <, <=, >= ```
Greater than, less than, less than and equals, greater than and equals comparison operators.

- AND, OR 
Can make more complex comparisons with the keywords AND, also OR

<!-- Assign a Boolean of false to the oval variable. Then check for that variable name. -->
$oval: false;
% If overal is true as in it exist then execute whatever is in the body and in our case is make the border radius 50%. Otherwise make it 5px.
@if $oval {
  border-radius: 50%;
} @else {
  border-radius: 5px;
}

