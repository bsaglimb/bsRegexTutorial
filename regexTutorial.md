# Regex Tutorial: Matching a HTML tag

As a fullstack software engineer student, I have developed a tutorial explaining a specifics of regex so that we can understand the search pattern the regex defines.

## Summary

A regex or regular expression are patterns used to match character combinations in strings. In JavaScript, regular expressions are also objects. These expressions are extremely useful for extracting data like phone numbers, emails, etc that follow a specific pattern from text, and they can be used in almost any programming language including JavaScript. It is a technique commonly developed in theoretical computer science.

We will look at a string of code using regex, this code looks for a match HTML tag.

Example: /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/


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


- `^abc$` -^start / $end of the string
    * `^` Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled. This matches a position, not a character.
    * `$` Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.
- `\b\B` -word, not-word boundary
    * `\b` Matches a word boundary position between a word character and non-word character or position or the start / end of string. (See the word character class (w) for more info.)
    * `\B` Matches any position that is not a word boundary. This matches a position, not a character. (See Boundaries for more detailed Information)


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