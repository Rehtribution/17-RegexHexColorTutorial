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
- Hexadecimal colors can contain the letters ```a-f```
- The digits ```0-9```
- And will be 6 characters long 
</br>
</br>
**Referencing the table above,**
</br>
- The letters are case sensitive so include ```A-F```
- The string is preceded by a ```#```
</br>
</br>
**Something we did not cover in the example,**
</br>
- They CAN be as short as 3 characters long
- The ```#``` generally signifies a color value but is not always present

With these factors in mind, our expression for this tutorial  will look like this:
</br>
```/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/```
## What do the ```/^?([])$``` mean and what's with the format?
Well that leads us to the meat and potatoes of this guide beginning with Anchors.
</br>
</br>
</br>
</br>

## Table of Contents

- [Anchors](#anchors)
- [Grouping and Capturing](#grouping-and-capturing)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Bracket Expressions](#bracket-expressions)
- [Conclusion](#conclusion)

## Regex Components

### Anchors
In regex, anchors are a way to match a position within a string. 
</br>
There are four main anchors, 
</br>
```/``` holds our expression together. Adding certain letters behind the last ```/``` can more closely specify what our regex is looking for, however we won’t be going in depth on that in this section.
</br>
```^```  Marks the beginning of our string.
</br>
```$``` Marks the end of the string.
</br>
We can break our expression out of these parameters for a visual example:
</br>
```
/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/
```

```
#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})
```
### Quantifiers
So what does the ```?``` do after the color signifier?
</br>

```?{}|``` Are Quantifiers, they follow to the right of the token they are referencing.
</br> 

</br>

```?``` Makes it's precedant an optional match, meaning that it will find matches with or without it included.
</br> 
```{}``` Designates a range of matches,
</br> 

```{3}``` Excactly 3 characters long
</br> 

```{3,}``` At least 3 characters long 
</br> 

```{3, 6}``` At least 3 characters but not longer than 6
</br> 

In our expression we can see that ```#``` is optional as the colors can be listed with or without, and we see the range of ```6``` and ```3```

```#?``` ([A-Fa-f0-9]```{6}``` | [A-Fa-f0-9]```{3}```)

```|``` Acts as a boolean OR. In our example we are looking for matches that are ```6``` OR ```3``` characters long.
</br> 

([A-Fa-f0-9]{6} ```|``` [A-Fa-f0-9]{3})
</br> 
</br> 

Removing what we've covered so far we are left with quite a small expression indeed.
</br> 

```
([A-Fa-f0-9])
```
</br> 

```([])``` Leads us into the next section.
</br> 
</br> 
</br> 

### Grouping and Capturing
```()``` Are a way to capture groups of characters or character sets, similar to the way a math formula would.
</br>
We are telling regex to look for any parameters that we set within the ```()```
</br>
</br>
The expression is almost gone!
</br>

```[A-Fa-f0-9]```

### Bracket Expressions

```[]``` Works similarly to the ```()``` described in the previous section. This simply designates a range of a character set for our regex to follow.
</br>
Look for any character that matches the range dictated within.
</br>
Now we are left with the last aspect of the expression!

```A-Fa-f0-9```
</br>

### Character Classes
Character classes are the types of characters we are searching for or characters we want omitted from the search.
</br>
In this case we are looking for three character ranges,
</br>
```A-F a-f 0-9```
</br>
As mentioned previously, our search is case sensitive so we want to include capitol and lowercase senarios. And of course we wish to capture any numbers so we include the ```0-9```.
</br>
And now the exciting conclusion!

### Conclusion
We started with 
```/^#?([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$/```
and broke it down into it's parts so we can understand how this expression works. Reviewing it now, can you see how we will find all the hexadecimal color values?
</br>
Valid returns for this expression would look like
</br>
```
#abc123
#000000
F00
```
and many other combinations.
</br>
I hope you enjoyed this tutorial and find yourself with a better understanding of how to use Regular Expressions to find Hexadecimal Color Value matches.
</br>
</br>


## Author
**Reht Cavazos**
</br>
Fullstack Developer
</br>
Checkout my work on GitHub!

[![GitHub Portfolio -> - Rehtribution](https://img.shields.io/badge/GitHub_Portfolio_-->-Rehtribution-darkred?style=for-the-badge)](https://github.com/Rehtribution)




[^1]: https://www.electronics-tutorials.ws/binary/bin_3.html
[^2]: https://marketing.istockphoto.com/blog/hex-colors-guide/#:~:text=Hex%20color%20codes%20are%20values,expressed%20is%20the%20color%20black.