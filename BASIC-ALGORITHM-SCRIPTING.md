# Basic Algorithm Scripting, my answers

### Convert Celsius to Fahrenheit

You are given a variable ```celsius``` representing a temperature in Celsius. Use the variable ```fahrenheit``` already defined and assign it the Fahrenheit temperature equivalent to the given Celsius temperature. Use the algorithm mentioned above to help convert the Celsius temperature to Fahrenheit.

```javascript
function convertToF(celsius) {
  let fahrenheit = celsius * 9/5 + 32;
  return fahrenheit;
}

convertToF(30);
```

### Reverse a String

Reverse the provided string.

You may need to turn the string into an array before you can reverse it.

Your result must be a string.

```javascript
function reverseString(str) {
  return str.split("").reverse().join("");
}

reverseString("hello");
```

### Factorialize a number

Return the factorial of the provided integer.

```javascript
function factorialize(num) {
  if (num == 0) {
    return 1;
  } else {
    return num * factorialize(num - 1);
  }
}

factorialize(5);
```

### Find the Longest Word in a String

Return the length of the longest word in the provided sentence.

```javascript 
function findLongestWordLength(str) {
  let stringArr = str.split(" ");
  let longestWord = '';
  for (let i = 0; i < stringArr.length; i++) {
    if (stringArr[i].length > longestWord.length) {
      longestWord = stringArr[i];
    } 
  }
  return longestWord.length; 
}

console.log(findLongestWordLength("The quick brown fox jumped over the lazy dog"));
```

