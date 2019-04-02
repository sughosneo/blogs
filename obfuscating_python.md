### Obfuscating Python Code
--------------------

My point of view in this topic would be - python might not have designed to be like this.I agree with some of the comments in this stack overflow conversation - https://stackoverflow.com/questions/261638/how-do-i-protect-python-code
Actully as per my understanding goes instead of giving .py files it's better to ship .pyc byte code whereever it's required. 
As there is no compiled concept in python point of view, byte code could be the possible answer. 
Now the question is can someone look into my byte code ? Well start reading over internet and found some answers around that - 

https://wiki.python.org/moin/Asking%20for%20Help/How%20do%20you%20protect%20Python%20source%20code%3F
https://wiki.python.org/moin/Pyarmor

To clear the head thought of creating one sample api and test it out,
Here it how it looks like - https://github.com/sughosneo/pycdemo

Ah ha ! so that's how it works !

On further reading found out one interesting article in medium - https://medium.com/@xpl/protecting-python-sources-using-cython-dcd940bb188e 
Further comments on this, when I would try that out.

