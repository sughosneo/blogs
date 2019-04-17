### Pickling In Python

##### What is Pickling ?

  - Is the process whereby a python object hierarchy is converted into a bytestream and "Unpickling" is the inverse operation.

##### What are Picklable Objects ?

    - None, True, and False
    - integers, long integers, floating point numbers, complex numbers
    - normal and Unicode strings
    - tuples, lists, sets, and dictionaries containing only picklable objects
    - functions defined at the top level of a module
    - built-in functions defined at the top level of a module
    - classes that are defined at the top level of a module
    - instances of such classes whose __dict__ or __setstate__() is picklable (see section 3.14.5 for details)

In some other language this methodology is called as - Marshalling and Unmarshalling.

Ref :

https://docs.python.org/2.4/lib/node66.html
