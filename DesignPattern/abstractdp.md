# Abstract Pattern

## Whats is the Abstract Factory Pattern?

1. It is like a factory, but everything is encapsulated
* The method that orders the object
* The factories that build the object
* The final objects
* The final objects contain objects that use the Strategy Pattern
    * Composition: Object class fields are objects

## What can you do with an Abstract Factory?

* Allows you to create families of related objects without specifying a concrete class.
* Use when you have many objects that can be added, or changed dynamically during runtime.
* You can model anything you can imagine and have those objects interact through common interfaces.
* The Bad: Things can get complicated.

## Example

You create a abstract class that work like a factory, but to implement the class is necessary define the methods.

```java

    public abstract class Manufacturer() {
        public abstract Wheel getWheel();
        public abstract Glass getGlass();
        public abstract Door getDoor();
        public abstract Motor getMotor();

        public Car createCar() {
            List<Wheel> wheels = new ArraysList<>();
            List<Glass> glasses = new ArrayList<>();
            List<Door> doors = new ArrayList<>();
            Motor motor;

            Car car = new Car();

            for(int i = 0; i < 4; i++) {
                car.addWheel(getWheel());
                car.addGlass(getGlass());
                car.addDoor(getDoor());
                car.addMotor(getMotor());
            }

            return car;
        }
    }
```

Now you need implements the abstract class and abstract methods.

```java
    public class FordManufacturer extends Manufacturer {
        public Wheel getWheel() { return new FordWhell() };
        public Glass getGlass() { return new FordGlass() };
        public Door getDoor() { return new FordDoor() };
        public Motor getMotor() { return new FordMotor() };
    }
```

the advantage of Abstract Factory:

```java
    public class ProductionLine () {

        private List<Employee> employees;

        public ProductionLine() {
            employees = new ArrayList<>();
            ...
        }

        public Car createCar() {
            Employee employee = employees.get(0);
            employee.startProcess(fordManufacturer.createCar());
        }
    }
```
source: [Youtube](https://www.youtube.com/watch?v=xbjAsdAK4xQ&index=6&list=PLF206E906175C7E07)