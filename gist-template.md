# A Simple Guide to Learning RegEx

In this tutorial, I will be explaining how to use RegEx or Regular Expressions in JavaScript.

## Summary

The Regular Expression that I will be matching in this tutorial is a hex value, also known as a color.  I will be matching the hex value of four colors.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/

By using this espression I will ask the program to find the following components of a hex value:
- Make sure the value starts with the # symbol
- Find a value where the letters a through f exist and any digits between 0 and 9
- Either the value can have 6 characters or 3

Example:
let myColors = "My favorite colors are: teal, blue, purple, and pink. The shades of each color I like are: #045d5d, #00008b, #7851a9, and #8b008b.";
let myRegex = /^#?([a-f0-9]{6}|[a-f0-9]{3})$/;
let result = myRegex.test(myColors);
console.log(result)

This should find only these values ["#045d5d", "#00008b", "#7851a9", "#8b008b"] from the whole string of "My favorite colors are: teal, blue, purple, and pink. The shades of each color I like are: #045d5d, #00008b, #7851a9, and #8b008b."

### Anchors

^any means that the string satrts with any
$any means that the string ends with any

### Quantifiers

any* means that an is followed by zero or more y
any+ means that an is followed by one or more y
any? means that an is followed by zero or one y
any{3} means that an is followed by 3 y
any{3,} means that an is followed by 3 or more y
any{3,7} means that an is followed by 3 to 7 y
a(ny) means that a is followed by zero or more ny
a(ny){3,7} means that a is followed by 3 to 7 ny

### OR Operator

a(n|y) means that a is followed by n or y and captures them
a[ny] means that a is followed by n or y but does not capture them

### Character Classes

\d represents a single digit character
\w represents a word
\s represents a whitespace character
. represents any character

### Flags

i means case insensitive therefore it does not matter if a letter is uppercase or lowercase
g means global and captures all matches
m means multi-line which allows to match one line instead of the whole string

### Grouping and Capturing

a(ny) means to capture a group with ny
a(?:ny)* where ?: allows ny to not be captured
a(?<foo>ny) where ?<foo> names the group

### Bracket Expressions

[any] means we are looking for an a or an or ny or n or y
[a-z] is the same as the above
[a-fA-F0-9] will find a case insensitive hex value
[0-9]% will find a percentage with a single digit only
[^a-zA-Z] will not find any letter a to z or A to Z

### Greedy and Lazy Match

let string = "anteater"
let regex = /a[a-z]*t/
A greedy match would result in "anteat".
A lazy match would result in "ant". 

### Boundaries

\b will search for only whole words
\B will see if a pattern is surrounded fully by words

### Back-references

([any])\1 would match the same exact text that matched the first group that was captured 
([any])([de])\5\4\3\2\1 would allow us to identify the same exact text that matched the first, second, third, fourth, or fifth group that was captured 
(?<foo>[any])\k<foo> allows us to reference the group

### Look-ahead and Look-behind

g(?=k) will match a g only if it follows a k even though k will be excluded from the overall match
(?<=k)g will match a g only if it comes before a k even though k will be excluded from the overall match

## Author

This tutorial was created by Ruchi Vaishnav, a Front End Web Developer in training.
GitHub: https://github.com/ruchivaishnav27
