# Matching Hex Values with Regex

Regular expressions (or regex for short) are useful for matching patterns within strings. The regular expression being used here is intended to match the hexidecimal (or hex for short) value within a string. Hexadecimals are simply a base 16 number system that allows values from 0 to F.

## Summary

This tutorial will go over the components of the regex being used here. The hex regex is useful in matching color codes within a string. The tutorial will cover the topics of Anchors, Quantifiers, Grouping Constructs, Bracket Expressions, Character Classes, The OR Operator, Flags, and Chaaracter Escapes. The Regex is below:

`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Author](#author)

## Regex Components

### Anchors

Anchors are special characters used in regular expressions to define the position of the pattern being searched. In this example, there are two anchors being used.

1. The first anchor is `^` or the caret symbol. This indicates the start of a string and is used to ensure that the regex matches at the beginning of the string. 

2. The second anchor is `$` or the dollar symbol. This indicates the end of a string and is used to ensure that the regex matches at the end of the string.

When these are used together, this will ensure that the regular expressions matches the entire string, from the beginning to end. 

### Quantifiers

Qantifiers are used to define the expected number of occurrences for the of the hexadmical digits. 

1. The `{6}` quantifier specifices the preceding character class, `[a-f0-9]`, should occur exactly six times. Since a hex color code consists of six hexademical digits, this quantifier ensures that the string value is a valid six digit color code.

2. The `{3}` quantifer specifices that the preceding character class which is again, `[a-f0-9]`, needs to match a three character sequence. This three character sequence represents the shortented RGB values in the hex color code.

### Grouping Constructs

Grouping constructs are used to group certain parts of the regular expression together. In this regular expression, the grouping consruct used is `()`. The parentheses define a group, allowing multiple elements to be treated as a single unit or group. Inside the parenthesis for this regeular expression, there is character class and quantifier that creates the first group and a second character class and quantifier that creates the second group separted by a pipe `|`. The first group is `[a-f0-9]{6}` and the second group would be `[a-f0-9]{3}`. This means that the hex regex will represent either a six digit or a three digit hex color code.

### Bracket Expressions

Bracket expressions are simply enclosed within brackets in the regex `[]`. In this hex regex, the bracket expression `[a-f0-9]` is being used. This represents a character class that matches any single character that is either a lower case letter from a to f, an uppercase letter from A to F, or a number from 0 to 9. These character classes will be further explained in the next section.

### Character Classes

Character classes are used to ensure that the hex regex matches only valid hexademical characters so the proper hex color code can be retrieved from a string. In this regular expression, the character class `[a-f0-9]` is used to match any lowercase or uppercase letter from A to F and a number from 0 to 9. 

### The OR Operator

The OR operator is represented by the pipe `|` symbol and is used to provide alternative matching options. In this regular expression, the OR operator separates the two valid patterns that can be matched: `[a-f0-9\{6}]` and `[[a-f0-9\{3}]` which is separated by the pipe `|` symbol in the full expression: `/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`

## Author

This was written by Zach Leone. Here is the link to my GitHub: https://github.com/wobbledy

