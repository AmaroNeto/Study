# Factory Pattern

## What is the factory pattern?

1. When a method returns one of several possible classes that share a common super class.

* Create a new enemy in a game.
* Random number generatior picks a number assigned to a specific enemy.
* The factory returns the enemy associated with that number.

2. The class is chosen at run time.

## When to use a factory pattern?

1. When you don't know ahead of time what class object you need.
2. When all of the potential classes are in the same subclass hierarchy.
3. To centralize class selection code.
4. when you don't want the user to have to know every subclass.
5. to encapsulate object creation.

### Example

1. Have a generic class __Animal__;

```java
    public class Animal {
        String name;
        String family;
    }
``` 
2. and two class that define a specific kind of animal:

```java
    public class Dog extends Animal {
        public Dog() {
            super.name = "Dog";
            super.family = "canine";
        }
    }

    public class Cat extends Animal {
        public Cat() {
            super.name = "Cat";
            super.family = "feline";
        }
    }
```

1. With a factory you can put the choice logic select a specific animal.

```java
    public class AnimalFactory {

        public Animal create(String family) {
            if(family.equals("feline")) {
                return new Cat();
            } else if (family.equals("canine")) {
                return new Dog();
            } else {
                return null;
            }
        }
    }
```