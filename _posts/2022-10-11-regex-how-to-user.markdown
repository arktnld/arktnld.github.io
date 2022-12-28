---
layout: post
title:  "Regex how to User"
date:   2022-10-11 08:35:10 -0300
categories: jekyll update
---
# Learning Regular Expressions

## Meta Characters

- Quotation marks are not meta characters

### WildCard

/h.t/ matches "hat" "hot" and "hit" but not "heat"

### Spaces

- tabs: \t
- line return: \r, \n, \r\n

## Character Set

/gr[ae]y/ matches "grey" and "gray"
/gr[ea]t/ does not match "great"

### Ranges

Includes al characters between two characters
[0-9]
[A-Za-z]
[50-99] is not all numbers from 50 to 99, it is the same as [0-9]

### Negative Character set

/see[^mn]/ matches "seek" and "sees" but not "seem" or "seen", does not match "see"

### Meta Characters Inside Character Sets
Most meta characters inside character sets are already escaped
/h[a.]t/ matches "hat" and "h.t", but not "hot"
Exceptions: ] - ^ \

### Shorthand Character Sets

\d - digit [0-9]
\w - word  [a-zA-Z0-9_]
\s - whitespace [\t\r\n]

\D - not digit [^0-9]
\W - not word [^a-zA-Z0-9_]
\S - not whitespace [^\t\r\n]

## Repetition

* - zero or more times
+ - one or more times
? - zero or one time

/.+/ matches any string of characters except a line return

/apples*/ matches "apple", "apples", and "applessssssss"
/apples+/ matches "apples", "applessssss", but not "apple"
/apples?/ matches "apple", "apples", but not "applesssssssss"

/\d\d\d\d*/ matches numbers with three digits or more
/\d\d\d+/ matches numbers with three digits or more

/colou?r/ matches "color" and "colour"

### Quatified Repetition

{min,max}
- min and max are positive numbers
- min must always be included and can be zero

\d{4,8} matches numbers with four to eight digits
\d{4} matches number swith exactly four digits (min is max)
\d{4,} matches numbers with four or more digits (max is infinite)

\d{0,} is the same as \d*
\d{1,} is the same as \d+

/\d{3}-\d{3}-\d{4}/ matches most US phone numbers

/A{1,2} bonds/ matches "A bonds" and "AA bonds", not "AAA bonds"

### Greedy Expressions

Standard repetition quantifiers are greedy:
- Expression tries to match the longest possible string
- Defers to achieving overall match
- /.+\.jpg/ matches "filename.jpg"
- The + is greed, but "gives back" the ".jpg"to make the match

Gives back as little as possible:
- /.*[0-9]+/ matches "Page 266"
- .* portion matches "
- [0-9]+ portion matches only "6"
- Match as much as possible before giving control to the next expression part

Regular expression engines are eager and greedy

### Lazy Expressions
> *?
> +?
> {min,max}?
> ??

Instructs quantifier to use a "lazy strategy" for making choices
- Match as little as possible before control to the next expression part
- Still defers to overall match
- Mot necessarily faster or slower

/.*?[0-9]+/ trying to match "Page 266", they try to match with wildcard as many times as a digit appears

## Grouping and Alternating
/(abc)+/ matches "abc" and "abcabcabc"
/(in)?dependent/ matches "independent" and "dependent"
/run(s)?/ is the same as /runs?/

- Group portions of the expression
- Apply repetition operators to a group
- Create a group of alternation expressions
- Captures group for use in matching and replacing

### Alternation Metacharacter
- | is an OR operator
- Either match expression on the left or match expression on the right
- Ordered, leftmost expression gets precedence
- Multiple choices can be daisy-chained
- Group alternation expressions to keep them distinct

 >   /w(ei|ie)rd/ matches "weird" and "wierd"

## Archors
^ start of string/line
$ end of string/line
\A start of string, never end of line
\Z end of string, never end of line

- reference a position, not an actual character
- Zero-width
- /^apple/ or /\Aapple/
- /apple$/ or /apple\Z/
- /^apple$/ or /\Aapple\Z/

Use "m" flag to match end and start on all lines

### Work Boundaries
- Reference a position, not an actual character
- Before the first word character in the string
- After the last word character in the string
- Between a word character and a non-word character
- workd characters [A-Za-z0-9_]

/\ba\b/ match all "a" that are alone
