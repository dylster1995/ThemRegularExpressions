# Regular Expressions (Did we learn it? Well... we are now.)

Welcome to the great big world of Regular expressions. Here is a cheatsheet for you to refer to on your journey.

## Summary

Regular expressions are great. They help you filter text by defining patterns to search for. 

## Table of Contents

- [Regular Expressions (Did we learn it? Well... we are now.)](#regular-expressions-did-we-learn-it-well-we-are-now)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
      - [/* - this* - Get string that goes thi with any number of 's' at the end.](#---this---get-string-that-goes-thi-with-any-number-of-s-at-the-end)
      - [/+ - this+ - Get string that goes thi with any number of 's' greater than 0 at the end.](#---this---get-string-that-goes-thi-with-any-number-of-s-greater-than-0-at-the-end)
        - [? - this? - Get string that goes thi with either 0 or 1 's' at the end.](#---this---get-string-that-goes-thi-with-either-0-or-1-s-at-the-end)
      - [{number} - this{3} - Get string that goes 'thisss' (3 s at the end).](#number---this3---get-string-that-goes-thisss-3-s-at-the-end)
      - [{minNumber,} - this{3,} - Get string that goes thi with 2 or more 's' at the end.](#minnumber---this3---get-string-that-goes-thi-with-2-or-more-s-at-the-end)
      - [{minNumber,maxNumber} - this{3,3} - Get string that goes 'thisss' (has at least 3 and at most 3 's' at the end).](#minnumbermaxnumber---this33---get-string-that-goes-thisss-has-at-least-3-and-at-most-3-s-at-the-end)
      - [()* - th(is)* - Get string that goes 'th' and then any number of 'is'.](#---this---get-string-that-goes-th-and-then-any-number-of-is)
      - [(){minNumber, maxNumber} - th(is){3,5} - Get string that goes 'th' then any number of 'is' between 3 and 5.](#minnumber-maxnumber---this35---get-string-that-goes-th-then-any-number-of-is-between-3-and-5)
    - [OR Operator](#or-operator)
      - [(|) - th(i|s) - Get string that goes 'th' then either 'i' or 's'.](#---this---get-string-that-goes-th-then-either-i-or-s)
      - [[] - th[is] - Get string that goes 'th' only if the an 'i' or 's' follows it.](#---this---get-string-that-goes-th-only-if-the-an-i-or-s-follows-it)
    - [Character Classes](#character-classes)
      - [\d - \d - Gets a numberic character from a string.](#d---d---gets-a-numberic-character-from-a-string)
      - [\w - \w - Gets a word character from a string.](#w---w---gets-a-word-character-from-a-string)
      - [\s - \s - Gets a whitespace character.](#s---s---gets-a-whitespace-character)
      - [. - . - Gets any character.](#------gets-any-character)
      - [\D - \D - Gets a non-numberic character from a string.](#d---d---gets-a-non-numberic-character-from-a-string)
      - [\W - \W - Gets a non-word character from a string.](#w---w---gets-a-non-word-character-from-a-string)
      - [\S - \S - Gets a non-whitespace character.](#s---s---gets-a-non-whitespace-character)
    - [Flags](#flags)
      - [g - Gets all values matching the pattern rather than just the first.](#g---gets-all-values-matching-the-pattern-rather-than-just-the-first)
      - [m - Used with ^ and $ to get the start and end of a line rather than the entire string.](#m---used-with--and--to-get-the-start-and-end-of-a-line-rather-than-the-entire-string)
      - [i - Used to include non-case sensitive results.](#i---used-to-include-non-case-sensitive-results)
    - [Grouping and Capturing](#grouping-and-capturing)
      - [() - th(is) - Gets 'is' from 'this' via capture group.](#---this---gets-is-from-this-via-capture-group)
      - [(?:)* - th(?:is)* - Gets 'is' from 'this' but actually doesn't cause it doesn't do the capture group.](#---this---gets-is-from-this-but-actually-doesnt-cause-it-doesnt-do-the-capture-group)
      - [(?<>) = th(?<name>is) - Adds the name 'name' to the capture group.](#--thnameis---adds-the-name-name-to-the-capture-group)
    - [Bracket Expressions](#bracket-expressions)
      - [[] - [this] - Gets any string that has a 't','h','i', or 's'.](#---this---gets-any-string-that-has-a-thi-or-s)
      - [[-] - [a-h] - Gets any string that has any letter between 'a' and 'h' in the alphabet.](#----a-h---gets-any-string-that-has-any-letter-between-a-and-h-in-the-alphabet)
      - [[---] - [a-fA-F0-9] - Gets any string with a single hexadecimal digit.](#------a-fa-f0-9---gets-any-string-with-a-single-hexadecimal-digit)
    - [Greedy and Lazy Match](#greedy-and-lazy-match)
    - [Boundaries](#boundaries)
    - [Back-references](#back-references)
    - [Look-ahead and Look-behind](#look-ahead-and-look-behind)
  - [Author](#author)

## Regex Components

### Anchors
^ - ^this - Get string that start with 'this'.
$ - this$ - Get string that end with 'this'.
^$ - ^this$ - Get string that begin and end with 'this'.
  - this - Get string that contain the string 'this'.

### Quantifiers
#### /* - this* - Get string that goes thi with any number of 's' at the end.
#### /+ - this+ - Get string that goes thi with any number of 's' greater than 0 at the end.
##### ? - this? - Get string that goes thi with either 0 or 1 's' at the end.
#### {number} - this{3} - Get string that goes 'thisss' (3 s at the end).
#### {minNumber,} - this{3,} - Get string that goes thi with 2 or more 's' at the end.
#### {minNumber,maxNumber} - this{3,3} - Get string that goes 'thisss' (has at least 3 and at most 3 's' at the end).
#### ()* - th(is)* - Get string that goes 'th' and then any number of 'is'.
#### (){minNumber, maxNumber} - th(is){3,5} - Get string that goes 'th' then any number of 'is' between 3 and 5.

### OR Operator
#### (|) - th(i|s) - Get string that goes 'th' then either 'i' or 's'.
#### [] - th[is] - Get string that goes 'th' only if the an 'i' or 's' follows it.

### Character Classes
#### \d - \d - Gets a numberic character from a string.
#### \w - \w - Gets a word character from a string.
#### \s - \s - Gets a whitespace character.
#### . - . - Gets any character.
#### \D - \D - Gets a non-numberic character from a string.
#### \W - \W - Gets a non-word character from a string.
#### \S - \S - Gets a non-whitespace character.

### Flags
#### g - Gets all values matching the pattern rather than just the first.
#### m - Used with ^ and $ to get the start and end of a line rather than the entire string.
#### i - Used to include non-case sensitive results.

### Grouping and Capturing
#### () - th(is) - Gets 'is' from 'this' via capture group.
#### (?:)* - th(?:is)* - Gets 'is' from 'this' but actually doesn't cause it doesn't do the capture group.
#### (?<>) = th(?<name>is) - Adds the name 'name' to the capture group.

### Bracket Expressions
#### [] - [this] - Gets any string that has a 't','h','i', or 's'.
#### [-] - [a-h] - Gets any string that has any letter between 'a' and 'h' in the alphabet.
#### [---] - [a-fA-F0-9] - Gets any string with a single hexadecimal digit.

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author
Dylan Yamashiro a new programmer just making their way in this journey of life. 
Github: https://github.com/dylster1995/ThemRegularExpressions
