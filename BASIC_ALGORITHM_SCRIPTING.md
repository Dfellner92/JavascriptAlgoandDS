# Basic Algorithm Scripting, my answers

### Convert Celsius to Fahrenheit

You are given a variable `celsius` representing a temperature in Celsius. Use the variable `fahrenheit` already defined and assign it the Fahrenheit temperature equivalent to the given Celsius temperature. Use the algorithm mentioned above to help convert the Celsius temperature to Fahrenheit.

```javascript
function convertToF(celsius) {
  let fahrenheit = (celsius * 9) / 5 + 32;
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
  let longestWord = "";
  for (let i = 0; i < stringArr.length; i++) {
    if (stringArr[i].length > longestWord.length) {
      longestWord = stringArr[i];
    }
  }
  return longestWord.length;
}

console.log(
  findLongestWordLength("The quick brown fox jumped over the lazy dog")
);
```

### Return Largest Numbers in Arrays

Return an array consisting of the largest number from each provided sub-array.

```javascript
function largestOfFour(arr) {
  let results = [];
  for (let i = 0; i < arr.length; i++) {
    let largestNumber = arr[i][0];
    for (let j = 1; j < arr[i].length; j++) {
      if (arr[i][j] > largestNumber) {
        largestNumber = arr[i][j];
      }
    }
    results[i] = largestNumber;
  }

  return results;
}

console.log(
  largestOfFour([
    [4, 5, 1, 3],
    [13, 27, 18, 26],
    [32, 35, 37, 39],
    [1000, 1001, 857, 1],
  ])
);
```

### Confirm the Ending

Check if a string (first argument, `str`) ends with the given target string (second argument, `target`).

This challenge can be solved with the `.endsWith()` method, which was introduced in ES2015. But for the purpose of this challenge, we would like you to use one of the JavaScript substring methods instead.

```javascript
function confirmEnding(str, target) {
  if (str.substring(str.length - target.length) == target) {
    return true;
  } else {
    return false;
  }
}

confirmEnding("Bastian", "n");
```

### Repeat a String Repeat a String

Repeat a given string `str` (first argument) for `num` times (second argument). Return an empty string if `num` is not a positive number. For the purpose of this challenge, do not use the built-in `.repeat()` method.

```javascript
function repeatStringNumTimes(str, num) {
  if (num <= 0) {
    return "";
  } else {
    str = str + repeatStringNumTimes(str, num - 1);
  }
  return str;
}

console.log(repeatStringNumTimes("abc", 3));
```

### Truncate a String

Truncate a string (first argument) if it is longer than the given maximum string length (second argument). Return the truncated string with a `...` ending.

```javascript
function truncateString(str, num) {
  if (str.slice(0, num) == str) {
    return str;
  } else {
    return str.slice(0, num) + "...";
  }
}

console.log(truncateString("A-tisket a-tasket A green and yellow basket", 8));
```

### Finders Keepers

Create a function that looks through an array `arr` and returns the first element in it that passes a 'truth test'. This means that given an element `x`, the 'truth test' is passed if `func(x)` is `true`. If no element passes the test, return `undefined`.

```javascript
function findElement(arr, func) {
  for (let i = 0; i < arr.length; i++) {
    if (func(arr[i])) {
      return arr[i];
    }
  }
}

console.log(findElement([1, 2, 3, 4], (num) => num % 2 === 0));
```

### Boo who

Check if a value is classified as a boolean primitive. Return `true` or `false`.

```javascript
function booWho(bool) {
  if (bool === true || bool === false) {
    return true;
  } else {
    return false;
  }
}

console.log(booWho(null));
```

### Title Case a Sentence

Return the provided string with the first letter of each word capitalized. Make sure the rest of the word is in lower case.

```javascript
function titleCase(str) {
  let strArr = str.split(" ");
  let strArr2 = [];
  for (let i = 0; i < strArr.length; i++) {
    strArr2.push(strArr[i][0].toUpperCase() + strArr[i].slice(1).toLowerCase());
  }
  return strArr2.join(" ");
}

console.log(titleCase("I'm a little tea pot"));
```

### Slice and Splice

You are given two arrays and an index.

Copy each element of the first array into the second array, in order.

Begin inserting elements at index `n` of the second array.

Return the resulting array. The input arrays should remain the same after the function runs.

```javascript
function frankenSplice(arr1, arr2, n) {
  let arr3 = [...arr2];
  arr3.splice(n, 0, ...arr1);
  return arr3;
}

console.log(frankenSplice([1, 2, 3], [4, 5, 6], 1));
```

### Falsy Bouncer

Remove all falsy values from an array.

Falsy values in JavaScript are `false`, `null`, `0`, `""`, `undefined`, and `NaN`.

Hint: Try converting each value to a Boolean.

```javascript
function bouncer(arr) {
  let newArr = [];
  for (let i = 0; i < arr.length; i++) {
    if (arr[i]) {
      newArr.push(arr[i])
    }
  }
  return newArr;
}

console.log(bouncer([false, null, 0, NaN, undefined, ""]));
```

### Where do I Belong

Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

```javascript
function getIndexToIns(arr, num) {
  let zip = [];
  arr.sort((a, b) => {
    return a - b
  })
  for (let i = 0; i < arr.length; i++) {
   if (arr[arr.length - 1] < num) {
      return arr.length;
    } else if (arr[i] < num && arr[i + 1] >= num ) {
      return i + 1;
    }
  }
  return zip.length;
}

console.log(getIndexToIns([], 1));
```

### Chunky Monkey

Write a function that splits an array (first argument) into groups the length of ```size``` (second argument) and returns them as a two-dimensional array.

```javascript
function chunkArrayInGroups(arr, size) {
  let newArr = [];
  for (let i = 0; arr.length; i++) {
    newArr.push(arr.splice(0, size));
  }
  return newArr;
}

console.log(chunkArrayInGroups([0, 1, 2, 3, 4, 5], 2));
```