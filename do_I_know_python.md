### Python topic(s) - Do I know Python ?

This study note possibly consolidates all the relevant python topics which someone should refer to for gaining
a detailed knowledge about python as programming language. This list is primarily focused on **python3.x**. But some of the concepts 
are also applicable in **python2.x** as well.

***Note : - This is still in making, I would try to include reference for individual topic
for ease of study***.

## Basic
________________________________________________________________________________________________

- ***`Installing **Python 3.x**`*** => on Windows,Linux

- ***`Primitive Types`*** => int,float,bool

- ***`Null Value`*** => **None**

- ***`Relational Operators`*** => (!=,==,<,>,<=,=>,is)

- ***`Conditional Statements`*** => if, elif, else

- ***`Loops`*** => for,while

- ***`Strings`*** => Declares as **str**

- ***`Everything is Object`*** [Ref](https://mail.python.org/pipermail/python-list/2015-June/691689.html) =>
   - In Python, "everything is an object" (that is, all values are objects)
     is because Python does not include any primitive unboxed values. Anything
     which can be used as a value (int, str, float, functions, modules, etc) are
    implemented as objects.
    - Below snippet show if you declare a class even that's also an object where specific memory reference is shown by **id()** function
    
        ```python
            >>> class Foo(object): pass
            >>> id(Foo)
            142630324
        ```        
   
- ***`Mutable and Immutable Objects`*** =>

- ***`Passing argument to function`*** [Ref](https://www.python-course.eu/passing_arguments.php) =>
    - When we pass the argument to a function it's not liked pass by value or
    -   it's directly pass by reference. It's more like pass by object.
    - For the scalar immutable object it never gets modified. For the mutable objects it gets changed unitl local name gets referenced.
 
- ***`Different predefined data structures in python`*** => 
    - Tuples        
    - List
    - Dictionary
    - Set [Ref](https://www.youtube.com/watch?v=MEPlLAjPvXY)
     
    ```python
     
      mySet = {1,'abc',2,7.8}
      #or#
      myCustomSet = set([1,'abc',2,7.8])
       
      # It doesn't have indexing concept like list. 
      # You can't slice one set. 
      # You can't access one value of a set using it's index number but you can loop through the elements.
      # You would always need to have unique element in sets. You can't have duplicates items.
  
    ```
        
    
- ***`Iterate through a collections`*** =>
    - Range
    - Using **for (each) in (any collections)**
    
- ***`Comprehensions`*** =>
    - List
    - Set
    - Dictionary
    
- ***`Iterable and Iterator`*** => 
    - iterate through the objects to fetch result
    - use of **next()** to fetch value.
        
- ***`Generators`*** [Ref](https://www.geeksforgeeks.org/generators-in-python/) => is a function that returns an object which we can iterate over.    
    - all generators are iterators
    - are lazily evaluated
    - looks like functions
    - yield result        
    
- ***`Defining functions`*** =>
    - with ***def*** statement.
    
- ***`Writing "Hello World"`*** => with **print()**
 
- ***`Docstrings`*** => Documenting python code.

- ***`Shebang`*** => 
    - (#!/usr/bin/env python3) let's script know which interpretor to choose
     
- ***`Importing module`*** => with **import** statement

- ***`Absolute import Vs Relative import`*** [Ref](https://www.youtube.com/watch?v=rehzDVnmhes) =>
    - Relative import is standardized approach.

- ***`Python Execution model`*** [Ref](https://docs.python.org/3/reference/executionmodel.html) => 
    - How does a python script run ?    

- ***`Difference between`*** =>
    - Python Module
    - Python Script
    - Python Program
    - Python Package     

- ***`Modularity in python`*** =>
    - Defining functions 
    - Defining module
    - Defining packages

- ***`\_\_future\_\_ statement`*** [Ref](https://github.com/sughosneo/blogs/blob/master/__future__.md) =>    
    - This statement helps to run the code snippet with those functions and statements which would be available in future releases.
    
    
- ***`Exception Handling`*** =>
    - try
    - catch
    - finally
    - Generic and specific exception

- ***`Classes Vs Objects`*** => This is standard OOPs concept, applicable in here too.

- ***`Constructors`*** [Ref]() => 
    - \_\_init\_\_ for a class to generate instance.
    
- ***`Destructors`*** [Ref]() => 
    - _\_del\_\_ for a object destructor of a instance.
    - Ideally you don't need to implement this destructor but for a class if someone wants to implement still they can. 
    
    ```python
      
        # Calling destructor 
        def __del__(self): 
            print("Destructor called") 
          
    ```

- ***`Comparing two object`*** [Ref](https://www.geeksforgeeks.org/difference-operator-python/) =>
    - We can do that using **is** operator in python
        
- ***`Different types of methods`*** [Ref](https://github.com/sughosneo/blogs/blob/master/type_of_methods_in_python.md) =>
    - instance methods
    - class methods
    - static methods

- ***`Inheritance`*** => Base class and Subclass concepts like standard OOPs.

- ***`Dunder or magic methods`*** [Ref](https://www.geeksforgeeks.org/dunder-magic-methods-python/) =>
    - This is actually double underscore methods. 
    - There are quite a bit of them available in ptyhon. Ex - \_\_main\_\_,\_\_call\_\_ etc..
    
- ***`Context Manages`*** [Ref](https://www.geeksforgeeks.org/context-manager-in-python/) =>
    - Helps to manage resources.
    - Ex - Database connection, File I/O connections etc.
    - Open connection and other dangling references gets taken care as soon as control flow gets out of the **with** clause.
    
    ```python
      
      with open("test.txt") as f:    
          data = f.read() 
    ```    

## Advanced
________________________________________________________________________________________________

- ***`Conditional Expression (extension of if/else statement)`*** =>
    - Example code snippet as per below :
    
    ```python
      result = value if condition else other_value
    ```
    
    
- ***`Anonymous functions or Lambda expression`*** =>
    - lambda is an expression.
    - It gets evaluated a function.
    - ***lambda argument : expression***
        - **Ex: -** lambda firstName : name.split()[-1]


- ***`map() and filter() function`*** [Ref](https://medium.com/@happymishra66/lambda-map-and-filter-in-python-4935f248593) =>
    
    - map() / function let run the function object on each item on a iterable.
    - filter() / function also does similar things. It let run the function on each item on a iterable.
    - Example - 
    
    ```python
    
      map(lambda x : x*2, [1, 2, 3, 4]) #Output [2, 4, 6, 8]
      
      filter(lambda x: x % 2 == 0, [1, 2, 3, 4, 5])
    ```
    
    


- ***`Difference between def and lambda`***

    - ***def*** is a statement /  ***lambda*** is an expression.
    - func has a name / lambda is anonymous
    - arguments delimited by parentheses / argument list terminated by colon(:)
         
- ***`Parameterized python script`*** =>
    - import argparse
    - parser = argparse.ArgumentParser(description='Process some integers.')
    - parser.add_argument(type=int,help='an integer for the accumulator')
    - args = parser.parse_args()
    
- ***`*args and **kwargs`*** [Ref](https://www.geeksforgeeks.org/args-kwargs-python/) =>
    - ***args** passing any number of parameter
    - ****kwargs** passing any number of key value pair as an arguments.
        
- ***`Package`*** =>
    - a module which can contain other modules
    
- ***`Module Vs Package`*** =>
    - Packages are directories.
    - Modules are generally file.
                    
- ***`Ductyping`*** [Ref](https://www.quora.com/What-is-Duck-typing-in-Python) =>
    - If it looks like a duck, swims like a duck, and quacks like a duck, then it probably is a duck.

- ***`Callable Instance`*** =>
    - \_\_call\_\_() methods
    - classes are callable

- ***`Serializing Python Objects`*** [Ref](https://github.com/sughosneo/blogs/blob/master/pickling_in_python.md) =>
    - Is the process whereby a python object hierarchy is converted into a bytestream and "Unpickling" is the inverse operation.
    
- ***`Functions are first class citizens`*** [Ref](https://github.com/sughosneo/blogs/blob/master/first_class_functions_in_python.md) =>
        
- ***`Nested functions`*** =>
    
    <details><summary>Code</summary>
    <p>
                
    ```python
  def outer_func():
    
        ''' This is the outter function which is callable '''
        
        j = 1
        k = 2
    
        def inner_local_func():
    
            ''' This functon is the local function and exist only within outter func '''
    
            a = "sumit"
            b = "ghosh"
    
            return a + " " + b
    
        print(inner_local_func())
    
        return j + k
        
  if __name__ == '__main__':
        print(outer_func())
    ```    
    </p>
    </details>
  
  - Returning local function / Yes, it can be done.
    
  <details><summary>Code</summary>
    <p>
                
   ```python
  def outer_func():    
        ''' This is the outter function which is callable '''        
    
        def inner_local_func():
    
            ''' This functon is the local function and exist only within outter func '''
    
            a = "sumit"
            b = "ghosh"
    
            return a + " " + b
        
        # return inner_local_func() - is also valid.
        return  inner_local_func
             
  if __name__ == '__main__':
        print(outer_func())
    ```    
    </p>
  </details>
    
- ***`Closures`*** [Ref](https://www.programiz.com/python-programming/closure) =>
        
    - It's a related concept with nested function that means function within a function.
    - This technique by which some data gets attached to the code is called closure in Python.
    - It has below properties.
        - We must have a nested function (function inside a function).
        - The nested function must refer to a value defined in the enclosing function.
        - The enclosing function must return the nested function.
    - In below code snippet firstName and lastName gets attached to the name variable, which can be executed later.
    <details><summary>Code</summary>
    <p>
                
    ```python
  def outer_func(firstName,lastName):
    ''' This is the outter function which is callable '''

    def inner_local_func():
        ''' This functon is the local function and exist only within outter func '''

        return firstName + " " + lastName

    return inner_local_func

  if __name__ == '__main__':
    name = outer_func("sumit","ghosh")
    print(name())

    ```    
    </p>
    </details>
    
            
- ***`Decorators`*** [Ref](https://github.com/sughosneo/dsalgo/tree/master/src/design_patterns/decorator) =>
    - Modify or enhance functions capability without changing function code.
    - It's just a syntactic sugar.    


- ***`Metaclasses`*** [Ref](https://pythontips.com/2013/09/20/all-about-the-metaclasses-in-python/) =>
    - Metaclasses are the ‘stuff’ that creates classes.
    - You define classes in order to create objects, right?
    - Python classes are objects,***metaclasses*** are the one who create these objects.
    - In Python3 onwards function ***type()*** is a metaclass. It lets you create class on the fly.


- ***`Monkey Patching`*** [Ref](https://www.geeksforgeeks.org/monkey-patching-in-python-dynamic-behavior/) =>
    
    - In Python, the term monkey patch refers to dynamic (or run-time) modifications of a class or module.
    - In Python, we can actually change the behavior of code at run-time.
    - Classes are mutable so we can reopen them and modify or even replace them.

- ***`Abstract base classes`*** [Ref](https://www.geeksforgeeks.org/abstract-classes-in-python/) =>
    - There is a popular say ***"Code towards abstraction"***
    - It's an important feature define a single interface to holding all the possible attribute or methods in a framework.
    - from abc import ABC,abstractproperty,abstractmethod         

- ***`Annotation typing`*** [Ref](https://dev.to/dstarner/using-pythons-type-annotations-4cfe) =>
    - Though python is a dynamic language. But in [PEP-848](https://www.python.org/dev/peps/pep-0484/) 
     type hinting has been introduced.
    - Developer still can specify type hinting in time of any variable use. Be it's a function or class attributes.
    - Originally this feature has been inspired from Type script.
    - Below code is annotated and it's easy to review and easy to read.If you notice person object has been called with wrong parameter
      but it still works and that's because of duck typing.
    - If you type ***help(person)*** you would notice __annotations__ information about **Person** class.
          
    <details><summary>Code</summary>
    <p>
                
    ```python
        
    '''
        Below script shown annotation example. 
        Anything apart from primitive types typing module needs to be imported. Ex : List return type in getDetails() method.
    '''
    from typing import List
    
    class Person:
    
        name : str
        age : int
        
        def __init__(self,name:str,age:int) -> None:
            self.name = name
            self.age = age
    
        def getDetails(self) -> List:
            ''' Return type is List'''
            return [self.name,self.age]
    
    
    if __name__ == '__main__':
    
       person = Person(10,"sumit")
       print(person.getDetails())
        
    ```    
    </p>
    </details>    
    
- ***`Data Classes`*** [Ref](https://realpython.com/python-data-classes/) =>
    - It's a new feature in python 3.7
    - It's a designated type of class which holds only data.
    - If you notice above annotation example Person class is also holding data for the person's name and age.
      And there constructor is involved to pass the data to the class during instantiation phase.
    - But it has become simplified a bit with data classes. Below is the example :
    
    <details><summary>Code</summary>
    <p>
                
    ```python
        
    from typing import List
    from dataclasses import dataclass
    
    @dataclass
    class Person:
    
        name : str
        age : int
    
        def getDetails(self) -> List:
    
            ''' Return type is List'''
            return [self.name,self.age]
            
    if __name__ == '__main__':
    
       person = Person("sumit",10)
       print(person.name)
       print(person.age)
        
    ```    
    </p>
    </details> 
    
- ***`Disposing/Cleaning up Python Obj`*** [Ref](https://stackoverflow.com/questions/865115/how-do-i-correctly-clean-up-a-python-object) =>
    - It's recomended to use with statement.
    - For any object automatically \_\_exit\_\_() method calls. If for the custom object specifically we could implement call
        \_\_exit\_\_() method.
       
    <details><summary>Code</summary>
    <p>
                
    ```python
        
    class SkeletonFixture:

    def __init__(self):
        pass

    def __enter__(self):
        return self

    def __exit__(self, exc_type, exc_value, traceback):
        pass

    def method(self):
        pass
    
    with SkeletonFixture() as fixture:
        fixture.method()
        
    ```    
    </p>
    </details>

- ***`Python Pointers Or Object Model`*** [Ref](https://realpython.com/pointers-in-python/) =>
    - Python Object model description.
    - Pointer doesn't exist in python. Everything is an object.

- ***`Memory Management in Python`*** [Ref]() =>
    - It's usually Garbage Collected by Cpython itself.

- ***`Asynchronous Programming In Python`*** [Ref](https://github.com/sughosneo/pyconcurrencydemo) =>
    - Before even talking about the Async programming, someone should understand different concepts about
    - Sync Single Threaded programming. 
    - Threading/ Multithreading programming.
    - Multiprocessing 
    - Async I/O which came from Python 3.4+
    - There are differences between concurrency and paraallelsim which has been described in [Ref](https://github.com/sughosneo/blogs/blob/master/concurrency_vs_parallelism.md) in here.
    - python also has some bultin libraries to achieve that. but user needs to know the difference between CPU bound and I/O bound operations/calls. 

- ***`GIL In Python`*** [Ref](https://realpython.com/python-gil/)
    - In simple terminology it's a mutex lock which only allows one python thread to hold the control of python interpreter.
    - It's actually applicable in individual python process. So multithreading in single python process it's not that so effective. CPU bound operations does affected because of that though IO bound operations wouldn't have much impact. 
    - That's the reason to utilize multiple CPU in multi-processor environment user should use Multiprocessing module rather than using multithreading. 
    - Other reference : https://www.geeksforgeeks.org/what-is-the-python-global-interpreter-lock-gil/   

- ***`Different Types of Locks In Python`*** [Ref](https://medium.com/better-programming/synchronization-primitives-in-python-564f89fee732) =>
    - Locks, RLocks, Semaphores, Events, Conditions and Barriers
    - Using this anyone can construct their own custom synchronization.
    - These are very much useful to synchronizing any multiple threads.
    - Simple usage of Condition which is advance one to make any individual function calls synchronous. 
    
    ```python
    
    # Example of how it can be used.  
    # https://leetcode.com/problems/print-in-order/
  
    from threading import Condition
  
    class Foo:
    
        isFirstCompleted = None
        isSecondCompleted = None
        condition = None
        
        def __init__(self):
            
            self.condition = Condition()
            self.isFirstCompleted = False
            self.isSecondCompleted = False
    
    
        def first(self, printFirst: 'Callable[[], None]') -> None:
                
            with self.condition:
                
                printFirst()
                self.isFirstCompleted = True
                self.condition.notifyAll()
                
    
    
        def second(self, printSecond: 'Callable[[], None]') -> None:
            
            with self.condition:
                self.condition.wait_for(
                    lambda: self.isFirstCompleted
                )
                            
                printSecond()
                self.isSecondCompleted = True
                self.condition.notifyAll()
    
        def third(self, printThird: 'Callable[[], None]') -> None:
            
            with self.condition:
                self.condition.wait_for(
                    lambda: self.isSecondCompleted
                )
                            
                printThird()            
                self.condition.notifyAll()
  
    ```    
    
    ```python
    
    # Another example of using lock/condition. Problem statement was :
    # https://leetcode.com/problems/print-foobar-alternately/
      
    from threading import Condition

    class FooBar:
        def __init__(self, n):
            self.n = n
            self._condition = Condition() # This condition would act as Semaphores
            self._isPrinted = False # This flag is going to get used as condition switching.
            
            
        def foo(self, printFoo: 'Callable[[], None]') -> None:
            
            for i in range(self.n):
                            
                with self._condition:
                    
                    self._condition.wait_for(
                        lambda: not self._isPrinted # So it would wait for True, that means _isPrinted value has to be False.
                    )
                    
                    printFoo()
                    self._isPrinted = True # Change the condition back to True
                    self._condition.notifyAll()
                    
    
    
        def bar(self, printBar: 'Callable[[], None]') -> None:
            
            for i in range(self.n):
                            
                with self._condition:
                                    
                    self._condition.wait_for(
                        lambda: self._isPrinted # Wait for the _isPrinted to become True. Because in after printing foo in above function it would be True.
                    )
                    
                    printBar()
                    self._isPrinted = False # Then switch the condition again back to False. So that it can be used in printFoo()
                    
                    self._condition.notifyAll()
                
    
    ```

- ***`Event Driven Programming`*** [Ref](https://www.youtube.com/watch?v=rJHTK2TfZ1I)
    - Event driven architecture is one of the programming model in different sceanrios. 
    - It has it's advantages and disadvantages respectively. 
    - It's different from standard request/response.
    - Python has popular async event based task queue system available which is [celery](https://www.youtube.com/watch?v=kDoHrFLkahA) 
         
- ***`Python program profiling`*** [Ref](https://github.com/sughosneo/blogs/blob/master/profiling_python_code.md) =>
    - How python program execution happens. Looking into it in details.
        
- ***`Obfuscating Python Code`*** [Ref](https://github.com/sughosneo/blogs/blob/master/obfuscating_python.md) => 
    - Making python source code non-readable.

- ***`Testing Python Code`*** [Ref]() =>
    - You can always perform Unit Test, Functional Test and Integration Test.
    - Python provides very rich framework for perform Unit and Functional Testing.

#### Q&A :
    
- ***`20 Useful Python Snippets`*** =>
   - https://medium.com/better-programming/20-python-snippets-you-should-learn-today-8328e26ff124
 
- ***`100 popular questions for python certifications`*** =>
    - https://www.edureka.co/blog/interview-questions/python-interview-questions/  
    
#### References :

[1] : PEP - https://www.python.org/dev/peps/

[2] : Stack Overflow - https://stackoverflow.com/

[3] : Geeksforgeeks - https://www.geeksforgeeks.org
 
[4] : RealPython - https://realpython.com/
 
[5] : Dev.to - https://dev.to/

[6] : Medium - http://medium.com

[7] : Youtube - https://www.youtube.com/
 
[8] : Quora - http://quora.com

[9] : GitHub - https://github.com/

