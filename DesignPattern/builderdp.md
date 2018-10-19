# Builder Pattern

## What is Builder Pattern?

1. Pattern used to create objects made from a bunch of other objects.

* When you want to build an object made up from other objects
* When you want the creation of these parts to be independent of main object
* Hide the creation of the parts from the client so both aren't dependent
* The builder knows the specifics and nobody else does

2. You can think in Builder Pattern when you need create class with optional params, so with Builder you can send just the params that you need.

## Example

```java
    public class House {
        private String door;
        private String windows;
        private String floor;
        private String wall;

        public House() {}

        public House(String windows, String wall) { ... }

        //Sets and Gets
    }
```
If you have a object _House_ and your params are optionals or can be dinamics you can create a builder for him.

```java
    public class HouseBuilder {

        private House house;

        public HouseBuilder() {
            house = new House();
        }

        public void addWindows(String windows) {
            house.setWindows(windows);
        }

        public void addDoor(String door) {
            house.setWindows(door);
        }

        public void addFloor(String floor) {
            house.setWindows(floor);
        }

        public void addWall(String wall) {
            house.setWall(wall);
        }

        public House create() {
            return this.house;
        }

    }
```