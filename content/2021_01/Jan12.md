---
title: Java 225
date: 2020-01-12 11:54
modified: 2020-01-12 11:54
category: programming
tags: sfu, cmpt225
Authors: Nathan Esau
---

I am no stranger to Java.

But that doesn't mean that I like Java.

My computer science course will be using Java. I can't say I'm surprised:

* Java is popular in enterprise software (I used Java myself for about 6 months last year, primarily for writing Web APIs and command line tools)

* Java is also popular in general (ex. Android development)

* Java courses are a good way to teach Object Oriented Programming, which is a powerful way to write large, scalable applications

But... it's not Python. It's not C++. And it's not Rust. *Hint: I like those languages better*

My first computer science lecture is a Java review. I guess I'll write a bit of code here for my reference.

Here is the Main class.

```java
// Main.java
import java.util.List;
import java.util.ArrayList;
import java.util.Random;
import animals.Animal;
import animals.AnimalFactory;

class Main {

    public static void main(String[] args) {

        AnimalFactory factory = new AnimalFactory();
        List<Animal> animalList = new ArrayList();
        for(int i = 0; i < 5; i++) {
            Animal animal = factory.getRandomAnimal();
            animalList.add(animal);
        }

        for(Animal animal : animalList) {
            System.out.println(animal + " says ");
            System.out.println(animal.makeSound());
        }
    }
}
```

...and then the Animal factory:

```java
// AnimalFactory.java
package animal;

import animal.Animal;
import animal.Cow;
import animal.Dog;

public class AnimalFactory {

    public Animal getRandomAnimal() {

        Random rand = new Random();
        switch(r.nextInt(3)) {
            case 0:
				return new Cow("Pink", "name" + r.nextInt(10), r.nextInt(200));
			case 1:
				return new Dog("Spaniel", "Blue", "name" + r.nextInt(100));
			case 2:
				return new Dog("Shepherd", "Gold", "name" + r.nextInt(100));
        }
        return null;
    }
}
```

...and the Animal interface (yes, every class needs to be in its own file):

```java
// Animal.java
package animal;

public interface Animal {

    public String makeSound();
}
```

and then the Cow class:

```java
// Cow.java
package animal;

public class Cow implements Animal {

    protected static final String color;

    protected static final String name;

    protected static final int weight;

    public Cow(String color, String name, int weight) {
        this.color = color;
        this.name = name;
        this.weight = weight;
    }

    @Override
    public String makeSound() {
        return "moo";
    }

    public String toString() {
        return String.format("Cow: Color = %s, Name = %s, Weight = %d", color, name, weight);
    }
}
```

and then the Dog class:

```java
// Dog.java
package animal;

public class Dog implements Animal {

    protected static final String breed;

    protected static final String color;

    protected static final String name;

    public Dog(String color, String name, int weight) {
        this.color = color;
        this.name = name;
        this.weight = weight;
    }

    @Override
    public String makeSound() {
        return "woof-woof";
    }

    public String toString() {
        return String.format("Dog: Breed = %s, Color = %s, Name = %s", breed, color, name);
    }
}
```

I guess that's basically it for this post.
