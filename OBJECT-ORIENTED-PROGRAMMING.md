### Use Prototype Properties to Reduce Duplicate Code

Add a `numLegs` property to the `prototype` of `Dog`

```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype.numLegs = 4;

// Only change code above this line
let beagle = new Dog("Snoopy");
```

### Iterate Over All Properties

Add all of the own properties of `beagle` to the array `ownProps`. Add all of the `prototype` properties of `Dog` to the array `prototypeProps`.

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

Write a `joinDogFraternity` function that takes a `candidate` parameter and, using the `constructor` property, return `true` if the candidate is a `Dog`, otherwise return `false`.

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

### Change the Prototype to a New Object

Add the property `numLegs` and the two methods `eat()` and `describe()` to the `prototype` of `Dog` by setting the `prototype` to a new object.

```javascript
function Dog(name) {
  this.name = name;
}

Dog.prototype = {
  // Only change code below this line
  numLegs: 4,
  eat: function () {
    console.log("eating");
  },
  describe: function () {
    console.log("four legged");
  },
};
```

### Remember to Set the Constructor Property when Changing the Prototype

Define the constructor property on the Dog prototype.

```javascript
function Dog(name) {
  this.name = name;
}

// Only change code below this line
Dog.prototype = {
  constructor: Dog,
  numLegs: 4,
  eat: function () {
    console.log("nom nom nom");
  },
  describe: function () {
    console.log("My name is " + this.name);
  },
};
```

### Understand Where an Object's Prototype Comes From

Use `isPrototypeOf` to check the `prototype` of `beagle`.

```javascript
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");

// Only change code below this line

Dog.prototype.isPrototypeOf(beagle);
```

### Understand the Prototype Chain

Modify the code to show the correct prototype chain

```javascript
function Dog(name) {
  this.name = name;
}

let beagle = new Dog("Snoopy");

Dog.prototype.isPrototypeOf(beagle); // yields true

// Fix the code below so that it evaluates to true
console.log(Object.prototype.isPrototypeOf(Dog.prototype));
```

### Use Inheritance So You Don't Repeat Yourself

The `eat` method is repeated in both `Cat` and `Bear`. Edit the code in the spirit of DRY by moving the `eat` method to the `Animal` `supertype`.

```javascript
function Animal(name) {
  this.name = name;
}

Animal.prototype = {
  constructor: Animal,
  eat: function () {
    console.log("nom nom nom");
  },
};

function Bear(name) {
  this.name = name;
}

Bear.prototype = {
  constructor: Animal,
};

function Cat(name) {
  this._name = name;
}

Cat.prototype = {
  constructor: Animal,
};
```

### Inherit Behaviors from a Supertype

Use `Object.create` to make two instances of `Animal` named `duck` and `beagle`.

```javascript
function Animal() {}

Animal.prototype = {
  constructor: Animal,
  eat: function () {
    console.log("nom nom nom");
  },
};

// Only change code below this line

let duck = Object.create(Animal.prototype); // Change this line
let beagle = Object.create(Animal.prototype); // Change this line
```

### Set the Child's Prototype to an Instance of the Parent

Modify the code so that instances of `Dog` inherit from `Animal`.

```javascript
function Animal() {}

Animal.prototype = {
  constructor: Animal,
  eat: function () {
    console.log("nom nom nom");
  },
};

function Dog() {}

// Only change code below this line
Dog.prototype = Object.create(Animal.prototype);

let beagle = new Dog();
beagle.eat();
```

### Reset an Inherited Constructor Property

Fix the code so `duck.constructor` and `beagle.constructor` return their respective constructors.

```javascript
function Animal() {}
function Bird() {}
function Dog() {}

Bird.prototype = Object.create(Animal.prototype);
Dog.prototype = Object.create(Animal.prototype);

// Only change code below this line

Bird.prototype.constructor = Bird;
Dog.prototype.constructor = Dog;

let duck = new Bird();
let beagle = new Dog();
```

### Add Methods After Inheritance

Add all necessary code so the `Dog` object inherits from `Animal` and the `Dog`'s `prototype` constructor is set to `Dog`. Then add a `bark()` method to the `Dog` object so that `beagle` can both `eat()` and `bark()`. The `bark()` method should print `Woof!` to the console.

```javascript
function Animal() {}
Animal.prototype.eat = function () {
  console.log("nom nom nom");
};

function Dog() {}

// Only change code below this line

Dog.prototype = Object.create(Animal.prototype);
Dog.prototype.constructor = Dog;

Dog.prototype.bark = function () {
  console.log("Woof!");
};

let beagle = new Dog();
beagle.eat();
beagle.bark();
```

### Override Inherited Methods

Override the `fly()` method for `Penguin` so that it returns the string `Alas, this is a flightless bird.`

```javascript
function Bird() {}

Bird.prototype.fly = function () {
  return "I am flying!";
};

function Penguin() {}
Penguin.prototype = Object.create(Bird.prototype);
Penguin.prototype.constructor = Penguin;

// Only change code below this line

Penguin.prototype.fly = function () {
  return "Alas, this is a flightless bird.";
};

// Only change code above this line

let penguin = new Penguin();
console.log(penguin.fly());
```

### Use a Mixin to Add Common Behavior Between Unrelated Objects

Create a mixin named `glideMixin` that defines a method named `glide`. Then use the `glideMixin` to give both `bird` and `boat` the ability to glide.

```javascript
let bird = {
  name: "Donald",
  numLegs: 2,
};

let boat = {
  name: "Warrior",
  type: "race-boat",
};

// Only change code below this line

let glideMixin = function (obj) {
  obj.glide = function () {
    console.log("gliding!");
  };
};
glideMixin(bird);
glideMixin(boat);

console.log(boat.glide(), bird.glide());
```

### Use Closure to Protect Properties Within an Object from Being Modified Externally

Change how `weight` is declared in the `Bird` function so it is a private variable. Then, create a method `getWeight` that returns the value of `weight` 15.

```javascript
function Bird() {
  let weight = 15;

  this.getWeight = function () {
    return weight;
  };
}

let robin = new Bird();
console.log(robin.getWeight());
```

### Understand the Immediately Invoked Function Expression (IIFE)

Rewrite the function `makeNest` and remove its call so instead it's an anonymous immediately invoked function expression (IIFE).

```javascript
(function () {
  console.log("A cozy nest is ready");
})();
```

### Use an IIFE to Create a Module

Create a module named `funModule` to wrap the two mixins `isCuteMixin` and `singMixin`. `funModule` should return an object.

```javascript
let funModule = (function () {
  return {
    isCuteMixin: function (obj) {
      obj.isCute = function () {
        return true;
      };
    },
    singMixin: function (obj) {
      obj.sing = function () {
        console.log("Singing to an awesome tune");
      };
    },
  };
})();
```
