# OOPS
>
Object-Oriented Programming is a methodology or paradigm to design a
program using classes and objects. It simplifies the software development
and maintenance by providing some concepts defined below :
#### 1.Inheritance:-
Inheritance is a process in which one object acquires all the properties and
behaviors ofits parent object automatically.
#### 2.Encapsulation:-
Encapsulation is the process of combining data and functions into a single
unit called class. In Encapsulation, the data is not accessed directly; it is
accessed through the functions present inside the class.
#### 3. Abstraction:-
>Abstraction is defined as delivering only essential information to the outer world while masking background details.
#### 4. Polymorphism:-
> Polymorphism is the ability to present the same interface in different forms.
> A real-life example of polymorphism is a person who at the same time can have different characteristics. A man at the same time is a father, a husband, and an employee. So the same person exhibits different behavior in different situations. This is called polymorphism.
>
# Advantage of OOPs over Procedure-oriented programming language
1.OOPs makes development and maintenance easier where as in Procedure-oriented programming language it is not easy to manage if code grows as project size grows.

2.OOPs provide data hiding whereas in Procedure-oriented programming language a global data can be accessed from anywhere.

3.OOPs provide ability to simulate real-world event much more effectively. We can provide the solution of real word problem if we are using the Object-Oriented Programming language.
# Why is C++ a partial oop?
>The C++ programming language is categorized as a partial object-oriented programming language even though it supports OOP concepts, including classes, objects, inheritance, encapsulation, abstraction, and polymorphism.

1) The main function must always be outside the class in C++ and is required. This means that we may do without classes and objects and have a single main function in the application.so Pure OOP has been violated.

2) Global variables are a feature of the C++ programming language that can be accessed by any other object within the program and are defined outside of it. Encapsulation is broken here. Even though C++ encourages encapsulation for classes and objects, it ignores it for global variables.
>
# Class
>
Class is a user-defined data type which defines its properties and its
functions. Class is the only logical representation of the data. For
example, Human being is a class. The body parts of a human being are its
properties, and the actions performed by the body parts are known as
functions. The class does not occupy any memory space till the time an
object is instantiated.
>
# Access specifiers(IMP)
> #### Access Specifiers IMP :  The access specifiers are used to define how functions and variables can be accessed outside the class. There are three types of access specifiers:
>1. Private: Functions and variables declared as private can be accessed only within the same class, and they cannot be accessed outside the class they are declared.
>2. Public: Functions and variables declared under public can be accessed from anywhere.
>3. Protected: Functions and variables declared as protected cannot be accessed outside the class except a child class. This specifier is generally used in inheritance.
# Object:-
>Object is a run-time entity. It is an instance of the class. An object can
represent a person, place or any other item. An object can operate on
both data members and member functions.
>
# Constructer
> Constructor is a special method which is invoked automatically at the time of object creation. It is used to initialize the data members of new objects generally. The constructor in C++ has the same name as class or structure.
### There can be Three types of constructors in C++
>1. Default constructor : Aconstructor which has no argument is known as default constructor. It is invoked at the time of creating an object. 
>2. Parameterized constructor : Constructor which has parameters is called a parameterized constructor. It is used to provide diff erent values to distinct objects.
>3. Copy Constructor : A Copy constructor is an overloaded constructor used to declare and initialize an object from another object. 
It is of two types - default copy constructor and user defined copy constructor.

# Destructer
>● Destructor : Adestructor works opposite to constructor; it destructs the objects of classes. It can be defined only once in a class. Like constructors, it is invoked automatically. Adestructor is defined like a constructor. It must have the same name as class, prefixed with a tilde sign (~).
```

class Rectangle{
    public:
    int l;
    int b;

    //Default constructer-no arguments passed
    Rectangle(){
        l=0;
        b=0;
    }
    //parameterized constructer
    Rectangle(int x,int y){
        l=x;
        b=y;
    }
    
    //copy constructer- initialize an object by existing an another object
    Rectangle(Rectangle &r){
        l=r.l;
        b=r.b;
    }

    //Destructer
    ~Rectangle(){
        cout<<"Destructer is called"<<endl;
    }

};
int main(){
  Rectangle *r1 = new Rectangle();
    cout<<r1->l<<" "<<r1->b<<endl;
    delete r1;

    Rectangle r2(2,3);
    cout<<r2.l<<" "<<r2.b<<endl;

    Rectangle r3(r2); // Reactangle r3=r2;
    cout<<r3.l<<" "<<r3.b<<endl;
}
```
# Encapsulation
>Encapsulation is the process of combining data and functions into a single unit called class. In Encapsulation, the data is not accessed directly; it is accessed through the functions present inside the class. In simpler words, attributes of the class are kept private and public getter and setter methods are provided to manipulate these attributes. Thus, encapsulation makes the concept of data hiding possible.(Data hiding: a language feature to restrict access to members of an object, reducing the negative effect due to dependencies. e.g. "protected", "private" feature in C++).

