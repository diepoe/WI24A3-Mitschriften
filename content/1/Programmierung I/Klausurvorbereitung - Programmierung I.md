
> [!question] [Quizzes](https://questioneer.azurewebsites.net)

## Übungsaufgaben
1. https://silhding.github.io/2020/04/05/java/
2. https://silhding.github.io/2020/04/13/java2/
3. https://silhding.github.io/2020/04/17/java3/

---
# Objektorientierung
## Encapsulation
==Kapselung== bedeutet, dass Objektdetails vor der Außenwelt verborgen und nur über definierte Schnittstellen zugänglich gemacht werden. Dies schützt die Daten und kontrolliert den Zugriff.
### Beispiel
```java
public class BankAccount {
    // Private Variablen können nur innerhalb der Klasse direkt zugegriffen werden
    private double balance;
    private String accountNumber;

    // Öffentliche Methoden erlauben kontrollierten Zugriff
    public void deposit(double amount) {
        // Validierung vor der Änderung des Kontostands
        if (amount > 0) {
            balance += amount;
        }
    }

    public double getBalance() {
        // Kontrollierter Zugriff auf den Kontostand
        return balance;
    }
}
```
## Abstraction
==Abstraktion== bedeutet, komplexe Implementierungsdetails zu verbergen und nur die wesentlichen Merkmale eines Objekts zu zeigen.
### Beispiel
```java
// Abstrakte Klasse definiert ein Grundmuster für Fahrzeuge
public abstract class Vehicle {
    // Abstrakte Methode, die von Unterklassen implementiert werden muss
    public abstract void move();

    // Gemeinsame Methode für alle Fahrzeuge
    public void startEngine() {
        System.out.println("Engine started");
    }
}

// Konkrete Implementierung
public class Car extends Vehicle {
    @Override
    public void move() {
        System.out.println("Car is driving");
    }
}
```
## Inheritance
==Vererbung== ermöglicht es, Eigenschaften und Methoden von einer Klasse an eine andere weiterzugeben.
### Beispiel
```java
public class Animal {
    protected String name;

    public void eat() {
        System.out.println(name + " is eating");
    }
}

public class Dog extends Animal {
    public Dog(String name) {
        // Zugriff auf Elternklassen-Attribut
        this.name = name;
    }

    // Zusätzliche spezifische Methode
    public void bark() {
        System.out.println(name + " is barking");
    }
}
```
## Polymorphism
==Polymorphie== erlaubt es, dass Objekte unterschiedlich auf die gleiche Methode reagieren können.
### Beispiel
```java
public interface Shape {
    // Polymorphe Methode zur Berechnung der Fläche
    double calculateArea();
}

public class Circle implements Shape {
    private double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}

public class Rectangle implements Shape {
    private double width;
    private double height;

    public Rectangle(double width, double height) {
        this.width = width;
        this.height = height;
    }

    @Override
    public double calculateArea() {
        return width * height;
    }
}

// Demonstration der Polymorphie
public class Main {
    public static void printArea(Shape shape) {
        System.out.println("Fläche: " + shape.calculateArea());
    }

    public static void main(String[] args) {
        Shape circle = new Circle(5);
        Shape rectangle = new Rectangle(4, 6);

        // Gleiche Methode, verschiedene Implementierungen
        printArea(circle);     // Berechnet Kreisfläche
        printArea(rectangle);  // Berechnet Rechteckfläche
    }
}
```