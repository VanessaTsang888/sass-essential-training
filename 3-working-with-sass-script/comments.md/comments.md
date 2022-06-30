COMMENTS

We add comments to our code to let others (developers) know what is going on with our code.
SASS comments have some interesting features. Here are some samples of what we can do with SASS comment.

1. Can use any css comments: 

 /* Regular CSS -- Published */

 /* Multi Line
        Comments -- Published */

2. Comments that will not output to css regardless of what mode we have set things to, and that is Javascript
style comments, that begin with two slashes:

    // Javascript Style -- Unpublished. 

This is good if we want to write comments with our code that nobody will ever see when they're converted into the final CSS. 

3. Can write comments that will always publish, regardless what your settings are. We do that by adding a exclamation mark 
right after the beginning star:

    /*! Forced publish this comment */


4. There is a way we can use interpolation in our comments. We can output the value of this color variable in a comment by
adding the hash symbol and inside a set of braces write a dollor sign and our variable name - any kind of expression and it
be added to your comments. 


-- Summary --
- Can use CSS Comments;
- JavaScript Unpublished;
- Force Publish Compressed;
- Interpolation OK.
