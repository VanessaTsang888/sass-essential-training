Code Files: http://raybo.org/slides_sassesst/?d=02_08&#/

Use what I've learnt so far to create a mixin that will help me generate a series of related message classes.

Follow these parameters:

1. Create a 'message mixin' that will help us generate a series of reated message classes.
2. Make sure mixin has a default value for a background color
3. Use 'nested styles' to make it easier to define our classes.
4. Add a 'hover state' so that when we roll over a message, it highlights in some way.
5. Use a 'parent selector' to help us build a variant of the main message class called info.

The Solution:
Two boxes. One on top of the other. First box (called Message) has white h1 and white paragraph text on gray background. 
Second box (called Info) the same but on green background. When user hover over the Message box. the bg will turn
dark gray. When user hover over the Info box, the bg will turn dark green. Should be easy to create multiple versions of
these, e.g. a danager class. 