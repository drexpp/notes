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
    
