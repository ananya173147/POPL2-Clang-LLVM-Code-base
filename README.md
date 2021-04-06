## CS232: POPL2


## Mini Assignment 2: Large Code Bases and OOP

Ananya Mantravadi

CS19B1004


### Introduction

The LLVM Project is a collection of modular and reusable compiler and toolchain technologies. Clang is not only a C, C++, Objective-C, or Objective-C++ compiler that is compiled in C++ based on LLVM, but also an infrastructure to build tools. Clang uses a recursive-descent parser. It is mainly used for better performance than GCC.


### C++11/C++14 features used



*   Use of auto keyword for automatic type detection
*   Use of nullptr in place of 0 or NULL
*
![alt_text](images/image1.png "image_tooltip")

    This is a new version of the range-based for loop that iterates over all elements of a TemplateIds.

*   
![alt_text](images/image2.png "image_tooltip")

    Usage of std::unique_ptr, as a replacement for std::auto_ptr

*  
![alt_text](images/image3.png "image_tooltip")
    Use of lambdas, which allow the definition of inline functions, working as a parameter or a local object.

*  
![alt_text](images/image4.png "image_tooltip")
    Use of static_cast for conversions from pointers to related classes, implicit conversions, etc. which is a compile-time cast.

*  
![alt_text](images/image5.png "image_tooltip")
    Use of enum classes that makes enumerations both strongly typed and strongly scoped.

*   
![alt_text](images/image6.png "image_tooltip")

    Use of constexpr for computations at compile-time instead of run-time.

*  
![alt_text](images/image7.png "image_tooltip")


    Use of static_assert which performs compile-time assertion checking

*   
![alt_text](images/image8.png "image_tooltip")


    Use of ‘=default;’ specifier at the end of a function to declare it as an explicitly defaulted function.

*   
![alt_text](images/image9.png "image_tooltip")


    Use of fixed-width integer types such as unit64_t (unsigned integer type with width of exactly 16 bits)



### Class hierarchy

The following link contains the class hierarchy from [LLVM doxygen documentation](https://llvm.org/doxygen/) which is a useful source of information about the LLVM source base - [https://llvm.org/doxygen/inherits.html](https://llvm.org/doxygen/inherits.html)


### OOP design decisions for LLVM



*   Inheritance: It is a process in which one object acquires all the properties and behaviors of its parent object automatically. 

    

![alt_text](images/image10.png "image_tooltip")


*   Multiple inheritance: Classes inheriting from more than one concrete class

    

![alt_text](images/image11.png "image_tooltip")


*   [Virtual Methods](https://llvm.org/docs/CodingStandards.html#provide-a-virtual-method-anchor-for-classes-in-headers): If a class is defined in a header file and has a vtable (either it has virtual methods or it derives from classes with virtual methods), it always has at least one out-of-line virtual method in the class. Many methods are virtual, and some of them are pure virtual.
*   Modularity: A major design concept for clang is its use of a library-based architecture to be modular. Each compilation phase consists of multiple modules. This approach leads to well-defined interfaces, good abstraction and makes the code more readable. Modularity is also achieved using namespaces with enums, enum classes, and anonymous namespaces.


![alt_text](images/image12.png "image_tooltip")
Ex of anonymous namespace


### Design Patterns

The following design patterns are incorporated into Clang/LLVM source code:

*   Factory Method Pattern: It provides an interface for creating an object, but lets subclasses decide which class to instantiate. It is useful to isolate the logic instantiation and enforces the cohesion.
*   Abstract Factory Pattern: It provides an interface for creating families of related or dependent objects without specifying their concrete classes.
*   Observer pattern: It defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
*   Visitor pattern: It lets you define a new operation without changing the classes of the elements on which it operates.
*   Low Coupling:  It can be achieved by using abstract classes, generic types, and methods and is desirable since changes in one area will require fewer changes throughout the entire application.

![alt_text](images/image13.png "image_tooltip")



### Usage of iterators and their own data structures


### References:



*   [https://github.com/llvm/llvm-project](https://github.com/llvm/llvm-project)
*   [https://llvm.org/docs/CodingStandards.html#provide-a-virtual-method-anchor-for-classes-in-headers](https://llvm.org/docs/CodingStandards.html#provide-a-virtual-method-anchor-for-classes-in-headers)
*   [https://cppdepend.com/blog/?p=92](https://cppdepend.com/blog/?p=92)
*   [https://llvm.org/doxygen/](https://llvm.org/doxygen/)
*   [https://en.wikipedia.org/wiki/Design_Patterns](https://en.wikipedia.org/wiki/Design_Patterns)
