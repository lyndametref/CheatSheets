# Anchors
    ^	Start of line or start of string
    $	End of line or end of string
    \A \Z Start/end of string
    \b Word boundary
    \B Not word boundary
    \< \> Start/End of word

Characters types
    .	Matches any character except new line (\n)
    \n New line
    \r Carriage return
    \t Tab
    \s Whitespace
    \S Non-whitespace character
    \c Control character
    \d Digit
    \D Not digit
    \w Word
    \W Not word

# Assertions
    ?= Lookahead assertion
    ?! Negative lookahead
    ?<= Lookbehind assertion
    ?!= or ?<! Negative lookbehind
    ?() Condition [if then]
    ?()| Condition [if then else]
    

Quantifiers
* Repeat 0 or more times
+ Repeat 1 or more times
{3} Repeat exactly 3 times
{3,} 3 or more times
? Repeat 0 or 1 time
{3,5} Repeat 3, 4 or 5
Add a ? to a quantifier to make it ungreedy.

# Meta characters to escape with \
^ [ ] . $ { } * ( ) \ +  | ? < >

# Replacement
(...) Group (for string extraction)
(?:...) Passive (non-c­apt­uring) group
$1 "­xyz­" in /^(?:a­bc)­(xyz)$/
$2 "­xyz­" in /^(abc­(xy­z))$/

# Ranges
(a|b) a or b
[abc] Range (a or b or c)
[^abc] Not (a or b or c)
[a-q] Lower case letter from a to q
[A-Q] Upper case letter from A to Q
[0-7] Digit from 0 to 7
[a-z0-9]	The set of characters can include a range

# Inspired from
* http://www.dr-chuck.net/pythonlearn/lectures/Py4Inf-11-Regex-Guide.doc
* https://www.cheatography.com/davechild/cheat-sheets/regular-expressions/