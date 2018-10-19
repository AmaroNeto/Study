# Prototype Design Pattern

## What is the Prototype Pattern?

* Creating new objects (instances) by cloning (copying) other objects.
* Allows for adding of any subclass instance of a known super class at run time.
* When there are numerous potential classes that you want to only use if needed at runtime.
* Reduces the need for creating subcalsses.

## Example

```java
    public interface Animal extends Clonable {
        public Animal makeCopy();
    }
```

```java
    public class Sheep implements Animal {
        public Sheep() {}

        public Animal makeCopy() {
            Sheep sheepObject = null;

            try { 
                sheepObject = (Sheep) super.clone();
            } catch (CloneNotSupportedException e) {
                e.printStackTrace();
            }

            return sheepObject;
        }
    }
```

```java
    public class CloneFactory {
        public Animal getClone(Animal animalSample) {
            return animalSample.makeCopy();
        }
    }
```

