### Type of methods and functions in python

In terms of methods - 

- Instance methods
- Class methods
- Static methods

In terms of functions - 

- Normal functions 
- Lamda/Anonymous functions


##### Instance methods :
    
    class C():
        
        def func(self,arg1):
            ....
            
        fun: function that would get converted into a C class instance method
        returns: a class method for function.
    
    # Calling instance methods
    c = C()
    c.func()
        
##### Class methods :

    class C():
    
        @classmethod
        def fun(cls, arg1, arg2, ...):
           ....
          
        fun: function that needs to be converted into a class method
        returns: a class method for function. 
    
    # Calling class methods
    value = C.func()

##### Static methods :

    class C():
    
        @staticmethod
        def fun(arg1, arg2, ...):
            ...
        returns: a static method for function fun.
     
    # Calling static methods
    value = C.func()
    


##### Normal functions :

    def myfunc():
        
        return "foo"
    
    if __name__ == '__main__':
        value = myfunc()



##### Lamda functions :
    
    sum = lambda x, y : x + y
    print(sum)


Ref :  

https://www.geeksforgeeks.org/class-method-vs-static-method-python/
https://www.w3schools.com/python/python_lambda.asp

