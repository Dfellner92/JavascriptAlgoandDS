# Basic Data Structures

### Iterate Through All an Array's Items Using For Loops

We have defined a function, ```filteredArray```, which takes ```arr```, a nested array, and ```elem``` as arguments, and returns a new array. ```elem``` represents an element that may or may not be present on one or more of the arrays nested within ```arr```. Modify the function, using a ```for``` loop, to return a filtered version of the passed array such that any array nested within ```arr``` containing ```elem``` has been removed.

```javascript
function filteredArray(arr, elem) {
  let newArr = [];
  // Only change code below this line
  for (let i = 0; i < arr.length; i++) {
    if (!arr[i].includes(elem)) {
      newArr.push(arr[i]);
    }
  }
  // Only change code above this line
  return newArr;
}

console.log(filteredArray([[3, 2, 3], [1, 6, 3], [3, 13, 26], [19, 3, 9]], 3));

// expected return = [];
```

### Create complex multi-dimensional arrays

We have defined a variable, ```myNestedArray```, set equal to an array. Modify ```myNestedArray```, using any combination of strings, numbers, and booleans for data elements, so that it has exactly five levels of depth (remember, the outer-most array is level 1). Somewhere on the third level, include the string ```deep```, on the fourth level, include the string ```deeper```, and on the fifth level, include the string ```deepest```.

```javascript
let myNestedArray = [
  // Only change code below this line
  ['unshift', false, 1, 2, 3, 'complex', 'nested'],
  ['loop', 'shift', ['deep', ['deeper', ['deepest']]], 6, 7, 1000, 'method'],
  ['concat', false, true, 'spread', 'array'],
  ['mutate', 1327.98, 'splice', 'slice', 'push'],
  ['iterate', 1.3849, 7, '8.4876', 'arbitrary', 'depth']
  // Only change code above this line
];
```

### Add Key-Value Pairs to JavaScript Objects

A ```foods``` object has been created with three entries. Using the syntax of your choice, add three more entries to it: ```bananas``` with a value of ```13```, grapes with a value of ```35```, and ```strawberries``` with a value of ```27```.

```javascript
```