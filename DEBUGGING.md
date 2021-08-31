# Debugging

### Use the JavaScript Console to Check the Value of a Variable

Use the ```console.log()``` method to print the value of the variable ```a``` where noted in the code.

```javascript

let a = 5;
let b = 1;
a++;
// Only change code below this line

let sumAB = a + b;
console.log(sumAB);
```

### Understanding the Differences between the freeCodeCamp and Browser Console

First, use ```console.log()``` to log the ```output``` variable. Then, use ```console.clear()``` to clear the browser console.

```javascript 


```

### Use typeof to Check the Type of a Variable

Add two ```console.log()``` statements to check the ```typeof``` each of the two variables ```seven``` and ```three``` in the code.

```javascript
let seven = 7;
let three = "3";
console.log(seven + three);
// Only change code below this line
console.log(typeof(seven));
console.log(typeof(three));
```

### Catch Misspelled Variable and Function Names

Fix the two spelling errors in the code so the ```netWorkingCapital``` calculation works.

```javascript
let receivables = 10;
let payables = 8;
let netWorkingCapital = receivables - payables;
console.log(`Net working capital is: ${netWorkingCapital}`);
```

### Catch Unclosed Parentheses, Brackets, Braces and Quotes

Fix the two pair errors in the code.

```javascript
let myArray = [1, 2, 3];
let arraySum = myArray.reduce((previous, current) =>  previous + current);
console.log(`Sum of array values is: ${arraySum}`);
```

### Catch Mixed Usage of Single and Double Quotes

Fix the string so it either uses different quotes for the ```href``` value, or escape the existing ones. Keep the double quote marks around the entire string.

```javascript
let innerHtml = "<p>Click here to <a href='#Home'>return home</a></p>";
console.log(innerHtml);
```

### Catch Use of Assignment Operator Instead of Equality Operator

Fix the condition so the program runs the right branch, and the appropriate value is assigned to ```result```.

```javascript
let x = 7;
let y = 9;
let result = "to come";

if(x == y) {
  result = "Equal!";
} else {
  result = "Not equal!";
}

console.log(result);
```