```
class ABC{
    int x;
    public:
    void set(int n){
        x=n;
    }
    int get(){
        return x;
    }
};
int main(){
    ABC obj1;
    obj1.set(3);
    cout<<obj1.get()<<endl;
}
```
# Abstraction
>Data abstraction is one of the most essential and important features of object-oriented programming in C++. Abstraction means displaying only essential information and hiding the details. Data abstraction refers to providing only essential information about the data to the outside world, hiding the background details or implementation. 

Consider a real-life example of a man driving a car. 

```
// C++ Program to Demonstrate the
// working of Abstraction
#include <iostream>
using namespace std;

class implementAbstraction {
private:
	int a, b;

public:
	// method to set values of
	// private members
	void set(int x, int y)
	{
		a = x;
		b = y;
	}

	void display()
	{
		cout << "a = " << a << endl;
		cout << "b = " << b << endl;
	}
};

int main()
{
	implementAbstraction obj;
	obj.set(10, 20);
	obj.display();
	return 0;
}
```

# Inheritance
Inheritance is a process in which one class/object acquires all the properties and behaviors ofits parent class/object automatically. In such a way, you can reuse, extend or modify the attributes and behaviors which are defined in other classes. 
In C++, the class which inherits the members of another class is called derived class and the class whose members are inherited is called base class. The derived class is the specialized class for the base class.
<h3>visibility-modes = {private, protected, public} </h3>

```

class Parent{

    public:
    int x;

    protected:
    int y;

    private:
    int z;
};
  //inherit kr rhey
class child1: public Parent{
    // x will remain public
    //y will remian protected
    // z will not be accessible
};
class child2: private Parent{
    // x will be private
    // y will be private
    // z will be inaccessible
};
class child3: protected Parent{
    // x will remain protected
    // y will remain protected
    // z will be inaccessible
};

```
<h3>Types of Inheritance :</h3>

> 1. Single inheritance : When one class inherits another class, it is known as single level inheritance

```
class Parent{
    public:
    Parent(){
        cout<<"Parent Class"<<endl;
    }
};
class Child: public Parent{
    public:
    Child(){
        cout<<"child class"<<endl;
    }
};

int main(){
    Child c;
}
```
> 2.Multilevel inheritance : In Multilevel inheritance deriving a class from another derived class.
```
class Parent{
    public:
    Parent(){
        cout<<"Parent Class"<<endl;
    }
};
class Child: public Parent{
    public:
    Child(){
        cout<<"child class"<<endl;
    }
};

class GrandChild: public Child{
    public:
    GrandChild(){
        cout<<"Grand child class"<<endl;
    }
};
int main(){
      GrandChild c;
}
```
> 3. Multiple inheritance : In Multiple inheritance deriving a new class that inherits the attributes from two or more classes(parent class).
```
class Parent1{
    public:
    Parent1(){
        cout<<"Parent1 Class"<<endl;
    }
};
class Parent2{
    public:
    Parent2(){
        cout<<"Parent2 Class"<<endl;
    }
};
class Child: public Parent1, public Parent2{
    public:
    Child(){
        cout<<"child class"<<endl;
    }
};
int main(){
      Child c;
}
```
> 4. Hierarchical inheritance : In Hierarchical inheritance more than one derived class inherit from a base(super) class.
```
class Parent1{
    public:
    Parent1(){
        cout<<"Parent1 Class"<<endl;
    }
};
class Child1: public Parent1{
    public:
    Child1(){
        cout<<"child1 class"<<endl;
    }
};
class Child2: public Parent1{
    public:
    Child2(){
        cout<<"child2 class"<<endl;
    }
};
```
> 5. Hybrid inheritance : Hybrid inheritance is a combination of simple, multiple inheritance and hierarchical inheritance.

