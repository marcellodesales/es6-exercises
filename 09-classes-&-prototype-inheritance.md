# Classes & Prototype Inheritance

1. Create a class `Airplane` (or even `Aeroplane`).
   Add a constructor that initializes this plane's `make` (manufacturer)
  `model`, `speed` and `altitude`.

```javascript
class Airplane {
  constructor(make, model, speed, altitude) {
    this.make = make;
    this.model = model;
    this.speed = speed;
    this.altitude = altitude;
  }
}

export default Airplane;
```

2. Add a method `showPlane()` to display these attributes.

```javascript
class Airplane {
  constructor(make, model, speed, altitude) {
    this.make = make;
    this.model = model;
    this.speed = speed;
    this.altitude = altitude;
  }

  showPlane() {
    return `This is a ${this.make} airplane model ${this.model} that goes ${this.speed}`;
  }
}

export default Airplane;
```

3. Instantiate an object of this class, say a Boeing 747, and
   call its `showPlane()` method.

```javascript
import Airplane from './model/airplane.js'

const myAirplane = new Airplane("Boing", "747", "750/MPH", "1000F")
console.log(`${myAirplane.showPlane()}`)
```

4. Create a base class, `FlyingVehicle`, and have your `Airplane`
   extend from it.
   1. Add a constructor.
   2. Refactor your classes to pull the `speed` and `altitude` properties up to the base class.
   3. Instantiate a new `Airplane`, ensuring that both its constructor and the superclass constructor get called.
   4. Add a method to the base class that returns `FlyingVehicle`s speed and altitude as a string. Modify `Airplane`'s '`showPlane()` method to use this string in its output.

```javascript
class FlyingVehicle {
  constructor(speed, altitude) {
    this.speed = speed;
    this.altitude = altitude;
  }

  showSpecs() {
    return `Speed is ${this.speed} in altitudes of ${this.altitude}`;
  }
}

export default FlyingVehicle;


///--------------------------------

import FlyingVehicle from './FlyingVehicle'

class Airplane extends FlyingVehicle {

  constructor(make, model, speed, altitude) {
    super(speed, altitude);
    this.make = make;
    this.model = model;
  }

  showPlane() {
    return `This is a ${this.make} airplane model ${this.model} with ${this.showSpecs()}`;
  }
}

export default Airplane;

//------------------------

const myAirplane = new Airplane("Boing", "747", "750/MPH", "1000F")

console.log(`${myAirplane.showPlane()}`)
```

5. Create a `Helicopter` class that extends `FlyingVehicle`.
   1. Instantiate a new Helicopter.
   2. Add a `static` method to `Helicopter` that returns an array of flight controls, namely (1) the cyclic, (2) the collective, (3) the anti-torque pedals, and (4) the throttle. Ensure you can return this list without instantiating an object of the class. Can you call it from an instance?

```javascript
import FlyingVehicle from './FlyingVehicle'

class Helicopter extends FlyingVehicle {

  static getFlightControls() {
    return ["cyclic", "collective", "anti-torque pedals", "throttle"];
  }
}

export default Helicopter;

//--------

import Helicopter from './model/Helicopter'


There is a new Flying object with {Helicopter.getFlightControls()}

```
