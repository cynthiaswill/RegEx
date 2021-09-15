# RegEx
This reference sheet has been created to provide a quick and easy lookup for Regex. There's also a few code examples to help explain certain concepts

## RegEx Character Classes

```/d/``` find a digit<br>
```/w/``` find a letter<br>
```/s/``` find a whitespace<br>
```/D/``` find anything NOT a digit<br>
```/W/``` find anyhting NOT a letter<br>
```/S/``` find anything NOT a whitespace<br>

## Pattern Modifiers

```//g``` = global match<br>
```//i``` = case insensitive<br>
```//m``` = multiline<br>
```//s``` = treat string as single line<br>

## Boundary Assertions

```/^A/``` = does string begin with 'A'?<br>
```/^[abc]/``` = does string begin with 'a', 'b', or 'c'?<br>
```/A$/``` = does string end with 'A'?<br>

## Groups and Ranges

```/./``` = show any character except new line<br>
```/(abc|def|ghi)/``` = find abc OR def OR ghi<br>
```/[abc]/``` = does a, b, or c exist within the string<br>
```/[a-c]/``` = does a, b, or c exist within the string<br>
```/[^a-c]/``` = match anything that is NOT a, b, or c<br>

## Capturing Groups
```/^(\+447|00447|07)\d{9}$/``` = find only strings that begin with +447, 00447, or 07

## Quantifiers
```/bo*/``` matches "booo" in a "Ghost boooed" and "b" in "bird song" but nothing in "goat herd", match 0 or more times<br>
```/a+/``` matches a in "candy" and "caaaaandy", match 1 or more times<br>
```/e?le?/``` matches "el" in "angel" and the "le" in "angle", match 0 or 1 times<br>
```/WordLength{4, 16}/``` = return a word that a min length of 4 upto 16<br>

## RegExp JavaScript Test Methods

```.exec()``` = tests for string, returns first match<br>
```.test()``` = tests for match in string, returns true : false<br>
```.match()``` = retrieves the result of matching string against regex<br>
```.matchAll()``` = retrieves all results of matching strings against regex<br>
```.search()``` = searches for a match between regex and string<br>
```str.replace(regex, 'wordUsedToReplace')``` = replace first occurrence in string<br>
```str.replaceAll(regex, 'wordUsedToReplace')``` = replace all occurences in string<br>

## Use Cases
```
const validateCode = code => {
  return /^(1|2|3)/g.test(code);
}
```
Does the string begin with 1, 2, or 3? Returns true : false
```
String.prototype. = function() {
  return /^[a-z]$/i.test(this);
}
```
Does the string begin and end with any alphabet character? Returns true : false
```
const validateUsr = username => {
  return /^[a-z0-9_]{4,16}$/.test(username);
}
```
Does the username contain begin and end with lowercase a-z, digits, an underscore, and is the length between 4 & 16?
```
const lowercaseCount = str => {
  return (str.match(/[a-z]/g) || '').length;
}
```
Count all lowercase a-z in the string then return the length

```
const hyphenate = words => {
  return words.replace(/ /g, '-');
}
```
Replace any white space with a hyphen