### Diamond Problem
> Base class has multiple parent classes having a common ancestor. so base class have will come acncestor properties two times
```
                class F
               /       \
        class E        class D
            |            |
        class C        class B
            \           /
              class A
So, class A have Ancestor F properties will come two times
```
```
class Parent{
    public:
    Parent(){
        cout<<"Parent Class"<<endl;
    }
};

class Child1: public Parent{
    public:
    Child1(){
        cout<<"child1 class"<<endl;
    }
};
class Child2: public Parent{
    public:
    Child2(){
        cout<<"child2 class"<<endl;
    }
};


class GrandChild: public Child1, public Child2{
    public:
    GrandChild(){
        cout<<"Grand child class"<<endl;
    }
};
int main(){
    GrandChild c;
}
Output: Parent Class
        child1 class
        Parent Class
        child2 class
        Grand child class
```
### Polymorphism
> Polymorphism is the ability to present the same interface in different forms.
> A real-life example of polymorphism is a person who at the same time can have different characteristics. A man at the same time is a father, a husband, and an employee. So the same person exhibits different behavior in different situations. This is called polymorphism.
> ##### Types of Polymorphism IMP
>  1. Compile Time Polymorphism (Static)
>  2. Runtime Polymorphism (Dynamic)
>  ![Polymorphism-in-CPP](https://github.com/MohdAqib8267/OOPS/assets/106628860/8bab0cd1-32e8-4f5e-ac1a-b3347f11f928)
>  #### 1. Compile-Time Polymorphism:-
> The polymorphism which is implemented at the compile time is known as compile-time polymorphism.
> Compile-Time Polymorphism is achieved by function overloading or operator overloading.
> ##### A. Function Overloading
>When there are multiple functions with the same name but different parameters, then the functions are said to be overloaded, hence this is known as Function Overloading. Functions can be overloaded by changing the number of arguments or/and changing the type of arguments.
```
class Sum{
    public:
    void add(int x,int y){
        int sum=x+y;
        cout<<sum<<endl;
    }
    void add(int x,int y,int z){
        int sum=x+y+z;
        cout<<sum<<endl;
    }
    void add(float x,float y){
        float sum=x+y;
        cout<<sum<<endl;
    }
};
int main(){
     Sum s;
    s.add(2,3);
    s.add(2,3,4);
    s.add(float(1.2),float(2.7));
}
Output: 5
        9
        3.9
```
> #### B. Operator Overloading
> C++ has the ability to provide the operators with a special meaning for a data type, this ability is known as operator overloading.
> For example, a single operator ‘+’, when placed between integer operands, adds them and when placed between string operands, concatenates them.
```
class Complex{
    public:
    int real;
    int img;
    Complex(int x,int y){
        real=x;
        img=y;
    }
    Complex operator+ (Complex &c){
        Complex ans(0,0);
        ans.real=real+c.real;
        ans.img=img+c.img;
        return ans;
    }
};
int main(){
    Complex c1(2,3);
    Complex c2(3,4);

    Complex c3=c1+c2;
    cout<<c3.real<<" i"<<c3.img<<endl;

}
```
> ### 2. Runtime Polymorphism
> Resolved at runtime.
> Runtime polymorphism is also known as dynamic polymorphism.
> This is acheived by Function overriding
> #### A. Function Overriding
> Function overriding means when the child class contains the method which is already present in the parent class. Hence, the child class overrides the method of the parent class. In case offunction overriding, parent and child classes both contain the same function with a diff erent definition.
```
class GFG_Base {
 
public:
    // virtual function
    virtual void display()
    {
        cout << "Called virtual Base Class function"
             << "\n\n";
    }
 
    void print()
    {
        cout << "Called GFG_Base print function"
             << "\n\n";
    }
};
class GFG_Child : public GFG_Base {
 
public:
    void display()
    {
        cout << "Called GFG_Child Display Function"
             << "\n\n";
    }
 
    void print()
    {
        cout << "Called GFG_Child print Function"
             << "\n\n";
    }
};
int main(){
     GFG_Base* base;
    GFG_Child child;
    base = &child;  // base ko child assign kiya
    base->display(); // base ke print me virtual lgaya h isliye wo override hp jayega child wale se
    base->print();
}
```
# Difference between compile time polymorphism vs run time polymorphism
| compile time polymorphism  | run time polymorphism |
| ----------------------------------------------------------- | ------------- |
|1.Acheived by function overloading and operator overloading  | Acheived by Function overriding.  |
|2.Implemented at compile time   | Implemented at run-time  |
|3.Functions name should be same but params canbe different   | Function names and params should be same  |
|4.Fast execution time   | slow execution time  |  |4.More memory effective   | Less memory effective  |

> Sometimes implementation of all functions cannot be provided in a base class because we don’t know the implementation. Such a class is called an abstract class.For example, let Shape be a base class. We cannot provide the implementation of function draw() in Shape, but we know every derived class must have an implementation of draw().

or
(A class that contains a pure virtual function is known as an abstract class)
```
// C++ program to calculate the area of a square and a circle

#include <iostream>
using namespace std;

// Abstract class
class Shape {
   protected:
    float dimension;

   public:
    void getDimension() {
        cin >> dimension;
    }

    // pure virtual Function
    virtual float calculateArea() = 0;
};

// Derived class
class Square : public Shape {
   public:
    float calculateArea() {
        return dimension * dimension;
    }
};

// Derived class
class Circle : public Shape {
   public:
    float calculateArea() {
        return 3.14 * dimension * dimension;
    }
};

int main() {
    Square square;
    Circle circle;

    cout << "Enter the length of the square: ";
    square.getDimension();
    cout << "Area of square: " << square.calculateArea() << endl;

    cout << "\nEnter radius of the circle: ";
    circle.getDimension();
    cout << "Area of circle: " << circle.calculateArea() << endl;

    return 0;
}
```

# Friend Function
> A friend function can be a special access to private and protected members of a class in C++. They are the non-member functions that can access and manipulate the private and protected members of the class for they are declared as friends.
```
class A{
    private:
    int x;
    protected:
    int z;
    public:
    A(int p,int q){
        x=p;
        z=q;
    }
    friend void print(A &obj);

};

void print(A &obj){
    cout<<obj.x<<endl;
    cout<<obj.z<<endl;
}
int main(){
 A obj(5,4);
//  cout<<obj.x<<endl;  //give error but using frient function work done.

print(obj);
}
```
# Static Binding and Dynamic Binding

The process of matching a specific function call to its respective function definition is known as binding.

There are two types of binding:
* Static Binding (also known as Early Binding).
* Dynamic Binding (also known as Late Binding).
### Static Binding 
Binding at compile time is known as static binding. Here it directly associates an address to the function call.This is achieved by using Function overloading or operator overloading.
For function overloading it is an example of early binding.

```
#include<iostream>
using namespace std;
class Base {
   public:
   void display() {
      cout<<" In Base class" <<endl;
   }
};
class Derived: public Base {
   public:
   void display() {
      cout<<"In Derived class" << endl;
   }
};
int main(void) {
   Base *base_pointer = new Derived;
   base_pointer->display();
   return 0;
}
****OUTPUT: In Base class
```
### Dynamic Binding
Binding at run time is known as Dynamic Binding. In this type of binding the compiler adds code that identifies the object type at runtime then matches the call with the right function definition. This is achieved by using virtual function.
```
#include<iostream>
using namespace std;
class Base {
   public:
   virtual void display() {
      cout<<"In Base class" << endl;
   }
};
class Derived: public Base {
   public:
   void display() {
      cout<<"In Derived class" <<endl;
   }
};
int main() {
   Base *base_pointer = new Derived;
   base_pointer->display();
   return 0;
}
**** OUTPUT: In Derived class
```
# Java Garbage Collection
<b>Java garbage collection is the process by which Java programs perform automatic memory management.</b>

Java programs compile to bytecode that can be run on a Java Virtual Machine, or JVM for short. When Java programs run on the JVM, objects are created on the heap, which is a portion of memory dedicated to the program. Eventually, some objects will no longer be needed. The garbage collector finds these unused objects and deletes them to free up memory.
# What Is an Exception?
The term exception is shorthand for the phrase "exceptional event."
#### Definition:  An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions during the execution of a program.
When an error occurs within a method, the method creates an object and hands it off to the runtime system. The object, called an exception object, contains information about the error, including its type and the state of the program when the error occurred. Creating an exception object and handing it to the runtime system is called throwing an exception.

After a method throws an exception, the runtime system attempts to find something to handle it. The set of possible "somethings" to handle the exception is the ordered list of methods that had been called to get to the method where the error occurred. The list of methods is known as the call stack (see the next figure).
![exceptions-callstack](https://github.com/MohdAqib8267/OOPS/assets/106628860/ea785121-2a3f-4989-becd-b7562aa9e98a)

The runtime system searches the call stack for a method that contains a block of code that can handle the exception. This block of code is called an exception handler. The search begins with the method in which the error occurred and proceeds through the call stack in the reverse order that the methods were called. When an appropriate handler is found, the run-time system passes the exception to the handler. An exception handler is considered appropriate if the type of the exception object thrown matches the type that can be handled by the handler. The exception handler chosen is said to catch the exception. If the runtime system exhaustively searches all the methods on the call stack without finding an appropriate exception handler, as shown in the next figure, the runtime system (and, consequently, the program) terminates.
![exceptions-errorOccurs](https://github.com/MohdAqib8267/OOPS/assets/106628860/5653296a-95cb-49c8-9ead-b127c1f8571e)

# ● ‘this’ Pointer :
>this is a keyword that refers to the current instance of the class. There can be 3 main uses of‘this’ keyword:
>1. It can be used to pass the current object as a parameter to another method
>2. It can be used to refer to the current class instance variable.
>3. It can be used to declare indexers.
#### C++ Syntax : 
```
struct node{
    int data;
    node *next;
     node(int x){
    this->data = x;
    this->next = NULL;
    }
 }
```
