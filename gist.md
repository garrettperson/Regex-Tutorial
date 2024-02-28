# Regex Tutorial: Matching an Email

The following tutorial walks the user through using a regex (regular expression) that matches email addresses.

## Summary

A regular expression (regex) is "a sequence of characters that defines a search pattern, (The Coding Train, 2.1: Introduction to Regular Expressions, https://www.youtube.com/watch?v=7DG3kCDx53c)." They're mostly useful for defining a search pattern within a body of text. This tutorial will cover a regular expression used to search for email addresses within a body of text. This tutorial will cover the various components of the regex and what they mean. Here is the regex for matching email addresses:

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

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

### Anchors

The ^ and $ characters are anchors. Anchors signify the beginning or ending of a string. The ^ anchor signifies that what follows it will be a string to be searched for. The $ anchor signifies that what precedes it is a string to be searched for, the $ anchor goes at the end of a string to be searched for. These anchors can search for literal values, e.g. "The man," whereby "the man" is excluded from the search because regular expressions are case sensitive, or the anchors can be used to search for more general values using bracket expressions.

In the regex that is our example, the ^ anchor occurs at the very beginning of the expression and the $ anchor occurs at the very end of the expression.

/ `^` ([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6}) `$` /`


### Quantifiers

The + and {} characters are quantifiers. Quantifiers determine the limits of the string or section of the string that the regular expression matches. 

`+` matches the regex pattern one or more times;
`*` matches the regex pattern zero or more times;
`?` matches the regex pattern zero or one time;
`{ n }` matches the regex pattern `n` times;
`{ n, }` matches the regex pattern `n` or more times;
`{ n, x }` matches the pattern at least `n` times and not more than `x` times

In our example expression the numbers within the {} curly brackets determine the minimum and maximum number of characters being looked for; `{2,6}` means it matches between 2 and 6 characters. Specifically the {2,6} looks for the part of the email address that occurs after the `.` e.g. for sal@hotmail.com the {2,6} looks at the `.com` portion and checks to see that `com` is at least 2 but not more than 6 characters.


/^([a-z0-9_\.-] `+` )@([\da-z\.-] `+` )\.([a-z\.] `{2,6}` )$/

The `+` character checks the other parts of the email address to see that the specified pattern occurs at least one time.

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

Grouping constructs allow one to group together different parts of a regex so that it is easier to read and understand. The most common way for a section of a regular expression to be grouped is using parentheses to form subexpressions.

In our example regex we can see the different subexpressions:

/^ `([a-z0-9_\.-]+)` @ `([\da-z\.-]+)` \. `([a-z\.]{2,6})` $/

`([a-z0-9_\.-]+)` matches the username of the email, e.g. "sal" for "sal@hotmail.com";

`([\da-z\.-]+)` matches the first part of the domain name for the email, e.g. "hotmail" for "sal@hotmail.com";

`([a-z\.]{2,6})` matches the second part of the domain name and the final part of the email address, e.g. "com" for "sal@hotmail.com";


Grouping constructs can be either capturing or non-capturing. Capturing groups capture and remember parts of the matched string, allowing them to be referenced later or used in replacement operations. Non-capturing groups do not capture and remember parts of the matched string; they are used to group parts of the pattern together but do not contribute to the results of the match. Capturing groups are denoted by `()` while non-capturing groups are denoted by `(?:)`.

### Bracket Expressions

Bracket expressions, also known as positive character groups, are defined by various characters within a pair of square brackets []. These characters within the brackets represent a range of characters to be matched. For example [a-z] searches for all lowercase letters, while [A-Z] searches for all uppercase letters. [0-9] searches for all numbers while [_-] searches for underscores and hyphens.

/^( `[a-z0-9_\.-]` +)@( `[\da-z\.-]` +)\.( `[a-z\.]` {2,6})$/

[a-z0-9_\.-] matches all lowercase letters, numbers 0-9, "_", ".", and "-".

[\da-z\.-] matches numbers 0-9 (\d), all lowercase letters, "." and "-".

[a-z\.] matches all lowercase letters and "."


### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
