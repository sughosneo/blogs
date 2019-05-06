### OOP design pattern in - Python language ?

This is one of the another article in "do I know ?" series. Where we would see different important
object oriented design patten details and it's possible implementation.



Creational Patterns
-------------------------------------

- ***`Singleton Pattern`*** [Ref](https://www.geeksforgeeks.org/singleton-design-pattern/) =>
    
    - It returns only one object for all set of call. 
    - There is always a doubt of can create real singleton in python ?
    - **Ans** - https://stackoverflow.com/questions/55860871/restricting-creation-of-object-in-a-singleton-class-using-constructor-in-python 
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/singleton
    
- ***`Factory Pattern`*** [Ref](https://www.geeksforgeeks.org/design-patterns-set-2-factory-method/) =>
    
    - Below example also shows how different object gets created
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/factory

- ***`Abstract Factory Pattern`*** [Ref]() =>

- ***`NULL Object Pattern`*** [Ref](https://www.geeksforgeeks.org/null-object-design-pattern/) =>
    
    - Instead of using repetitive NULL object check we can use this Null object pattern during creation of object.      
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/null

Structural Patterns
-------------------------------------

- ***`Adapter Pattern`*** [Ref](https://www.geeksforgeeks.org/adapter-pattern/) =>
    
    - Adapter pattern lets you wrap an otherwise incompatible object in an adapter to make it compatible with another class.
    - Adapter pattern works as a bridge between two incompatible interfaces
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/adapter
    
- ***`Decorator Pattern`*** [Ref](https://www.geeksforgeeks.org/decorators-in-python/) =>
    
    - Decorating one function call without making any code changes.
    - There are 2 types of it - function and class decorator    
    
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/decorator

- ***`Facade Pattern`*** [Ref](https://sourcemaking.com/design_patterns/facade/python/1) =>
    - Facade pattern provides a simplified interface to a complex subsystem.
    - One good example would be "When a computer starts up, it involves the work of cpu, memory, 
        hard drive, etc. To make it easy to use for users, we can add a facade which wrap the complexity of the task, and provide one simple interface instead."
        
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/facade


Behavioral Patterns
-------------------------------------

- ***`Observer Pattern`*** [Ref](https://sourcemaking.com/design_patterns/observer/python/1) =>
    
    - Define a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
    - This pattern is useful event driven programming to notify the state changed to multiple objects.
    - Implementation : https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/observer

- ***`Strategy Pattern`*** [Ref]() =>
    

References 
-----------------------

[1] : https://medium.com/educative/the-7-most-important-software-design-patterns-d60e546afb0e

[2] : https://github.com/jackdbd/design-patterns

[3] : https://python-3-patterns-idioms-test.readthedocs.io/en/latest/ 

[4] : https://www.u-cursos.cl/usuario/f133dab21b6cbf814b4607124f431358/mi_blog/r/head_first_design_patterns.pdf

[5] : https://hackernoon.com/10-oop-design-principles-every-programmer-should-know-f187436caf65
