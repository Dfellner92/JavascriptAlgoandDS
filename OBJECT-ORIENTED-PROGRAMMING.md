### Use Prototype Properties to Reduce Duplicate Code

Add a ```numLegs``` property to the ```prototype``` of ```Dog```

```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

// Only change code above this line
let beagle = new Dog("Snoopy");
```

### Iterate Over All Properties

Add all of the own properties of ```beagle``` to the array ```ownProps```. Add all of the ```prototype``` properties of ```Dog``` to the array ```prototypeProps```.

```javascript 
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

let beagle = new Dog("Snoopy");

let ownProps = [];
let prototypeProps = [];

// Only change code below this line
for (let property in beagle) {
  if (beagle.hasOwnProperty(property)) {
    ownProps.push(property);
  } else {
    prototypeProps.push(property);
  }
}
```

### Understand the Constructor Property

Write a ```joinDogFraternity``` function that takes a ```candidate``` parameter and, using the ```constructor``` property, return ```true``` if the candidate is a ```Dog```, otherwise return ```false```.

```javascript
function Dog(name) {
  this.name = name;
}

// Only change code below this line
function joinDogFraternity(candidate) {
  if (candidate.constructor === Dog) {
    return true;
  } else {
    return false;
  }
```
