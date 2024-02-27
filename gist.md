# Regex Tutorial: Matching an Email

The following tutorial walks the user through using a regex (regular expression) that matches email addresses.

## Summary

A regular expression (regex) is "a sequence of characters that defines a search pattern, (The Coding Train, 2.1: Introduction to Regular Expressions, https://www.youtube.com/watch?v=7DG3kCDx53c)." They're mostly useful for defining a search pattern within a body of text. This tutorial will cover a regular expression used to search for email addresses within a body of text. This tutorial will cover the various components of the regex and what they mean. Here is the regex for matching email addresses:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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

### Quantifiers

### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
