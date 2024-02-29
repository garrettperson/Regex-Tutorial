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

In our example expression the numbers within the {} curly brackets determine the minimum and maximum number of characters being looked for; `{2,6}` means it matches between 2 and 6 characters. Specifically the {2,6} looks for the part of the email address that occurs after the `.` e.g. for gagmac@gmail.com the {2,6} looks at the `.com` portion and checks to see that `com` is at least 2 but not more than 6 characters.


/^([a-z0-9_\.-] `+` )@([\da-z\.-] `+` )\.([a-z\.] `{2,6}` )$/

The `+` character checks the other parts of the email address to see that the specified pattern occurs at least one time.

### OR Operator

The `|` character is the OR operator. It allows one to select between 2 or more possibilities. For example, if a given expression is `(aid)` we could change it to `(a|i|d)` and the same results would be returned.

### Character Classes

A character class matches a single character out of a set of characters. Character classes allow one to specify a range or list of characters to be matched at a particular position in a string. The bracket expressions discussed in another section are character classes.

[a-z] matches any lowercase letter
[A-Z] matches any uppercase letter
[0-9] matches any digit
[A-Za-z0-9] matches any letter or any digit
[A-Za-z0-9_-] matches any letter, any digit, a hyphen or an underscore
`.` matches any character except for the newline character
`\n` matches the newline character
`\d` matches any digit (equivalent to [0-9])
`\w` matches any alphanumeric character or an underscore (equivalent to [A-Za-z0-9_])
`\s` matches a whitespace character, including tabs and line-breaks
`\D` matches any non-digit character
`\W` matches any non-alphanumeric character and excludes underscores
`\S` matches any non-whitespace character

### Flags

Flags occur at the end of the second slash of a regex. They set limits or additional functions for the regex. The three most common flags are:

`g` for global search, wherein the regex is tested against all possible matches for the string;
`i` for case-insensitive search wherein the uppercase letters are treated the same as lowercase letters in attempting a match for the string;
`m` for multi-line search, wherein a multiple-line string is treated as multiple lines

### Grouping and Capturing

Grouping constructs allow one to group together different parts of a regex so that it is easier to read and understand. The most common way for a section of a regular expression to be grouped is using parentheses to form subexpressions.

In our example regex we can see the different subexpressions:

/^ `([a-z0-9_\.-]+)` @ `([\da-z\.-]+)` \. `([a-z\.]{2,6})` $/

`([a-z0-9_\.-]+)` matches the username of the email, e.g. "gagmac" for "gagmac@gmail.com";

`([\da-z\.-]+)` matches the first part of the domain name for the email, e.g. "gmail" for "gagmac@gmail.com";

`([a-z\.]{2,6})` matches the second part of the domain name and the final part of the email address, e.g. "com" for "gagmac@gmail.com";


Grouping constructs can be either capturing or non-capturing. Capturing groups capture and remember parts of the matched string, allowing them to be referenced later or used in replacement operations. Non-capturing groups do not capture and remember parts of the matched string; they are used to group parts of the pattern together but do not contribute to the results of the match. Capturing groups are denoted by `()` while non-capturing groups are denoted by `(?:)`.

### Bracket Expressions

Bracket expressions, also known as positive character groups, are defined by various characters within a pair of square brackets []. These characters within the brackets represent a range of characters to be matched. For example [a-z] searches for lowercase letters, while [A-Z] searches for uppercase letters. [0-9] searches for numbers while [_-] searches for underscores or hyphens.

/^( `[a-z0-9_\.-]` +)@( `[\da-z\.-]` +)\.( `[a-z\.]` {2,6})$/

[a-z0-9_\.-] matches lowercase letters, numbers 0-9, "_", ".", and "-".

[\da-z\.-] matches numbers 0-9 (\d), lowercase letters, "." and "-".

[a-z\.] matches lowercase letters and "."


### Greedy and Lazy Match

Greedy and lazy quantifiers are used to control the matching behavior when applying quantifiers to a problem. Greedy quantifiers match as much of the input string as possible while lazy quantifiers match as little of the input string as possible. Greedy quantifiers are standard, denoted by `*`, `+`, `?`, or `{}` without any special characters altering their function. Lazy quantifiers on the other hand are denoted with a `?` after the quantifiers: `*?`, `+?`, `??`, or `{}?`. For an example of how lazy and greedy quantifiers work let's examine the string "aggg". If using a greedy quantifier `a.*g` the match will be "aggg," whereas using a lazy quantifier `a.*?g` the match will be "ag." 

In the example of our regex, all the quantifiers are greedy.

/^([a-z0-9_\.-] `+` )@([\da-z\.-] `+` )\.([a-z\.] `{2,6}` )$/


## Author

The author of this tutorial is a student in UCLA Extension's Coding Bootcamp. His github profile can be found at https://github.com/garrettperson
