# Matching Hexadecimal Color Value with Regex Tutorial

This tutorial will introduce you to Regular Expressions, simplified as Regex, and how they work to match, locate, and validate text.
First, what is Regex? </br>
Regex is a string of text, numbers, and symbols that can be broken down into patters that can then be combined with funcitons to parse through and locate strings that match them.


# Summary

There are many ways to utilize Regex but we will focus on the Hexidecimal Color Value here.
## What are Hexadecimal Numbers?
A simple explanation can be found in electronics-tutorials.ws. [^1] </br>
“The “Hexadecimal” or simply “Hex” numbering system uses the Base of 16 system and are a popular choice for representing long binary values because their format is quite compact and much easier to understand compared to the long binary strings of 1’s and 0’s.

Being a Base-16 system, the hexadecimal numbering system therefore uses 16 (sixteen) different digits with a combination of numbers from 0 through to 15. In other words, there are 16 possible digit symbols…hexadecimal numbers that identify the values of ten, eleven, . . . , fifteen are replaced with capital letters of A, B, C, D, E and F respectively.”

## So how does this factor into colors?
A clear description can be found on istockphoto.com. [^2] </br>
“Hex color codes are values that tell the display how much of a color to show. The values are a special code that represents color values from 0 to 255.

If red, green, and blue are all at the minimum 0 (represented as “00” in the code), the color expressed is the color black. If red, green, and blue are all at the maximum 255 (represented as “ff” in the code), the color expressed is the color white.”

See the table below for an example.

| Color | RGB | Hex Code |
| ----------- | ----------- | ----------- |
| Black | (0, 0, 0) | #000000 |
| Red | (255, 0, 0) | #FF0000 |
| Green | (0, 128, 0) | #0008000 |
| Blue | (0, 0, 255) | #0000FF |
| White | (255, 255, 255) | #FFFFFF |


</br>
</br>

## How can we use this information?
Well with what we know now,
</br>
- Hexadecimal colors can contain the letters a-f
- The digits 0-9
- And will be 6 characters long 
</br>
</br>
**Referencing the table above,**
</br>
- The letters are case sensitive so include A-F
- The string is preceded by a #
</br>
</br>
**Something we did not cover in the example,**
</br>
- They CAN be as short as 3 characters long

With these factors in mind, our expression for this tutorial  will look like this:
```
/^#([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/

```
## What do the ```/^([])$``` mean and what's with the format?
Well that leads us to the meat and potatoes of this guide beginning with Anchors.
</br>
</br>
</br>
</br>

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)

## Regex Components

### Anchors

### Quantifiers

### OR Operator

### Character Classes

### Grouping and Capturing

### Bracket Expressions


## Author
Fullstack Developer

[![GitHub Portfolio -> - Rehtribution](https://img.shields.io/badge/GitHub_Portfolio_-->-Rehtribution-darkred?style=for-the-badge)](https://github.com/Rehtribution)




[^1]: https://www.electronics-tutorials.ws/binary/bin_3.html
[^2]: https://marketing.istockphoto.com/blog/hex-colors-guide/#:~:text=Hex%20color%20codes%20are%20values,expressed%20is%20the%20color%20black.