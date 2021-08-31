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
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28
};

// Only change code below this line
foods.bananas = 13;
foods['grapes'] = 35;
const favFood = 'strawberries';
foods[favFood] = 27;
// Only change code above this line

console.log(foods);
```
### Modify an Object Nested Within an Object

Here we've defined an object ```userActivity```, which includes another object nested within it. Set the value of the ```online``` key to ```45```.

```javascript
let userActivity = {
  id: 23894201352,
  date: 'January 1, 2017',
  data: {
    totalUsers: 51,
    online: 42
  }
};

// Only change code below this line
userActivity.data.online = 45;
// Only change code above this line

console.log(userActivity);
```

### Access Property Names with Bracket Notation

We've defined a function, ```checkInventory```, which receives a scanned item as an argument. Return the current value of the ```scannedItem``` key in the ```foods``` object. You can assume that only valid keys will be provided as an argument to ```checkInventory```.

```javascript
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
};

function checkInventory(scannedItem) {
  // Only change code below this line
  if (foods[scannedItem]) {
    return foods[scannedItem];
  }
  // Only change code above this line
}

console.log(checkInventory("apples"));
```

### Use the delete Keyword to Remove Object Properties

Use the delete keyword to remove the ```oranges```, ```plums```, and ```strawberries``` keys from the ```foods``` object.

```javascript
let foods = {
  apples: 25,
  oranges: 32,
  plums: 28,
  bananas: 13,
  grapes: 35,
  strawberries: 27
};

// Only change code below this line
delete foods.oranges;
delete foods.plums;
delete foods.strawberries;
// Only change code above this line

console.log(foods);
```

### Check if an Object has a Property

Finish writing the function so that it returns true if the object passed to it contains all four names, ```Alan```, ```Jeff```, ```Sarah``` and ```Ryan``` and returns false otherwise.

```javascript
let users = {
  Alan: {
    age: 27,
    online: true
  },
  Jeff: {
    age: 32,
    online: true
  },
  Sarah: {
    age: 48,
    online: true
  },
  Ryan: {
    age: 19,
    online: true
  }
};

function isEveryoneHere(userObj) {
  // Only change code below this line
  if (userObj.hasOwnProperty('Alan') &&
    userObj.hasOwnProperty('Jeff') &&
    userObj.hasOwnProperty('Sarah') &&
    userObj.hasOwnProperty('Ryan')
  ) {
    return true;
  } else {
    return false;
  }
  // Only change  above this line
}

console.log(isEveryoneHere(users));
```

### Iterate Through the Keys of an Object with a for...in Statement


We've defined a function ```countOnline``` which accepts one argument (a users object). Use a for...in statement within this function to loop through the users object passed into the function and return the number of users whose ```online``` property is set to ```true```. An example of a users object which could be passed to ```countOnline``` is shown below. Each user will have an ```online``` property with either a ```true``` or ```false``` value.code

```javascript
function countOnline(usersObj) {
  // Only change code below this line
  let result = 0;
  for (let user in usersObj) {
    if (usersObj[user].online === true) {
      result++;
    }
  }
  return result;
  // Only change code above this line
}
```

### Generate an Array of All Object Keys with Object.keys()

Finish writing the ````getArrayOfUsers``` function so that it returns an array containing all the properties in the object it receives as an argument.


