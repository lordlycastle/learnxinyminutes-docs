---
lanuage:applescript
contributors:
    ["lordlycastle","https://github.com/lordlycastle"]
    filename:learnapplescript.applescript
    
AppleScript is a scripting langauge created by Apple, which lets users control
"scriptable" Maintosh applications along with parts of the OS X, to automate
repetitive tasks, combine features from multiple scriptable applications, and
create complex workflows. 

AppleScript has some elements of object-oriented programming, particularly in
the construction of script objects, and natural language programming
tendencies in its syntax, but does not strictly conform to either category.
```applescript
-- Single end of line comment
(* Multi-line comment
    Starting AppleScript 2.0 '#' is also supported as end of line comment.
    A text script with the shebang line '#!/usr/bin/osascript', and 
    executable permission is also an acceptable script.
*)

-- Statements are terminated by newline
set num to 69
set str to "Hello, world!"

-- To extend statements to next line use the continuation character; ¬.
-- In a U.S keyboard, it can be enterted with Alt(⌥)+l(lowercase L).
-- Script editor (defualt AppleScript editor) uses Alt(⌥)+Return(↩) as shortcut
display dialog "How do like AppleScript so far?" buttons {"Great", "OK"} ¬
default button "OK" giving up after 3

-- Basic variable types:

-- Boolean
true
false

-- Strings are enclosed with ". String, and text classes are the same
set myString to "Try the Moo Shu Pork!"
set america to "Freedom" & "Democracy" -- '&' joins the strings

-- Number
set myNumber to 2
-- Basic arithmetic works as you'd expect. Precedence is enforced with brackets
set daysInWeek to 5 + 2
set weekDays to daysInWeek - 2.0
set chinasPopulation to 1.36 * (10 ^ 9)
set largeNumber to 9.9999999999E+10
set minusPiBy2 to - (pi / 2) -- 'pi' is one of the constants (read-only)

-- List (Array): defines a mutable collection of value, known as items.
-- Don't have be of same type.
set thingsILike to {"Beethoven", {"Cake", "Ice-Cream"}, 3.14159, 42}
set foodILike to item -3 of thingsILike -- negative index i.e from the end 
set end of thingsILike to "AppleScript" -- appends the string to the list
set item 1 of item 2 to "Chocolate Cake" -- Replace "Cake" of the embedded list
set numbersILike to item 3 thru 4 of thingsILike -- range using 'thru'

-- Record (Dictionary): record is an unordered collection of labeled properties
set cookie to {product:"Cookie", price:1.99}
set deserts to {{product:"Cupcake", price:0.99}, cookie} -- List of Records
-- You can use 'of' to access value for key.
set total to (price of cookie) + (price of (item 1 of deserts)) -- 2.98

-- There are some Application specific variable types, which we'll get to later.


-- Negation uses 'not' keyword
set myFalse to not true -- is equal to false
set myTrue to not false -- is equal to true

-- Equality is 'is equal to', or 'is'
"Breakfast" is equal to "Break" & "fast" -- true 
"Crumpet" is equal to "Muffin" -- false
price of cookie is 1.99 -- true
4 + 2 is 42 --false

-- Inequality is 'is not equal to', or 'is not'
"Football" is not equal to "Soccer" -- true
product of item 1 of deserts is not equal to "Cupcake" -- false
"Bing" is not "Google" -- true
item 1 of deserts is not {product:"Cupcake", price:0.99} -- false

-- More Comparisons
-- Less than/equal to
length of "Boo" is less than 4 -- true
9 < 7 -- false
price of cupcake ≤ 1 -- true. Alt(⌥)+, for ≤. Alt(⌥)+. for ≥.
pi is less than or equal to 3.14 -- false 'pi' is equal to 3.14159265359

--More than/equal to 
length of "Boo freaking who" is more than length of "You!" --true
7 + 0.99999 > 8 -- false
pi as integer ≥ 3 -- true. 'pi' is integer is 3 (round to nearest int)
length of "Breakfast" ≥ length of "Break" + length of "fast" -- false



```