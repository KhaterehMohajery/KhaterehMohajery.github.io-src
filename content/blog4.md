Title: Regular Expression 
Date: 2017-01-08 10:20
Category: Review

Regular Expressions are among the most amazing and helpful things you can have specially when you are working with text data. It is much easier to find patterns, groups or specific characters using regular expression (aka regex).
There are few ones that are specially very helpful:
such as:

\d  Any digit

\D  Any Non-digit character

\+   One or more repetition 

[abc]  Only a, b, or c

[^abc]  Not a, b nor c

 \w 	Any Alphanumeric character
 
 \W 	Any Non-alphanumeric character
 
 \s  Any whitespace
 
 \S  Any Non-whitespace 
 
 ^ $  Starts and ends
 
 ?  Optional character 
 
some example :

 \d+  matches any numbers (integers)
 
 ab?c  matches either the strings "abc" or "ac" because the b is considered optional
 
 ^Hello  matches each line that starts with Hello
 
 bye$  matches each line that end with bye
 
 '^\W+|\W+$'  gets rid of punctuations
 
Use regular expressions with split, replace, stripe methods on strings in pandas and you can easily deal with your messy text data!
