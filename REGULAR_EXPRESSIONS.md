### Using the Test Method

Apply the regex ```myRegex``` on the string ```myString``` using the ```.test()``` method.

```javascript
let myString = "Hello, World!";
let myRegex = /Hello/;
let result = myRegex.test(myString); // Change this line
```

### Match Literal Strings

Complete the regex ```waldoRegex``` to find ```"Waldo"``` in the string ```waldoIsHiding``` with a literal match.

```javascript
let waldoIsHiding = "Somewhere Waldo is hiding in this text.";
let waldoRegex = /Waldo/; // Change this line
let result = waldoRegex.test(waldoIsHiding);
```

### Match a Literal String with Different Possibilities

Complete the regex ```petRegex``` to match the pets ```dog```, ```cat```, ```bird```, or ```fish```.

```javascript
let petString = "James has a pet cat.";
let petRegex = /dog|cat|bird|fish/; // Change this line
let result = petRegex.test(petString);
```

### Ignore Case While Matching

Write a regex ```fccRegex``` to match ```freeCodeCamp```, no matter its case. Your regex should not match any abbreviations or variations with spaces.

```javascript
let myString = "freeCodeCamp";
let fccRegex = /freecodecamp/i; // Change this line
let result = fccRegex.test(myString);
```

### Extract Matches

Apply the ```.match()``` method to extract the string ```coding```.

```javascript
let extractStr = "Extract the word 'coding' from this string.";
let codingRegex = /coding/; // Change this line
let result = extractStr.match(codingRegex); // Change this line
console.log(result); // was accepted, but logs an array
```

### Find More Than the First Match

Using the regex ```starRegex```, find and extract both ```Twinkle``` words from the string ```twinkleStar```.

```javascript
let twinkleStar = "Twinkle, twinkle, little star";
let starRegex = /twinkle/ig; // Change this line
let result = twinkleStar.match(starRegex); // Change this line
console.log(result);
```

### Match Anything with Wildcard Period

Complete the regex ```unRegex``` so that it matches the strings ```run```, ```sun```, ```fun```, ```pun```, ```nun```, and ```bun```. Your regex should use the wildcard character.

```javascript
let exampleStr = "Let's have fun with regular expressions!";
let unRegex = /.un/; // Change this line
let result = unRegex.test(exampleStr);
console.log(result);
```

### Match Single Character with Multiple Possibilities

Use a character class with vowels (```a```, ```e```, ```i```, ```o```, ```u```) in your regex ```vowelRegex``` to find all the vowels in the string ```quoteSample```.

```javascript
let quoteSample = "Beware of bugs in the above code; I have only proved it correct, not tried it.";
let vowelRegex = /[aeiou]/ig; // Change this line
let result = quoteSample.match(vowelRegex); // Change this line
console.log(result)
```

### Match Letters of the Alphabet

Match all the letters in the string ```quoteSample```.

```javascript
let quoteSample = "The quick brown fox jumps over the lazy dog.";
let alphabetRegex = /[a-z]/ig; // Change this line
let result = quoteSample.match(alphabetRegex); // Change this line
```

### Match Numbers and Letters of the Alphabet

Create a single regex that matches a range of letters between ```h``` and ```s```, and a range of numbers between ```2``` and ```6```. Remember to include the appropriate flags in the regex.

```javascript
let quoteSample = "Blueberry 3.141592653s are delicious.";
let myRegex = /[h-s2-6]/ig; // Change this line
let result = quoteSample.match(myRegex); // Change this line
```

### Match Single Characters Not Specified

Create a single regex that matches all characters that are not a number or a vowel. Remember to include the appropriate flags in the regex.

```javascript
let quoteSample = "3 blind mice.";
let myRegex = /[^aeiou0-9]/ig; // Change this line
let result = quoteSample.match(myRegex); // Change this line
```

### Match Characters that Occur One or More Times

You want to find matches when the letter ```s``` occurs one or more times in ```Mississippi```. Write a regex that uses the ```+``` sign.

```javascript
let difficultSpelling = "Mississippi";
let myRegex = /s+/ig; // Change this line
let result = difficultSpelling.match(myRegex);
```

### Match Characters that Occur Zero or More Times

For this challenge, ```chewieQuote``` has been initialized as the string ```Aaaaaaaaaaaaaaaarrrgh!``` behind the scenes. Create a regex ```chewieRegex``` that uses the ```*``` character to match an uppercase ```A``` character immediately followed by zero or more lowercase ```a``` characters in ```chewieQuote```. Your regex does not need flags or character classes, and it should not match any of the other quotes.

```javascript
let chewieRegex = /Aa*/; // Change this line
// Only change code above this line

let result = chewieQuote.match(chewieRegex);
```

### Find Characters with Lazy Matching


Fix the regex ```/<.*>/``` to return the HTML tag ```<h1>``` and not the text ```"<h1>Winter is coming</h1>"```. Remember the wildcard ```.``` in a regular expression matches any character.