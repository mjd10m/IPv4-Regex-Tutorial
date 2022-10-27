# Title Introductory Tutorial to the IPv4 IP Address Regex

Regular expressions, or regex for short, are a series of special characters that define a search pattern.  They can be used to find a string made of specific character or strings that contain certain characters.  They are made up of a series of characters that have a different meaning depending on how they appear in the series.  Regex's are universal and the same ones can be used across all programing languages and give you the same result.

## Summary

In this tutorial i will be covering the IPv4 IP Address Regex and will go over the various components of the Regex and how to interpret what each character in the expression means.  It contains several of the Regex Compnents such as Anchors, Quantifier, Or Operators and many more which will all be covered in this tutorial. 

Regex Code: ^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$

## Table of Contents

- [Anchors](#anchors)
- [Bracket Expressions](#bracket-expressions)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Greedy and Lazy Match](#greedy-and-lazy-match)

## Regex Components

Regex Components used in the IPv4 Regex:
Bracket Expressions
Anchors
Quantifier
Or Operator
Grouping and Capturing
Greedy and Lazy Match

### Anchors

Anchors are used to specify what characters or group of characters the the string must begin and end with for the string to be considered valid.  The ^ anchor is used to signify what characters the string must begin with.  The $ anchor is used to signify what characters the must end with.  The IPv4 Regex tells us that the string must beging with (characters coming after the ^) and end with (characters coming before the $) a numerical value between 0-255.  In the next section we will cover how the 0-255 range is being determined.

### Bracket Expressions

Bracket Expressions are used to represent a range of characters that we want to match in our string.  In the IPv4 Regex there are a few variations of the numerical ranges.  [0-9] allows any character between 0 and 9.  Since we can only used 0 thru 9 in order to look for values greater than 9 we must combine multiple bracket expressions to get the desired number.  To get numbers from 10 to 99 we use [1-9][0-9].  Now since we only want to accept numbers up to 255 once we get to 3 digits we have to be a little more specific with out ranges, for numbers 100 to 200 it would look like 1[0-9][0-9] and similarly for 200 to 255 we use whatever range combinations needed to accept up to 255.  Now you will notice that in the Regex above for 100 to 200 we actually use 1[0-9]{2} but this is the same as 1[0-9][0-9] and will cover what that  curley bracket means in the next section.

### Quantifiers

Quantifiers are used to set limits on the string that your match your regex.  They can include a minimum and maximum, atleast a specfied number of times or an exact number of times.  In the IPv4 Regex there are two instances where the curley brackets are used, the one mention in the previous section and then a {3} after the beginning anchor.  A single number within the bracket signifies that the string pattern that comes before it must occur the exactly the number of times as the number in the brackets.  So the {3} tells us that the starting string pattern must occur 3 times.

### OR Operator

Sometimes in a Regex Expression we want to accept multiple variations of a string.  To do that we use the | to signify that we will accept either this string or that string.  In the IPv4 there are several OR Operatiors so that we can include the entire range from 0 to 255 because the bracket expressions for defining ranges does not all us to simply put [0-255].  

### Character Classes

Character classes are essentailly built in shortcuts that allow you to define a range.  The IPv4 Regex does not have any character classes but \d could be used to represent the [0-9] expressions in leu of writing the whole expression out.

### Character Escapes

Backslash (\) is used to signify a character escape.  This escapes a character that would otherwise be interpreted literally.  In the IPv4 Regex you can see that there is a backslash before the period, that is because we want to look for an actual period in the string and do not want the it to be interpreted as the chracter class associated with a period.

### Grouping and Capturing

In Regex Expressions we use () in order to group parts of the expression together.  These create what we call subexpressions and help keep out expressions more orgainzed as they become more complex.  In the IPv4 Regex you can see that all of the bracket expression we use to make our 0 to 255 range are within parentheses signifying that they are grouped together.  You can also see that the information related to the beginning and ending anchors are also grouped together so we can easily associate which expressions belong to which anchors

### Greedy and Lazy Match

Quantifiers have two differnt ways they can match.  Greedy where for every position in the string it ties to match the pattern at that position or lazy where it will try to repeat the search a miniaml number of times.  The curely bracket quantifiers as well as the others are inheritenly greedy essentially meaning there will be by default more changes for the pattern to match.  In order to make a quantifer lazy you must add the ? after the quantifer which will change it to match as few occurences as possible thus making it harder to have a valid string. 

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
