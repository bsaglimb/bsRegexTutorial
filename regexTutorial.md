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
    * `\b` Matches a word boundary position between a word character and non-word character or position or the start / end of string. (See the word character class (w) for more info)
    * `\B` Matches any position that is not a word boundary. This matches a position, not a character. (See Boundaries for more detailed Information)


### Quantifiers

Quantifiers indicate that the preceding token must be matched a certain number of times. A quantifire can be greedy or lazy that is explained below.

- `a*a+a?` -0 or more, 1 or more, 0 or 1
    * ``"+"` Matches 1 or more of the preceding token.
    * ``"*"` Matches 0 or more of the preceding token.
    * ``"?"` Matches 0 or 1 of the preceding token, effectively making it optional.
    * ``"?"` Makes the preceding quantifier lazy, causing it to match as few characters as possible. By default, quantifiers are greedy, and will match as many characters as possible.

- `a{5}a{2,}` -Looks for exactly five, two or more

- `{2,6}` -forces the input of characters between two & six characters long.

- `a+?a{2,}?` -match as few as possible

- `ab|cd` -match ab or cd

### OR Operator

- `|` Acts like a boolean OR and matches the expression before or after the |. It can operate within a group, or on a whole expression. The patterns will be tested in order. Just as in javascript, it will match either set of characters. It will look for this OR that. The OR operator indicates that it could either of the components that we are separating.

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

My name is Brianna Saglimbeni, and I'm a full stack web developer in training with the University of Miami. My github is [bsaglimb](https://github.com/bsaglimb). Please also feel free to email me at bsaglimb@gmail.com. 