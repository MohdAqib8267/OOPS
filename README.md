# OOPS
<hr/>
# Inheritance
Inheritance is a process in which one class/object acquires all the properties and behaviors ofits parent class/object automatically. In such a way, you can reuse, extend or modify the attributes and behaviors which are defined in other classes. 
In C++, the class which inherits the members of another class is called derived class and the class whose members are inherited is called base class. The derived class is the specialized class for the base class.
<h3>visibility-modes = {private, protected, public} </h3>
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
