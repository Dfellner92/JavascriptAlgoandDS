### Sum all numbers in a range

We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them. The lowest number will not always come first.

For example, `sumAll([4,1])` should return `10` because sum of all the numbers between 1 and 4 (both inclusive) is `10`.

```javascript
function sumAll(arr) {
  arr.sort((a, b) => {
    return a - b;
  });
  let arrInit = arr[0];
  let total = 0;
  while (arrInit <= arr[1]) {
    total += arrInit;
    arrInit++;
  }
  return total;
}

console.log(sumAll([10, 5]));
```

### Spinal Tap Case

Convert a string to spinal case. Spinal case is all-lowercase-words-joined-by-dashes.

```javascript
function spinalCase(str) {
  return str
    .replaceAll(/([a-z])([A-Z])/g, "$1 $2")
    .replaceAll(/[_ ]/g, "-")
    .toLowerCase();
}
```

### Sum all Primes

```javascript
function sumPrimes(num) {
  let index = 1;
  let sumArray = [];
  let primes = [];
  let sum = 0;
  while (index <= num) {
    sumArray.push(index);
    index++;
  }
  sumArray.forEach((number) => {
    let i = 1;
    let arr = [];
    while (i <= number) {
      if (number % i === 0) {
        arr.push(i);
      }
      i++;
    }
    if (arr.length === 2) {
      primes.push(number);
    }
  });
  primes.forEach((number) => (sum += number));
  return sum;
}

console.log(sumPrimes(10));
```

### Search and Replace

Perform a search and replace on the sentence using the arguments provided and return the new sentence.

First argument is the sentence to perform the search and replace on.

Second argument is the word that you will be replacing (before).

Third argument is what you will be replacing the second argument with (after).

```javascript
function myReplace(str, before, after) {
  let newStr = str.split(" ");
  let upperRegex = /[A-Z]/;
  let isBeforeCapitalized = upperRegex.test(before[0]);
  let isAfterCapitalized = upperRegex.test(after[0]);
  for (let i = 0; i < newStr.length; i++) {
    if (isBeforeCapitalized && newStr[i] === before) {
      let first = after.slice(0, 1).toUpperCase();
      let rest = after.slice(1);
      newStr[i] = first + rest;
    } else if (isAfterCapitalized && newStr[i] === before) {
      let first = after.slice(0, 1).toLowerCase();
      let rest = after.slice(1);
      newStr[i] = first + rest;
    } else if (newStr[i] === before) {
      newStr[i] = after;
    }
  }
  return newStr.join(" ");
}

console.log(myReplace("I think we should look up there", "up", "Down"));
```

### Diff Two Arrays

Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

```javascript
function diffArray(arr1, arr2) {
  let newArr = [];
  arr1.forEach((element) =>
    arr2.includes(element) ? newArr : newArr.push(element)
  );
  arr2.forEach((element) =>
    arr1.includes(element) ? newArr : newArr.push(element)
  );
  return newArr;
}

console.log(
  diffArray(
    ["andesite", "grass", "dirt", "pink wool", "dead shrub"],
    ["diorite", "andesite", "grass", "dirt", "dead shrub"]
  )
);
```

### Missing Letters

Find the missing letter in the passed letter range and return it.

If all letters are present in the range, return `undefined`.

```javascript
function fearNotLetter(str) {
  let alphabet = [
    "a",
    "b",
    "c",
    "d",
    "e",
    "f",
    "g",
    "h",
    "i",
    "j",
    "k",
    "l",
    "m",
    "n",
    "o",
    "p",
    "q",
    "r",
    "s",
    "t",
    "u",
    "v",
    "w",
    "x",
    "y",
    "z",
  ];
  let lowerStr = str.toLowerCase().split("");
  let inc = alphabet.indexOf(lowerStr[0]);
  for (let i = 0; i < lowerStr.length; i++) {
    if (alphabet[inc] === lowerStr[i]) {
      inc++;
    } else {
      return alphabet[inc];
    }
  }
  return undefined;
}

console.log(fearNotLetter("stvwx"));
```

### Sorted Union

Write a function that takes two or more arrays and returns a new array of unique values in the order of the original provided arrays.

```javascript
function uniteUnique(arr) {
  let newArr = [...arr];
  for (let i = 1; i < arguments.length; i++) {
    arguments[i].forEach((elem) =>
      newArr.includes(elem) ? newArr : newArr.push(elem)
    );
  }
  return newArr;
}

console.log(uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]));
```

### Drop it

Given the array `arr`, iterate through and remove each element starting from the first element (the 0 index) until the function `func` returns `true` when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise, `arr` should be returned as an empty array.

