Sure, let's dive into Object-Oriented Programming (OOP) in C++.

### **Introduction to Object-Oriented Programming (OOP)**

OOP is a programming paradigm that uses "objects" to model real-world things and their interactions. The four main principles of OOP are Encapsulation, Abstraction, Inheritance, and Polymorphism.

### **1. Classes and Objects**

- **Class**: A blueprint for creating objects (a particular data structure).
- **Object**: An instance of a class.

#### Example:
```cpp
#include <iostream>
using namespace std;

class Car {
public:
    string brand;
    string model;
    int year;

    void displayInfo() {
        cout << "Brand: " << brand << endl;
        cout << "Model: " << model << endl;
        cout << "Year: " << year << endl;
    }
};

int main() {
    Car car1;
    car1.brand = "Toyota";
    car1.model = "Corolla";
    car1.year = 2020;

    car1.displayInfo();

    return 0;
}
```

### **2. Encapsulation**

Encapsulation means bundling the data (variables) and methods (functions) that operate on the data into a single unit, a class. It also involves restricting access to some of the object's components.

#### Example:
```cpp
#include <iostream>
using namespace std;

class Person {
private:
    string name;
    int age;

public:
    void setName(string n) {
        name = n;
    }

    string getName() {
        return name;
    }

    void setAge(int a) {
        age = a;
    }

    int getAge() {
        return age;
    }
};

int main() {
    Person person1;
    person1.setName("Alice");
    person1.setAge(25);

    cout << "Name: " << person1.getName() << endl;
    cout << "Age: " << person1.getAge() << endl;

    return 0;
}
```

### **3. Inheritance**

Inheritance allows a class to inherit properties and behavior (methods) from another class. The class being inherited from is called the "base class," and the class that inherits is called the "derived class."

#### Example:
```cpp
#include <iostream>
using namespace std;

class Animal {
public:
    void eat() {
        cout << "Eating..." << endl;
    }
};

class Dog : public Animal {
public:
    void bark() {
        cout << "Barking..." << endl;
    }
};

int main() {
    Dog dog1;
    dog1.eat();
    dog1.bark();

    return 0;
}
```

### **4. Polymorphism**

Polymorphism means "many forms," and it allows methods to do different things based on the object it is acting upon. There are two types: compile-time (function overloading and operator overloading) and runtime (method overriding).

#### Example of Function Overloading:
```cpp
#include <iostream>
using namespace std;

class Print {
public:
    void display(int i) {
        cout << "Integer: " << i << endl;
    }

    void display(double f) {
        cout << "Float: " << f << endl;
    }

    void display(string s) {
        cout << "String: " << s << endl;
    }
};

int main() {
    Print print;
    print.display(5);
    print.display(3.14);
    print.display("Hello, World!");

    return 0;
}
```

#### Example of Method Overriding:
```cpp
#include <iostream>
using namespace std;

class Base {
public:
    virtual void show() {
        cout << "Base class" << endl;
    }
};

class Derived : public Base {
public:
    void show() override {
        cout << "Derived class" << endl;
    }
};

int main() {
    Base* b;
    Derived d;
    b = &d;

    b->show();

    return 0;
}
```

### **5. Abstraction**

Abstraction means hiding the complex implementation details and showing only the essential features of the object.

#### Example:
```cpp
#include <iostream>
using namespace std;

class AbstractCar {
public:
    virtual void start() = 0; // Pure virtual function
    virtual void stop() = 0;  // Pure virtual function
};

class SportsCar : public AbstractCar {
public:
    void start() override {
        cout << "Sports car starting..." << endl;
    }

    void stop() override {
        cout << "Sports car stopping..." << endl;
    }
};

int main() {
    SportsCar myCar;
    myCar.start();
    myCar.stop();

    return 0;
}
```

### Summary

1. **Classes and Objects**: Create classes and instantiate objects.
2. **Encapsulation**: Keep data safe from outside interference and misuse.
3. **Inheritance**: Derive new classes from existing ones.
4. **Polymorphism**: Use the same interface for different underlying forms (data types).
5. **Abstraction**: Hide complex implementation details and show only the necessary features.

By understanding these core principles and practicing with examples, you'll be well on your way to mastering OOP in C++.