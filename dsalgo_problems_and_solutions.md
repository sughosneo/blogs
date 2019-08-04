### DSAlgo problem and solutions - in a single list

Arrays
--------------------------------------------

- ***`How do you find the missing number in a given integer array of 1 to 100?`*** 
    - https://www.geeksforgeeks.org/find-the-missing-number/
    - O(n) where n is numbmer of elements.

    
- ***`How do you find the duplicate number on a given integer array ?`***
    - Naive solution would be compare each element in the list with other which is O(n*(n-1))
    - But better solution is to use Dict/Hashmap to keep track of duplicate items. O(n), considering
        each dict or Hashmap operation complexity would be O(1). In this solution there would be an extra space required.
        

- ***`How do you find the largest and smallest number in an unsorted integer array ?`***
    - With one iteration of the list/array we could figure out largest and smallest element. We would just need to keep track of
        largest and smallest element in each iteration of every item. Complexity would be O(n)     
    - Or, we could sort the array and figure out the smallest and largest element with a[0] and a[len(a)-1]. Complexity would be in that case O(nlog(n))
    - http://www.java67.com/2014/02/how-to-find-largest-and-smallest-number-array-in-java.html
    

- ***`How do you find all pairs of an integer array whose sum is equal to a given number ?`***
    - Sort the array and then traverse from left and right simultaneously.
    - Or, use Dict/Hashmap to calculate other element from the sum.
    - https://www.geeksforgeeks.org/given-an-array-a-and-a-number-x-check-for-pair-in-a-with-sum-as-x/
    

- ***`How do you find duplicate numbers in an array if it contains multiple duplicates?`***
    - Use Dict/Hashmap 
    - https://www.geeksforgeeks.org/find-duplicates-in-on-time-and-constant-extra-space/            


- ***`How do you remove duplicates from an array in place?`***
    - If we would have had an option to use extra space we could have used Dict/Hashmap like above.
    - But in this case we have to use the same array.
    - So we would require to sort the array in ascending order. Once it's done, then it we could check each neighbour element for duplicate.
    - https://www.geeksforgeeks.org/remove-duplicates-sorted-array/
     
     
- ***`How do you reverse an array in place ?`*** 
    - In python someone can use reverse() methods on specific data structures.
    - We would require to loop through the middle of the array and keep replacing elements from first and last array.
    - https://www.geeksforgeeks.org/in-place-algorithm/
    


String
---------------------------------------------------------------------

- ***`How do you print duplicate characters from a string?`***
    - No of characters in both the string should be same.
    - Both the strings should use similar set of characters.
    - a) Sort both string and then compare both string.
    - b) Or, we can use Dict/Hashmap to count characters in both string.  
    - https://www.geeksforgeeks.org/check-whether-two-strings-are-anagram-of-each-other/
    

- ***`How do you print the first non-repeated character from a string?`***
    - We would require to scan all the chars once to form the Dict/Hashmap.
    - Then we would require to scan the chars again to figure out the value is 1 or not.
    - Then return that 1st char. 
    - https://www.geeksforgeeks.org/given-a-string-find-its-first-non-repeating-character/
    
    
- ***`How can a given string be reversed using recursion?`***
    - For generic reversed string problem there could be many ways. Recursion is one of the way.
    - Using for/while Loop, Python Built in function, using Stack, recursion.  
    - https://github.com/sughosneo/dsalgo/blob/master/src/basic/ReverseStringUsingRecursion.py  
    

- ***`How do you check if a given string is a palindrome?`***
    - We can reverse the string following above logic and then check if the both strings are same or not.
    - In that way we could see if both strings are palindrome or not.
    
    
- ***`How do you count a number of vowels and consonants in a given string?`***
    - We can still solve this problem using one for loop and counting each character and identifying a,e,i,o,u vowels.
    - Rest other characters would be the constants.
    - http://www.java67.com/2013/11/how-to-count-vowels-and-consonants-in-Java-String-word.html
    

- ***`How do you find all permutations of a string?`***
    - Need to implement.
    
- ***`Trie Datastructure`***
    - https://www.geeksforgeeks.org/trie-insert-and-search/
    - https://towardsdatascience.com/implementing-a-trie-data-structure-in-python-in-less-than-100-lines-of-code-a877ea23c1a1
    
    
- ***`Given a dictionary of words and a string of characters, find if the string of characters can be broken into individual valid words from the dictionary.`***
    - Need to implement. 
    
- ***`A DNA is composed of a series of nucleotides abbreviated as A, C, G, and T, for example: 'ACGAATTCCG'.
Write a function to find all the 10-letter-long sequences(sub-strings) that occur more than once in a DNA molecule.   
Example - Input: 'AAAAACCCCCAAAAACCCCCCAAAAAGGGTTT', Expected Output: [AAAAACCCCC,CCCCCAAAAA]`***
    - Implementation : 
    - https://www.ideserve.co.in/learn/find-10-letter-repeated-DNA-sequences

- ***`Given a string S, find the longest palindromic subsequence.`***
    - 
    
- ***`Heap implementation`***
    - https://towardsdatascience.com/data-structure-heap-23d4c78a6962
    - https://interactivepython.org/runestone/static/pythonds/Trees/BinaryHeapImplementation.html
    

Trees
---------------------------------------------------------------------

- ***`Binary Trees`*** 
    - 

- ***`BFS`***
    - https://medium.com/basecs/breaking-down-breadth-first-search-cebe696709d9
    
- ***`DFS`***