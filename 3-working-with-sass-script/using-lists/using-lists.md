# Lists

These are know as arrays in Javascript.
We can use lists to create an Array type object that helps iterate through a group of items easily. 

1. Arrays are one of the more flexible data types in SASS. 
2. We create them by using either commas or spaces.
3. Can also use optional brackets or parentheses.
4. If we passing along an element that already has spaces then we need to add quotes to the item or sass will think that it's a new element.
5. Arrays are One Index. So the first element is number One which is different compared to other programming language e.g. JS.
6. We can even include negative indexes. This can be useful to get the last element in an array.
7. List values are immutable which means there content never change. When we change a list we actually create a new copy in order to aviod potential problems. 

-- SUMMARY --
1. Spaces, Commas
2. Brackets ``` [...] ``` or Parenthesis ``` (...) ```
3. use a set of Quote when spaces between elements
4. Indexed at 1 NOT 0 like other languages
5. Negative Indexes (-1)
6. Immutable (changes -> makes a copy)

## Methods to use with lists

- We can get the length of an array using the length method: length($myList)
- Can get the last element in an array using the nth method, we specify a list as well as the index of the list: nth($myList, 2)
- Change the value of an array element (actually end up with a new array) using the set-nth method. So we not changing anything but creating a new array with a new value in whichever position you specify -> set-nth($myList, 2, newValue)
- We can find out the index of a specific value, e.g. search for an item named Orange. Look for the index of Orange in the list named $myList: index($myList, 2, newValue)
- Can append something to the end of an array using the append method. When we append something we are actually creating a new list: append($myList, newValue, comma | space)
- Can join two lists together by specifying the two lists and we can specify a comma or space. This will actually create a new list: join($myList01, $myList02, comma | space)
- Can join two types of elements. One element will corrispond to theindex of another element: zip($myList1, $myList2)
- We can check to see if the list is currently bracketed. Sometimes the brackets are actually useful in css: is-bracketed($myList)
- We can check to see what the separator for the list is with this other method: list-separator($myList2)


