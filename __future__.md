###  \_\_future\_\_ - Statement In Python 

A future statement is a directive to the compiler that a particular module should be compiled using syntax or semantics that will be available in a specified future release of Python where the feature becomes standard.

The future statement is intended to ease migration to future versions of Python that introduce incompatible changes to the language. It allows use of the new features on a per-module basis before the release in which the feature becomes standard.

For an example :

You have written below code snippet: 

    def printInfo():
        print("This is a valuable information")

    if __name__ == '__main__':
        printInfo()
        
It would work fine in python3.x but if you want to run this code in python2.x then it wouldn't work because **print** in the python2 print is 
a statement. So if you have to make this same code works in python2 as well. You would require to import **\_\_future\_\_** module.
So code snippet would become as per below :

    from __future__ import print_function

    def printInfo():
        print("This is a valuable information")

    if __name__ == '__main__':
        printInfo()

- For further example - you can look into https://github.com/keras-team/keras/blob/master/keras/backend/common.py 
Most of the renound companies when they opensource their python code base for any applications you would notice this behaviour in their respective modules.

#### Things to remember before using it - 

- A future statement must appear near the top of the module. 
- The only lines that can appear before a future statement are:

  the module docstring (if any),
  comments,
  blank lines, and
  other future statements.
  The only feature in Python 3.7 that requires using the future statement is annotations.
  
  All historical features enabled by the future statement are still recognized by Python 3. 
  The list includes **absolute_import, division, generators, generator_stop, unicode_literals, print_function, nested_scopes and with_statement**. 
  
  They are all redundant because they are always enabled, and only kept for backwards compatibility.
  
 #### Ref :
 
 https://docs.python.org/3/reference/simple_stmts.html#future-statements 
 https://stackoverflow.com/questions/7075082/what-is-future-in-python-used-for-and-how-when-to-use-it-and-how-it-works
 https://www.youtube.com/watch?v=-VEHllXwVJY
 
 
 
