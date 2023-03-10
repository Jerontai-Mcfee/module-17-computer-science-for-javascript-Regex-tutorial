# Regex Tutorial
A Regex is shorthand for regular expressions.
A Regex is a string of text that lets you create patterns that help match,locate,and manage text.
These expressions are extremely useful for extracting data like phone numbers,emails, that follow a specific pattern from text. They can also be used in conjunction with any programming language including JavaScript.


## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.Here is a basic template that you can use to create your own cheatsheet:

## Table of Contents

- [Basic Syntax](#Basic-Syntax)
- [Anchors][def]
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
- [Example and Breakdown](#Example-and-Breakdown)

### Basic Syntax
<br>
 A regular expression is a sequence of characters that defines a search pattern. It can contain letters, numbers, and special characters. Some common special characters include:

* '.' (dot): matches any single character except a newline

* '*' (asterisk): matches the preceding character zero or more times

* '+' (plus): matches the preceding character one or more times

* '?' (question mark): matches the preceding character zero or one time

* '^' (caret): matches the beginning of a string

'$' (dollar sign): matches the end of a string
<br>
<br>

### Anchors
<br>
* '\b '- Matches the boundary between a word and a non-word character.

* '\B' - Matches the boundary between two word characters or two non-word characters.

* '^' - Matches the start of the string.

* '$' - Matches the end of the string.
<br>
<br>

### Quantifiers
<br>
Quantifiers allow you to specify how many times a character or group of characters should be matched. Some common quantifiers include:
* '* '- Matches zero or more occurrences of the previous character or group.

* '+'- Matches one or more occurrences of the previous character or group.

* '?'- Matches zero or one occurrence of the previous character or group.

'{m}' - Matches exactly m occurrences of the previous character or group.
'{m,n}' - Matches between m and n occurrences of the previous character or group.
<br>
<br>
### OR Operator
The "or" operator is denoted by the vertical bar | character. For example, the pattern cat|dog would match either "cat" or "dog". You can also use parentheses to group patterns together with the "or" operator. For example, the pattern (red|blue) car would match either "red car" or "blue car".
<br>

It's worth noting that the "or" operator has lower precedence than other operators, such as quantifiers and anchors. This means that if you use the "or" operator in a complex regex, you may need to use parentheses to group patterns together and ensure that the operator is applied correctly.

Here are some additional examples of how to use the "or" operator in regular expressions:

* (Jan|Feb|Mar)uary matches "January", "February", or "March"

* apple|orange|banana matches "apple", "orange", or "banana"

* (http|https)://www.example.com matches URLs that start with "http://www.example.com" or "https://www.example.com
<br>
<br>
### Character Classes

Character classes allow you to match specific types of characters. Some common character classes include:

* '\d': matches any digit (0-9).

* '\w': matches any word character (letter, digit, or underscore).

* '\s': matches any whitespace character (space, tab, newline, etc.).

* '[]': matches any single character in the brackets.
<br>
<br>
### Flags
<br>
Flags are modifiers that can change the behavior of the pattern matching. Flags are usually specified after the closing delimiter of the regular expression and are denoted by a single letter.

Here are some common flags and their meanings:
<br>
<br>
* 'i' (case-insensitive): Makes the matching case-insensitive. For example, the pattern /apple/i would match "apple", "Apple", "aPpLe", and so on.

* 'g' (global): Matches all occurrences of the pattern in the input string. For example, the pattern /a/g would match all occurrences of the letter "a" in the input string.

* 'm' (multiline): Allows the ^ and $ anchors to match the beginning and end of each line in a multiline string, instead of just the beginning and end of the entire string.

* 's' (dot-all): Allows the . character to match any character, including newlines.

* 'u' (unicode): Enables full Unicode support. This is useful for matching characters from non-Latin scripts or for working with text that contains characters outside the ASCII range.

* 'y' (sticky): Matches the pattern starting at the current position in the string, without backtracking. This flag is useful for finding matches in large strings or for implementing custom text editors.

To use flags in a regular expression, you simply append the flag letter after the closing delimiter of the expression. For example, the pattern /apple/i would match "apple", "Apple", "aPpLe", and so on, because the i flag makes the matching case-insensitive.
<br>
<br>

Note that different programming languages and tools may have slightly different syntax for specifying flags, so be sure to consult the documentation for your specific implementation.
<br>
<br>
### Grouping and Capturing
Grouping allows you to apply a quantifier to a group of characters. Some common grouping syntax include:

* '()' (parentheses): group characters together

* '|' (pipe): match one of several possible patterns

* '(?)' (non-capturing parentheses): group characters without capturing the match
<br>
<br>

### Bracket Expressions
<br>
In regular expressions, bracket expressions (also known as character classes) allow you to match any one character from a set of characters. A bracket expression is enclosed in square brackets [] and contains a list of characters or character ranges that you want to match.

Here are some examples of bracket expressions:

* '[abc]': Matches any one character that is either "a", "b", or "c".

* '[a-z]': Matches any one lowercase letter from "a" to "z".

* '[A-Z]': Matches any one uppercase letter from "A" to "Z".

* '[0-9]': Matches any one digit from "0" to "9".

* '[aeiou]': Matches any one lowercase vowel.
<br>
<br>
You can also use the ^ character at the beginning of a bracket expression to create a negated character class. For example, [^abc] matches any one character that is not "a", "b", or "c".

You can include special characters, such as . or *, inside a bracket expression, but they will match literally, not as metacharacters. For example, [*+] matches either "*" or "+", not any number of the preceding character.

Here are some additional examples of bracket expressions:

* '[\d]': Matches any one digit (equivalent to [0-9]).

* '[\w]': Matches any one word character, which includes letters, digits, and underscores (equivalent to [a-zA-Z0-9_]).

* '[\s]': Matches any one whitespace character, such as a space or a tab.

* '[aeiouyAEIOUY]': Matches any one vowel, either lowercase or uppercase.


<br>
<br>
### Greedy and Lazy Match
<br>
In regular expressions, quantifiers such as *, +, and ? are greedy by default, which means they match as many characters as possible while still allowing the overall pattern to match. However, you can make a quantifier lazy (or non-greedy) by appending a question mark ? after it.

For example, consider the input string "ababab". The pattern /a.*b/ would match the entire string, because the * quantifier is greedy and matches all occurrences of any character between "a" and "b". 

However, the pattern' /a.*?b/ 'would only match the substring "ab", because the *? quantifier is lazy and matches as few characters as possible between "a" and "b".

Here are some additional examples of greedy and lazy matching:

* The pattern '/a+/' would match one or more occurrences of the letter "a" in the input string, while the pattern '/a+?/' would match as few occurrences of "a" as possible.

* The pattern '/a.*c/' would match any substring that starts with "a" and ends with "c", while the pattern /a.*?c/ would match the shortest such substring.

* The pattern '/<.*>/' would match any text enclosed in angle brackets, while the pattern '/<.*?>/' would match the shortest such text.

In general, it's a good idea to use lazy matching when you know that there may be multiple possible matches within a string, and you want to find the shortest match that satisfies the pattern. However, it's also important to be aware of the potential performance implications of using lazy matching, especially for large or complex input strings.


<br>
<br>
### Boundaries

<br>

In regular expressions, boundaries allow you to match patterns only at certain positions in the input string. There are two types of boundaries: the caret '^' and the dollar sign '$'.

The caret '^' is used to match the beginning of a string or the beginning of a line in a multiline string. For example, the pattern '^apple' would match the word "apple" only if it appears at the beginning of the string or at the beginning of a line.

The dollar sign '$' is used to match the end of a string or the end of a line in a multiline string. For example, the pattern 'apple$' would match the word "apple" only if it appears at the end of the string or at the end of a line.

Here are some additional examples of how to use boundaries in regular expressions:

* '^\d{3}-\d{2}-\d{4}$': Matches a social security number in the format of "###-##-####".

* '^\w+@[a-zA-Z_]+?\.[a-zA-Z]{2,3}$': Matches an email address in a standard format.

* '^The\b': Matches the word "The" only when it appears at the beginning of a word. This prevents the pattern from matching words like "Theresa" or "Them".

* '\bcat\b': Matches the word "cat" only when it appears as a separate word. This prevents the pattern from matching words like "category" or "scatter".

Note that the behavior of boundaries may vary depending on the programming language or tool you are using, so be sure to consult the documentation for your specific implementation.

### Back-references
<br>
In regular expressions, a back reference is a reference to a previously matched sub-expression. You can use back references to match a repeated pattern, or to ensure that a pattern appears twice in a row.
<br>
<br>
Back references are created by enclosing a sub-expression in parentheses, and then referring to it later in the pattern by its numerical order. The first sub-expression is referred to as '\1', the second sub-expression as '\2', and so on.
<br>
<br>
For example, the pattern '(\w+)\s+\1' would match any word that appears twice in a row, separated by one or more whitespace characters. The first sub-expression '(\w+)' matches any word, and the '\s+' matches one or more whitespace characters. The back reference '\1' then matches the same word that was matched by the first sub-expression, ensuring that the pattern appears twice.
<br>
<br>
Here are some additional examples of back references:
<br>
<br>

* The pattern '(\d{3})-(\d{2})-\1'  would match any string in the format of "###-##-###", where the first and last sets of digits are the same.

* The pattern '<(.*?)>(.*?)<\/\1>' would match any text enclosed in matching HTML tags, such as '<p>some text</p>'. 

  The first sub-expression '(.*?) 'matches the tag name, which is then referred to by the back reference '\1'. 
  The second sub-expression '(.*?)' matches the text between the tags.

* The pattern '(\w)\1+' would match any consecutive repeated characters in a word, such as "ee" in "sheep" or "tt" in "butter". The first sub-expression '(\w)' matches any word character, which is then referred to by the back reference '\1'.
<br>
Back references can be very useful for finding repeated patterns or ensuring that certain patterns appear in a specific order. However, they can also be complex to use and may have performance implications for large or complex input strings, so use them judiciously.
<br>
<br>

### Look-ahead and Look-behind
Lookahead and lookbehind are special types of zero-width assertions in regular expressions that allow you to match a pattern based on what comes before or after the current position in the input string, without including those characters in the final match. Look-around expressions are also sometimes called "look-around assertions".

There are two types of look-around expressions: lookahead and lookbehind.

* 1. Positive look-ahead '(?=pattern)' asserts that the current position in the input string is followed by the pattern 'pattern'. The pattern is matched, but not included in the final match.

For example, the pattern 'foo(?=bar)' would match any occurrence of the word "foo" that is immediately followed by the word "bar". This would match "foobar" but not "foobazbar".

* 2. Negative look-ahead '(?!pattern) asserts that the current position in the input string is not followed by the pattern pattern.

For example, the pattern foo(?!bar) would match any occurrence of the word "foo" that is not immediately followed by the word "bar". This would match "foobaz" but not "foobar".

* 3. Positive look-behind '(?<=pattern)' asserts that the current position in the input string is preceded by the pattern pattern. The pattern is matched, but not included in the final match.

For example, the pattern '(?<=abc)def' would match any occurrence of the word "def" that is immediately preceded by the letters "abc". This would match "abcdef" but not "defabc".

* 4. Negative look-behind '(?<!pattern)' asserts that the current position in the input string is not preceded by the pattern pattern.

For example, the pattern '(?<!abc)def' would match any occurrence of the word "def" that is not immediately preceded by the letters "abc". This would match "defghi" but not "abcdef".

Look-around assertions can be very useful for complex matching scenarios, where you need to match a pattern only if it is preceded or followed by certain other patterns. However, they can also be complex to use and may have performance implications for large or complex input strings, so use them judiciously.
<br>
<br>

### Example And Breakdown

Here's an example regex that matches the email "jerontai07@gmail.com":

'/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/ '

Let's break this down:

* '^' is an anchor that matches the beginning of the input string.

* '[a-zA-Z0-9._%+-]+' matches one or more characters that are letters (both uppercase and lowercase), digits, or any of  
the characters ".", "_", "%", "+", or "-".  This matches the username portion of the email address.
   
* '@' matches the "@" character that separates the username from the domain name.

* '[a-zA-Z0-9.-]+' matches one or more characters that are letters (both uppercase and lowercase), digits, or the characters "." or "-". This matches the domain name portion of the email address, which can contain periods to separate subdomains or hyphens.

* '\.' matches a literal "." character. We need to escape the period with a backslash since it has a special meaning in regular expressions.

* '[a-zA-Z]{2,}' matches two or more characters that are letters (both uppercase and lowercase). This matches the top-level domain of the email address, such as "com", "org", or "edu". Note that some top-level domains have more than two letters, so this pattern will also match those.

* '$' is an anchor that matches the end of the input string.

This regular expression uses character classes, repetition, anchors, and escape sequences to match the email "jerontai07@gmail.com".
<br>
<br>
 The character classes '[a-zA-Z0-9._%+-]' and '[a-zA-Z0-9.-]' allow for a wide variety of characters in the username and domain name, while the use of repetition with the "+" and "{2,}" operators ensures that there are one or more characters in each part of the email address. The anchors "^" and "$" ensure that the email address is matched in its entirety and not just as part of a larger string.

<br>

## Author
<br>
Hey my name is Je'Rontai Mcfee

I am a very passionate student at the Georgia Institute of Technology. I have Developed and Honed my skills in their Full-stack Web Developer program.

Github:https://github.com/Jerontai-Mcfee

Github repository: https://github.com/Jerontai-Mcfee/module-17-computer-science-for-javascript-Regex-tutorial

 Email: jerontai07@gmail.com

[def]: #anchors