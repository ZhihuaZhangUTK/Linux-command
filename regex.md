# Regular experssion


## Characters
| Character | Legend | Example | Sample Match |
| ------------- | ------------- | ------------- | ------------- |
| \d	| Most engines: one digitfrom 0 to 9	| file_\d\d	| file_25
| \d	| .NET, Python 3: one Unicode digit in any script	| file_\d\d	| file_9੩
| \w	| Most engines: "word character": ASCII letter, digit or underscore	| \w-\w\w\w	| A-b_1
| \w	| .Python 3: "word character": Unicode letter, ideogram, digit, or underscore	| \w-\w\w\w	| 字-ま_۳
| \s	| .NET, Python 3, JavaScript: "whitespace character": any Unicode separator	| a\sb\sc	| a b
| \D	| One character that is not a digit as defined by your engine's \d	| \D\D\D	| ABC
| \W	| One character that is not a word character as defined by your engine's \w	| \W\W\W\W\W	| @-+=)
| \S	| One character that is not a whitespace character as defined by your engine's \s	| \S\S\S\S	| Yoyo

## Quantifiers

| Quantifier	| Legend	| Example	| Sample Match
| ------------- | ------------- | ------------- | ------------- |
| +	| One or more	| Version \w-\w+	| Version A-b1_1
| {3}	| Exactly three times	| \D{3}	| ABC
| {2,4}	| Two to four times	| \d{2,4}	| 156
| {3,}	| Three or more times	| \w{3,}	| regex_tutorial
| *	| Zero or more times	| A*B*C*	| AAACC
| ?	| Once or none	| plurals?	| plural

## More Characters
| Character	| Legend	| Example	| Sample Match
| ------------- | ------------- | ------------- | ------------- |
| .	| Any character except line break	| .*	| whatever, man.
| \.	| A period (special character: needs to be escaped by a \)	| a\.c	| a.c
| \	| Escapes a special character	| \.\*\+\?    \$\^\/\\	| .*+?    $^/\

## Logic
| Logic	| Legend	| Example	| Sample Match
| ------------- | ------------- | ------------- | ------------- |
| |	Alternation / OR operand	| 22|33	| 33
| ( … )	| Capturing group	A(nt|pple)	| Apple | (captures "pple")
| \1	| Contents of Group 1	| r(\w)g\1x	| regex
| \2	| Contents of Group 2	| (\d\d)\+(\d\d)=\2\+\1	| 12+65=65+12

## Anchors and Boundaries
| Anchor	| Legend	| Example	| Sample Match
| ------------- | ------------- | ------------- | ------------- |
| ^	| Start of string or start of line depending on multiline mode. (But when [^inside brackets], it means "not")	| ^abc .*	| abc (line start)
| $	| End of string or end of line depending on multiline mode. Many engine-dependent subtleties.	| .*? the end$	| this is the end
| \A	| Beginning of string (all major engines except JS)	| \Aabc[\d\D]*	| abc (string......start)
| \z	| Very end of the stringNot available in Python and JS	| the end\z	| this is...\n...the end
| \Z	| End of string or (except Python) before final line break Not available in JS	| the end\Z	| this is...\n...the end\n
| \G	| Beginning of String or End of Previous Match .NET, Java, PCRE (C, PHP, R…), Perl, Ruby		
| \b	| Word boundary Most engines: position where one side only is an ASCII letter, digit or underscore	| Bob.*\bcat\b	| Bob ate the cat
| \B	| Not a word boundary	| c.*\Bcat\B.*	| copycats



## Lookarounds
| Lookaround	| Legend	| Example	| Sample Match
| ------------- | ------------- | ------------- | ------------- |
| (?=…)	| Positive lookahead	| (?=\d{10})\d{5}	| 01234 in 0123456789
| (?<=…)	| Positive lookbehind	| (?<=\d)cat	| cat in 1cat
| (?!…)	| Negative lookahead	| (?!theatre)the\w+	| theme
| (?<!…)	| Negative lookbehind	| \w{3}(?<!mon)ster	| Munster





## Flags

A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):

- g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
- m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
 - i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)
 
 
 Grouping and capturing — ()
 - a(bc)           parentheses create a capturing group with value bc
 - a(?:bc)*        using ?: we disable the capturing group
 - a(?<foo>bc)     using ?<foo> we put a name to the group 
 