```javascript
function dropElements(arr, func) {
  let elem = 0;
  let ind = false;
  for (let i = 0; i < arr.length; i++) {
    if (func(arr[i]) === true) {
      elem = elem += i;
      ind = true;
      break;
    }
  }

  return ind ? arr.slice(elem) : [];
}

console.log(
  dropElements([1, 2, 3], function (n) {
    return n > 0;
  })
);
```

### Convert HTML

Convert the characters `&`, `<`, `>`, `"` (double quote), and `'` (apostrophe), in a string to their corresponding HTML entities.

```javascript
function convertHTML(str) {
  let newStr = str;
  if (str.includes("&")) {
    newStr = newStr.replaceAll("&", "&amp;");
  }
  if (str.includes("<")) {
    newStr = newStr.replaceAll("<", "&lt;");
  }
  if (str.includes(">")) {
    newStr = newStr.replaceAll(">", "&gt;");
  }
  if (str.includes("'")) {
    newStr = newStr.replaceAll("'", "&apos;");
  }
  if (str.includes('"')) {
    newStr = newStr.replaceAll('"', "&quot;");
  }
  return newStr;
}

console.log(convertHTML("<>"));
console.log(convertHTML("Hamburgers < Pizza < Tacos"));
```

### Binary Agents

Return an English translated sentence of the passed binary string. The binary string will be space separated.

```javascript
function binaryAgent(str) {
  const cipher = {
    "01100001": "a",
    "01100010": "b",
    "01100011": "c",
    "01100100": "d",
    "01100101": "e",
    "01100110": "f",
    "01100111": "g",
    "01101000": "h",
    "01101001": "i",
    "01101010": "j",
    "01101011": "k",
    "01101100": "l",
    "01101101": "m",
    "01101110": "n",
    "01101111": "o",
    "01110000": "p",
    "01110001": "q",
    "01110010": "r",
    "01110011": "s",
    "01110100": "t",
    "01110101": "u",
    "01110110": "v",
    "01110111": "w",
    "01111000": "x",
    "01111001": "y",
    "01111010": "z",
    "01000001": "A",
    "01000010": "B",
    "01000011": "C",
    "01000100": "D",
    "01000101": "E",
    "01000110": "F",
    "01000111": "G",
    "01001000": "H",
    "01001001": "I",
    "01001010": "J",
    "01001011": "L",
    "01001100": "L",
    "01001101": "M",
    "01001110": "N",
    "01001111": "O",
    "01010000": "P",
    "01010001": "Q",
    "01010010": "R",
    "01010011": "S",
    "01010100": "T",
    "01010101": "U",
    "01010110": "V",
    "01010111": "W",
    "01011000": "X",
    "01011001": "Y",
    "01011010": "Z",
    "00100000": " ",
    "00100001": "!",
    "00100111": "'",
    "00111111": "?",
  };
  const keys = Object.keys(cipher);
  let arr = [];
  str.split(" ").forEach((unit) => {
    if (keys.includes(unit)) {
      arr.push(cipher[unit]);
    }
  });

  return arr.join("");
}

console.log(
  binaryAgent(
    "01000001 01110010 01100101 01101110 00100111 01110100 00100000 01100010 01101111 01101110 01100110 01101001 01110010 01100101 01110011 00100000 01100110 01110101 01101110 00100001 00111111"
  )
);
```

### Arguments optional

Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

```javascript
function addTogether() {
  let [first, second] = arguments;
  if (typeof first !== "number") {
    return undefined;
  }
  if (second === undefined) {
    return (second) => addTogether(first, second);
  }
  if (typeof second !== "number") {
    return undefined;
  }
  return first + second;
}

console.log(addTogether(2)(7));
```

### Sum All Odd Fibonacci Numbers

Given a positive integer `num`, return the sum of all odd Fibonacci numbers that are less than or equal to `num`.

The first two numbers in the Fibonacci sequence are 1 and 1. Every additional number in the sequence is the sum of the two previous numbers. The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8.

For example, `sumFibs(10)` should return `10` because all odd Fibonacci numbers less than or equal to `10` are 1, 1, 3, and 5.

```javascript
function sumFibs(num) {
  let prevNumber = 0;
  let currNumber = 1;
  let result = 0;
  while (currNumber <= num) {
    if (currNumber % 2 !== 0) {
      result += currNumber;
    }
    currNumber += prevNumber;
    prevNumber = currNumber - prevNumber;
  }

  return result;
}

console.log(sumFibs(75025));
```

### 