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

Character classes match a character from a specific set. There are a number of predefined character classes and you can also define your own sets. Character classes are components within our regular expression that tells us what type of characters to expect.

- `[ABC]` Characters inside brakets will match any character in the set.
- `[^ABC]`Adding caret will match any character that is not in the set.
- `[A-Z]` Adding a dash between two characters will select a range.
- `.` Will Match any characters expect linebreaks. Its like a wildcard and will accpet any input.
- `[\s\S]` A character set that can be used to match any character, including line breaks, without the dotall flag. (An alternative is [^] caret in brackets, but it is not supported in all browsers)
- `\w` Matches any word character (alphanumeric & underscore). Only matches low-ascii characters (no accented or non-roman characters).
- `\W` Matches any character that is not a word character. (alphanumeric and underscore)
- `\d` Matches any digit character. (0-9)
- `\p` Matches a character in the specified unicode category.

### Flags

Expression flags change how the expression is interpreted. Flags follow the closing forward slash of the expression.

- `i` Ignores case
- `g` Global search retain the index of the last match, allowing subsequent searches to start from the end of the previous match. Without the global flag, subsequent searches will return the same match.
- `m` Multiline flag When the multiline flag is enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.
- `u` Unicode
- `y` The expression will only match from its lastIndex position and ignores the global (g) flag if set. Because each search in RegExr is discrete, this flag has no further impact on the displayed results.
- `s` Dot (.) will match any character, including newline.

NOTE: Unicode is an international character encoding standard that provides a unique number for every character across languages and scripts.

### Grouping and Capturing

- `(ABC)` Capturing groups multiple tokens together and creates a capture group for extracting a substring or using a backreference.
- `(?<name>ABC)` named capturing group captures groups of a specific name.
- `\1` is a numeric Referance
- `(?:ABC)` Groups multiple tokens together without creating a capture group.

### Bracket Expressions

A bracket expression enclosed in square brackets is a regular expression that matches a single character, or collating element. If the initial character is a circumflex ^, then this bracket expression is complemented.

In this example

See Character Class to see some other examples.


### Greedy and Lazy Match

- 'Greedy' means matching the longest possible string. A Greedy quantifier tells the engine to match as many instances of its quantified token or subpattern as possible. This behavior is called greedy.

- 'Lazy' means matching the shortest possible string. A lazy quantifier tells the engine to match as few of the quantified tokens as needed. As you'll see in the table below, a regular quantifier is made lazy by appending a ? question mark to it.

NOTE: By default, a regex will perform a greedy match. We can use `?` to match in a lazy way.


### Boundaries

Not to be confused with actual characters, simply put, Boundaries are the places between characters. A Boundary should be thought of as a wall between any adjacent characters.

- The `\b` is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.

- Characters that are matched by the short-hand character class `\w` are the characters that are treated as word characters by word boundaries.

- Since digits are considered to be word characters, `\b4\b` can be used to match a 4 that is not part of a larger number. So saying `\b` matches before and after an alphanumeric sequence is more exact than saying “before and after a word”.

- `\B` is the negated version of `\b`. `\B` matches at every position where `\b` does not. Effectively, `\B` matches at any position between two word characters as well as at any position between two non-word characters.


### Back-references

- Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.

-For Example: `<([A-Z][0-9]*)\b[^>]*>.*?</\1>` This regex contains only one pair of parentheses, which capture the string matched by `[A-Z][0-9]*`. This is the opening HTML tag. The backreference `\1` references the first capturing group. `\1` matches the exact same text that was matched by the first capturing group. The `/` before it is a literal character. It is simply the forward slash in the closing HTML tag that we are trying to match.

### Look-ahead and Look-behind

`(?=ABC)` is a postive lookahead and it matches a group after the main expression without including it in the result.

`(?!ABC)` is a negitive lookahead and it specifies a group that can not match after the main expression (if it matches, the result is discarded)

`(?<=ABC>)` is a postive lookbehind and matches a group before the main expression without including it in the result.

`(?<!ABC)` is a negitive lookbehind and Specifies a group that can not match before the main expression (if it matches, the result is discarded).

Lookaheads and lookbehinds forces the main expressions to be what you have defined it as. Without it being exactly what it is it will not be accepted as a valid input.

## Author

My name is Brianna Saglimbeni, and I'm a full stack web developer in training with the University of Miami. My github is [bsaglimb](https://github.com/bsaglimb). Please also feel free to email me at bsaglimb@gmail.com. 