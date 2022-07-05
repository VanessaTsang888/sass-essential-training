# maps lecture

## Resources
[SASS Official docs -> maps](https://sass-lang.com/documentation/values/maps)

### What is maps?
Our lists can get confusing when we working with values that are inside of values, so SASS provides concept called: maps.
So maps is a concept/module that allows us to better work with values that are inside of a value 


From the official docs:
Maps in Sass hold pairs of keys and values, and make it easy to look up a value by its corresponding key. They’re written (<expression>: <expression>, <expression>: <expression>). The expression before the : is the key, and the expression after is the value associated with that key. The keys must be unique, but the values may be duplicated. Unlike lists, maps must be written with parentheses around them. A map with no pairs is written ().

Fun fact:
Astute readers may note that an empty map, (), is written the same as an empty list. That’s because it counts as both a map and a list. In fact, all maps count as lists! Every map counts as a list that contains a two-element list for each key/value pair. For example, (1: 2, 3: 4) counts as (1 2, 3 4).

Maps allow any Sass values to be used as their keys. The == operator is used to determine whether two keys are the same.

Heads up!
Most of the time, it’s a good idea to use quoted strings rather than unquoted strings for map keys. This is because some values, such as color names, may look like unquoted strings but actually be other types. To avoid confusing problems down the line, just use quotes!



### Map Basics
Maps hold key value pairs which are common in programming languages.

- 
```
(<key_exp>: <val_exp>, ...)
```
- Keys unique
- @use "sass:ap";
- Immutable

The keys need to be unqiue. 
Its a good idea to use quotes since sass can interpret unquoted Strings as different value types.
Maps are not auto included module so we may have to use the @use rule to include them in our project.
Just like lists, maps are immutable.

### Why we use maps?
Because maps allows us to better work with values that are inside of a value. 


### How we use maps
Example of a map module and a map method used on it:
1. Add the @use at-rule at the top to specify that your using the map module.
2. Define a map by using a variable name, e.g. $colorList:
3. Within a pair of parentheses we put the name and value pairs we want to add and we can add multiple 
of them. We can even add another value that is another map but this can get a little complicated.
4. We can use one of the methods to do something with our map, e.g. ``` map.get($colorList.primary) ```
Here we are saying: get the value primary of our color list map.
 
```
@use "sass:map";
$colorList: (
  "primary": RoyalBlue,
  // ...
  );

/* map.get($colorList.primary) */;
```
### Other
Map Methods:
- Dot or hypen
- ``` map-get(), map.set() ```
- Immutable
- Merge functions ``` map.merge() ``` ``` map.deep-merge() ```
- ``` map.remove() ``` ``` map.deep-remove() ```
- ``` map.keys() ``` ``` map.values ```
- ``` has.key() ```

There are many map methods and these we can use either a period or a hyphen. 
Apart from map.set() we can use either Dot or hympen after the map keyword.
``` map.set() ``` allows us to set the value of an existing  map.
There are couple of merge functions that allows us to merge maps together.
``` map.deep-merge() ``` is for when we have a map inside of map, hence the word 'merge'. 
We can remove a specific map and deep-remove is for when we using multi-level maps.
Map keys and map values gives us the list of all the keys in a map as well as the value.
We can find out whether or not a key exists with the has.key method

From official docs:
Since maps aren’t valid CSS values, they don’t do much of anything on their own. That’s why Sass provides a bunch of functions to create maps and access the values they contain.

Look Up a Value
Maps are all about associating keys and values, so naturally there’s a way to get the value associated with a key: the map.get($map, $key) function! This function returns the value in the map associated with the given key. It returns null if the map doesn’t contain the key.

```
$font-weights: ("regular": 400, "medium": 500, "bold": 700);

@debug map.get($font-weights, "medium"); // 500
@debug map.get($font-weights, "extra-bold"); // null
```

Do Something for Every Pair permalinkDo Something for Every Pair
This doesn’t actually use a function, but it’s still one of the most common ways to use maps. The @each rule evaluates a block of styles for each key/value pair in a map. The key and the value are assigned to variables so they can easily be accessed in the block.

```
$icons: ("eye": "\f112", "start": "\f12e", "stop": "\f12f");

@each $name, $glyph in $icons {
  .icon-#{$name}:before {
    display: inline-block;
    font-family: "Icon Font";
    content: $glyph;
  }
}
```


