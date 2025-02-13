# OOPS-in-C-

# 🚀 Object-Oriented Programming (OOP) in C++

This repository contains examples and explanations of **Object-Oriented Programming (OOP) concepts in C++**.

## 📌 Topics Covered
- Object Creation (Stack vs. Heap)
- Constructors & Destructors
- Encapsulation & Abstraction
- Inheritance (Types & Examples)
- Diamond Problem & Virtual Inheritance
- Polymorphism (Compile-time & Run-time)
- Function & Operator Overloading
- Method Overriding
- Friend Functions
- Use of `const` in C++

---

## 📌 1. Object Creation: Stack vs Heap
C++ allows object creation in two ways:

| Feature        | Stack Allocation | Heap Allocation (`new`) |
|---------------|----------------|--------------------|
| **Memory Location** | Stack         | Heap             |
| **Lifetime**      | Automatic (destroyed when out of scope) | Manual (must use `delete`) |
| **Performance**   | Faster        | Slightly slower   |
| **Syntax**       | `ClassName obj;` | `ClassName* obj = new ClassName();` |

📌 **Use Stack Allocation** for temporary objects.  
📌 **Use Heap Allocation** when objects need to persist across multiple function calls.

---

## 📌 2. Constructors & Destructors
**Constructor:** Special function that initializes an object.  
**Destructor:** Cleans up when an object goes out of scope.

```cpp
class Example {
public:
    Example() { cout << "Constructor Called\n"; }
    ~Example() { cout << "Destructor Called\n"; }
};
📌 3. Inheritance in C++
C++ supports different types of inheritance:

Type	Description
Single	One class inherits from another.
Multiple	A class inherits from multiple base classes.
Multilevel	Grandparent → Parent → Child.
Hierarchical	Multiple classes inherit from a single base class.
Hybrid	Combination of two or more types.
📌 Example: Single Inheritance

cpp
Copy
Edit
class Animal {
public:
    void eat() { cout << "Eating...\n"; }
};

class Dog : public Animal {
public:
    void bark() { cout << "Barking...\n"; }
};

int main() {
    Dog d;
    d.eat();  // Inherited
    d.bark(); // Own method
}
📌 4. Diamond Problem & Virtual Inheritance
When a class inherits from two classes that share a common base class, ambiguity arises.
Solution: Use virtual inheritance.

cpp
Copy
Edit
class A { public: void show() { cout << "Class A\n"; } };
class B : virtual public A {};
class C : virtual public A {};
class D : public B, public C {};

int main() {
    D obj;
    obj.show();  // No ambiguity
}
📌 5. Polymorphism
Types:

Compile-time Polymorphism (Function & Operator Overloading)
Run-time Polymorphism (Method Overriding using Virtual Functions)
📌 Function Overloading Example

cpp
Copy
Edit
class Math {
public:
    int add(int a, int b) { return a + b; }
    double add(double a, double b) { return a + b; }
};
📌 Method Overriding Example (Using Virtual Functions)

cpp
Copy
Edit
class Parent {
public:
    virtual void show() { cout << "Parent class\n"; }
};

class Child : public Parent {
public:
    void show() override { cout << "Child class\n"; }
};

int main() {
    Parent* p = new Child();
    p->show();  // Calls Child's show()
}
📌 6. Operator Overloading (Adding Complex Numbers)
Operator overloading allows user-defined types to use operators like +.

cpp
Copy
Edit
class Complex {
public:
    int real, imag;
    Complex(int r, int i) : real(r), imag(i) {}

    Complex operator+(const Complex& c) {
        return Complex(real + c.real, imag + c.imag);
    }

    void display() { cout << real << " + " << imag << "i\n"; }
};

int main() {
    Complex c1(2, 3), c2(4, 5);
    Complex c3 = c1 + c2;
    c3.display();  // Output: 6 + 8i
}
📌 7. Friend Function (Accessing Private Members)
A friend function is not a class member but can access private data.

cpp
Copy
Edit
class Sample {
private:
    int num;
public:
    Sample(int n) : num(n) {}

    friend void display(const Sample& s);
};

void display(const Sample& s) {
    cout << "The number is: " << s.num << endl;
}
📌 8. Use of const in C++
const prevents modification of variables or methods.

cpp
Copy
Edit
class Demo {
private:
    int data;
public:
    Demo(int d) : data(d) {}

    void show() const {  // Const function
        cout << "Data: " << data << endl;
    }
};
📌 Contributions 🤝
Feel free to fork this repository and contribute with improvements, examples, and explanations!

📌 License 📝
This project is open-source and available under the MIT License.

yaml
Copy
Edit

---

## **📌 Next Steps**
- **Save this file as `README.md`.**
- **Push it to your GitHub repository.**

Let me know if you need **changes, additions, or formatting improvements**! 🚀
