October 2018
==========

Tech
----


### Compilers (Compilers: Principles, Techniques, and Tools (2nd Edition))
  
  #### Scopes (static, dynamic and explicit access control)
  
   - static: Typical scope-block structure of C++ programs.
   ![static](https://i.imgur.com/26nvu5U.png)

    
   - explicit: Java, C++, C, ... (protected, public, private)
    
   - dynamic: Has to be decided in run time
   ![dynamic](https://i.imgur.com/HT3JMFu.png)
  
    
### Cracking the code interview

  #### Arrays and Strings
    
  - StringBuilder: Creates a resizable array of all the strings, copying them back to a string only when necessary.
```
    String joinWords(String[] words) {
      StringBuilder sentence
      new StringBuilder();
      for (String w : words) {
        sentence.append(w);
      }
      return sentence.toString();
    }
```

  - 1.1 - Implement an algorithm to determine if a string has all unique characters
  
  ```
  def isUniqueChars(str):
        if(len(str) > 128):
                return False

        arrChars = []
        for c in str:
                if c in arrChars:
                        return False
                else:
                         arrChars.append(c)
        return True


  isUniqueChars('abcdefghijm')
  ```
  
  - 1.2 - Given two strings, write a method to decide if one is a permutation of the other
  
  
    - One approach
   
    ```
    def isPermutationSort(str1, str2):
        if len(str1) != len(str2):
                return False

        return sorted(str1) == sorted(str2)

    isPermutationSort('abcdex', 'axdcbe')
    ```
    - Other approach
    ```
    def isPermutation(str1, str2):
            if len(str1) != len(str2):
                    return False

            dictChars1 = {}

            for c in str1:
                    if c in dictChars1:
                            dictChars1[c] += 1
                    else:
                            dictChars1[c] = 1
            for c in str2:
                    if c in dictChars1:
                            dictChars1[c] -= 1
                            if dictChars1[c] < 0:
                                    return False
                    else:
                            return False

            return True


    isPermutation('abcdexe', 'gdcabex')                                
    ```
    
  - 1.3 - Write a method to replace all spaces in a string with '%20'.
    ```
    import string

    def Urlify(sStr, iNum):
            sNewStr = sStr[:iNum].replace(' ', '%20')
            print(sNewStr)
            
    Urlify('hello world hehe   ', 16)                                         
    ```
    
  - 1.4 - Given a string, write a function to check if it is a permutation of a palindrome
    
    ```
    # Time complexity O(n)
    def checkIfPermIsPalindrome(str):
            dictWordsCount = {}
            count = 0

            for c in str:
                    if c in dictWordsCount:
                            dictWordsCount[c] += 1     
                            if dictWordsCount[c] % 2 == 0:
                                    count -= 1
                    else:
                            dictWordsCount[c] = 1
                            if c != ' ':
                                    count += 1
            return count <= 1
            
    checkIfPermIsPalindrome('tact coa')
    ```
