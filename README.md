# OOPS
oops Notes
<hr/>

# Inheritance
Inheritance is a process in which one class/object acquires all the properties and behaviors ofits parent class/object automatically. In such a way, you can reuse, extend or modify the attributes and behaviors which are defined in other classes. In C++, the class which inherits the members of another class is called derived class and the class whose members are inherited is called base class. The derived class is the specialized class for the base class.
<h3>visibility-modes = {private, protected, public} </h3>
<h3>Types ofInheritance :</h3>
1. Single inheritance : When one class inherits another class, it is known as single level inheritance
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
```

2. Multiple inheritance : Multiple inheritance is the process of deriving a new class that inherits the attributes from two or more classes. 3. Hierarchical inheritance : Hierarchical inheritance is defined as the process of deriving more than one class from a base class. 4. Multilevel inheritance : Multilevel inheritance is a process of deriving a class from another derived class. 5. Hybrid inheritance : Hybrid inheritance is a combination of simple, multiple inheritance and hierarchical inheritance

