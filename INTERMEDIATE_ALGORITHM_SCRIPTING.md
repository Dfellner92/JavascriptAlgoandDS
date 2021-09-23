### Sum all numbers in a range

We'll pass you an array of two numbers. Return the sum of those two numbers plus the sum of all the numbers between them. The lowest number will not always come first.

For example, ```sumAll([4,1])``` should return ```10``` because sum of all the numbers between 1 and 4 (both inclusive) is ```10```.

```javascript
function sumAll(arr) {
  arr.sort((a, b) => {
    return a - b
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

### Diff Two Arrays

Compare two arrays and return a new array with any items only found in one of the two given arrays, but not both. In other words, return the symmetric difference of the two arrays.

```javascript
function diffArray(arr1, arr2) {
  var newArr = [];
  for (let i = 0; i < arr1.length; i++) {
    if (arr2.indexOf(arr1[i]) === -1) {
      newArr.push(arr1[i]);
    }
    }
    for (let j = 0; j < arr2.length; j++) {
      if (arr1.indexOf(arr2[j]) === -1) {
      newArr.push(arr2[j]);
    }
  }
  return newArr;
}

console.log(diffArray(["andesite", "grass", "dirt", "pink wool", "dead shrub"], ["diorite", "andesite", "grass", "dirt", "dead shrub"]));
```

### Drop it

Given the array ```arr```, iterate through and remove each element starting from the first element (the 0 index) until the function ```func``` returns ```true``` when the iterated element is passed through it.

Then return the rest of the array once the condition is satisfied, otherwise, ```arr``` should be returned as an empty array.

```javascript
function dropElements(arr, func) {
  let elem = 0;
  let ind = false;
  for (let i = 0; i < arr.length; i++) {
    if (func(arr[i]) === true) {
      elem = elem += i;
      ind = true;
      break;
    }; 
  };
  
  return ind ? arr.slice(elem) : [];

}

console.log(dropElements([1, 2, 3], function(n) {return n > 0;}));
```