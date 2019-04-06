## Do I know shell scripting ?

Though I work with some of the basic unix command everyday. But I always ask myself this question.
If you have the same feeling better you go through below reference and try out some of the basic shell programming of your own.

#### Where shell gets placed in Unix Architecture ?

 ![Unix Architecture](./images/u_arch_diagram.png)

#### Good guide for the beginners :
Ref : https://www.tutorialspoint.com/unix/shell_scripting.htm 

#### Some of the basic theory oriented questions :
Ref : https://www.softwaretestinghelp.com/shell-scripting-interview-questions/

#### And here is my sample code :

    #!/bin/bash
    # How to take parameters in shell script ?
    Name=$1
    Value=$2

    # How can someone read any user input ?
    read email

    # Printing user input(s) using echo command
    echo $Name
    echo $Value
    echo $email

    # Below block show basic while loop. 
    # It's same like other language but just syntaxwise there are some differences
    i=0
    while [ $i -lt 20 ]
    do
            echo $i 
            i=`expr $i + 1`
    done

    # Defining a string array 
    nameArray="Sumit","Ghosh","John","Doe"

    # Accessing previously defined array value(s) using for loop
    for name in $nameArray
    do
            echo $name
    done
  
  # How can I run this shell script code ?
    $ cd /home/<work_dir>/
    $ vi CodeSample.sh
    $ Copy above code content and save the file. 
    $ Then to run this
    $ bash ./CodeSample.sh "sumit" 3 or sh ./CodeSample.sh "sumit" 3
    $ Script would wait on the user input. 
    $ Type email id like - foo@abc.com
    $ Then you would see output in the screen.
  
