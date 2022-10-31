# My First Mod for Logic World
Tested and working for public preview version 0.91 preview 510

# So whats in here?
It is a mix of modified variants of existing in game components, and some more complex function components that do cool things like 
decoders, adder, multiplier, 7 segment display driver... read on for the full list

# Miniature Components!
These are half height versions of the most common components in Logic World. Half height means when you stack a board with these components, 
the height of the board plus the component fits within 1 square. You can create some extremely tight and compact builds with little to no gaps between layers.

The list so far:

* Inverter  
same as the normal inverter, just smaller. input pin is behind the output instead of above it

* SR Latch  
new component, this has a set and reset pin. The set pin is longer than the reset

* D Latch  
same as the in game D Latch. The clock pin is behind instead of on top, and it is shorter than the data pin

* AND gate  
2 pin version of the normal AND gate. Cannot be adjusted for 3/4 pin variants

* XOR gate  
same as the LW version, just smaller!

* Buffer/Fast buffers  
same as the LW versions, except they dont use the fancy angled meshes, just a shrunk down box

* Binary to BCD converters  
These are half height versions of the normal sized ones described later. Available in 4 in/4 out, 5 in/5 out and 5 in/6 out versions

# Complex Logic
These provide pretty useful functions that can also speed up your build quite a bit

* Decoders  
These are useful to take a binary value and select an output based on that value. These also include an enable input so you can build a much 
larger decoder (for example, part of a 64k address decoder for your massive ram projects!). These come in 2bit to 4 outputs, 3bit to 8 outputs and
4 bit to 16 output variants. Pay attention to the registration marks (the small gold squares) as these mark output 0 and where the LSB of your input
goes. The enable pin is on the opposite of the component

* Binary to BCD converters  
These help in converting binary data into a format called Binary Coded Decimal (BCD for short). These are very useful when making displays that show
you a number a human can understand. There are 3 variants: a 4bit in/4 bit out converter which can display numbers 0-19 (with an additional lsb input), 
a 5bit in/5bit out converter for 0-31 range, and a 5bit/6bit out converter for 0-63 ranges. These work simlarly to the 74185 chips that can decode binary
to bcd format. See [the datasheet, page 8](https://digsys.upc.edu/csd/chips/classic/DM74185.pdf) on how to use these to build 8, 12 and 16 bit to BCD
converters. the smaller variants were made to fit the cases where not all inputs or outputs are used, as is shown on the 16bit converter circuit in that datasheet. 
All 3 of these components come in half height versions as well, you can build very compact bin 2 bcd converters!

* Vedic 4x4 Multiplier  
A handy device for building larger multipliers. This performs a 4bit x 4bit multiplication, with an 8 bit result on the output. See 16 or 32 bit vedic 
multipliers on google on how to build larger width multipliers using this device. Has registration marks showing where the lsb of the inputs and output will
be.

* 8 bit Adder
As the name suggests, an 8 bit adder. Has a carry in input on one side, and a carry out on the other. The registration marks on the chip will tell you where 
the lsb of the inputs and outputs will be.

* 7 Segment Display Driver  
This device takes a 4 bit input (you can use those fancy bcd converters above, hint hint ;)) and turns on the proper segment outputs to light up your numeric 
displays. The outputs are arranged to go directly to the segments that need to be lit to represent the number it is displaying. The display handles digits 0-9 
and the letters a-f for hex displays. It also includes a 'ripple blank' input and output. These are handy when you dont want to display leading zeros on a larger
numeric display. Enable this pin on the highest digit of your dipsplay, then chain the output of the digit to the rb input of the next lowest digit, repeat for
all the digits in your display. You can leave the least significant digit unconnected so you still see the single 0 when there is no value to display. This also fits
perfectly behind a 3x5 pixel display, letting you create tight and compact displays with this component.


Note all the inputs of these components have been shortened slightly so input pins can share the same square as output pins of other components, giving you the freedom
to shrink those builds even more!

# Where's the mod for Logic World version 0.90?
The difference between the LogicScript implementations in LW 0.90 and 0.91 is so large that it would not be possible to go back to that version. 
Just upgrade to the public preview version plz ;)
