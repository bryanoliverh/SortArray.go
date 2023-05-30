# List of some of my LeetCode, HackerRank, and other challenges!
1. [compress.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/compress.go)

 - Time Complexity: O(n)
   
   Space Complexity: O(1)

 - **Input and Output Examples:**
 
   **Example 1:**

   Input: chars = ["a","a","b","b","c","c","c"] 
   Output: Return 6, and the first 6 characters of the input array should be: ["a","2","b","2","c","3"] 
   Explanation: The groups are "aa", "bb", and "ccc". This compresses to "a2b2c3". 
   
   **Example 2:** 

   Input: chars = ["a"] 
   Output: Return 1, and the first character of the input array should be: ["a"] 
   Explanation: The only group is "a", which remains uncompressed since it's a single character. 
  
   **Example 3:**

   Input: chars = ["a","b","b","b","b","b","b","b","b","b","b","b","b"] 
   Output: Return 4, and the first 4 characters of the input array should be: ["a","b","1","2"]. 
   Explanation: The groups are "a" and "bbbbbbbbbbbb". This compresses to "ab12". 

 - It will first check if the length of chars is 0 or 1 and it will return 0 or 1 respectively, since there is no need to compress a sequence of 0 or 1 character.

 - The function initializes comp variable to be the first character in chars, count to be 1, and compressIdx to be 0 and it will then enter a for loop that iterates over the characters in chars, starting from the second character. If the current character is the same as the previous one (comp), the function increments the count variable by 1.

 - If the current character is different from the previous one, the function writes the previous character (comp) to the compressIdx position in chars and increments compressIdx by 1.If the count variable is greater than 1, it means there are repeated characters, so the function converts the count to a string using strconv.Itoa(count) and writes each digit of the count to the compressIdx position in chars, and increments compressIdx by the length of the count string. The function then updates comp to be the current character and resets count to 1. After the loop is finished, the function returns the value of compressIdx, which represents the length of the compressed sequence.

2. [isPalindrome.go](https://github.com/bryanoliverh/LeetCode-Practice-Golang/blob/main/sortArray.go)

  - Time Complexity: O(log(n))
  
    Space Complexity: O(n)

  - The function isPalindrome takes an integer x as input and it will return a boolean which indicates whether x is a palindrome or not. A palindrome is a number that reads the same backward as forward.
so for example:

  - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: x = 121
    
    Output: true
    
    Explanation: 121 reads as 121 from left to right and from right to left.

  - The function first checks if x is negative or ends with a zero, except when x is zero itself. If either condition is true, the function immediately returns false because such numbers cannot be palindromes.

  - Afterward, the function initializes a variable rev to zero and it will enter a loop where it repeatedly extracts the last digit of x and adds it to rev after shifting the digits of rev one position to the left. Therefore, this effectively reverses the digits of x and stores the result in rev. At the same time, the function removes the last digit of x by integer division with 10.

  - The loop will continue as long as x is greater than rev, since the reversal of the first half of x is not complete until x becomes smaller than rev. If x and rev have an odd number of digits, the middle digit is ignored because it is the same in both numbers. After the loop completes, the function checks whether x is equal to rev or to rev/10 and the second case arises when x has an odd number of digits, and the middle digit has already been removed from rev.
  - The expression x == reverse || x == reverse / 10 is checking whether the input integer x is a palindrome or not while at the end of the for loop, the variable reverse will contain the reverse of the first half of x. For example, if x is 1234321, then reverse will be 1234. Then it will compare the first half of x with the second half to check if it's a palindrome. If x has an odd number of digits, we can ignore the middle digit, which will be equal to itself. If x has an even number of digits, we need to compare the first half of x with the second half minus the last digit. For example, if x is 1221, then reverse will be 12, and we need to ignore the last digit in reverse. Therefore, the expression x == reverse / 10 checks if x is a palindrome when it has an even number of digits.
  - If either of these conditions is true, the function returns true, indicating that x is a palindrome. Otherwise, it returns false.

  
3. [sortArray.go](https://github.com/bryanoliverh/LeetCode-Practice-Golang/blob/main/sortArray.go)
  - Time Complexity: O(n log n)
    
    Space Complexity: O(n)

  - Sort Array Function in GO without built-in functions!

  - The function takes 1 list input and returns the sorted list without any built in functions.


  - The function implements quick sort algorithm which takes slice of integers with the variable name of nums, and the range of indices low and high which will be sorted. If low is less than high, the slice will be partitioned using the partition function, and recursively calls itself on the left and right sub-arrays.

 - Another function is the partition function which is used to do the partition of the input slice of integers nums. It will choose the last element in the slice as the initial element that will be use as the pivot, and iterates over the slice from low to high-1. If an element is less than the initial element, it swaps it with the current index i, and increments i. Finally, it swaps the pivot element with the element at index i and returns i.

4. [twoSum.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/twoSum.go)

  - Time Complexity: O(n)
   
    Space Complexity: O(n)
  - Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.  You may assume that each input would have exactly one solution, and you may not use the same element twice. 
  - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: nums = [2,7,11,15], target = 9 
    
    Output: [0,1] 
    
    Explanation: Because nums[0] + nums[1] == 9, we return [0, 1]. 
  - The twoSum function takes an integer slice array and a target integer target as its input, and returns a slice of two integers that represent the indices of the two numbers in the input array that add up to the target value. If there are no such indices, an empty slice is returned. 
  - The function uses a hash map called seenNums to keep track of the numbers it has already seen while iterating through the array. In each iteration, it calculates the difference between the target value and the current number in the array and checks whether the difference is already in the hash map. If it is, the function returns a slice with the current index i and the index of the difference j that was previously stored in the hash map. If the difference is not in the hash map, the function stores the current number and its index in the hash map. 
  - seenNums map stores the numbers in the input array as keys and their corresponding indices as values. The syntax j, ok := seenNums[potentialMatch] will simultaneously checks whether the value exists in the map and retrieves its value. The value of found will be true if potentialMatch is a key in the seenNums map, and false otherwise. The value of j will be the value associated with the key potentialMatch if it exists in the map, and the zero value for its type otherwise. 
  
 5. [intToRoman_romanToInt.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/intToRoman_romanToInt.go)
   -  Time Complexity: O(n)
   
      Space Complexity: O(1)
  - Given an integer, convert it to a roman numeral. 
  - **Input and Output Examples:**
  
     **Example 1:** 
     
     Input: num = 3 
     
     Output: "III" 
     
     Explanation: 3 is represented as 3 ones. 

     **Example 2:** 
     
     Input: num = 58 
     
     Output: "LVIII" 
     
     Explanation: L = 50, V = 5, III = 3. 
   - romanToInt is the reverse function that will take roman characters and map it to Integer/common numbers.
   
   
6. [threeSumClosest.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/threeSumClosest.go)
  -  Time Complexity: O(n^2)
   
      Space Complexity: O(1)
      
  - This function finds the closest sum of three numbers in the given input slice nums to a target number target. 
  - The function starts by sorting the input slice. Then, it iterates over the first len(nums) - 2 elements of the sorted slice nums, while keeping track of the closest sum seen so far and the distance of the closest sum to the target. 

  - For each element nums[i] in the outer loop, the function initializes two pointers left and right that point to the next and last elements, respectively. It then iterates over the slice from the left and right pointers until they meet. 

 
 

  - At each iteration, the function calculates the sum of the three elements at indices i, left, and right. If this sum is less than the target, the left pointer is incremented, otherwise, the right pointer is decremented. If the sum equals the target, the function returns the target. 

  - For each calculated sum, the function checks if it is closer to the target than the closest sum seen so far. If so, it updates the closest sum and the distance accordingly. 

  - Finally, the function returns the closest sum found. 
  
7. [mergeTwoList.go](  https://github.com/bryanoliverh/CodePractice-Golang/blob/main/mergeTwoList.go)
  -  Time Complexity: O(m+n), where m and n are the lengths of list1 and list2 
   
      Space Complexity: O(1)
      
  - **Input and Output Examples:**
  
    **Example 1:** 
    
    Input: list1 = [1,2,4], list2 = [1,3,4]
    
    Output: [1,1,2,3,4,4]

    **Example 2:**

    Input: list1 = [], list2 = []
    
    Output: []
  
  
  - The mergeTwoLists function takes in two singly-linked lists list1 and list2 and merges them into a new singly-linked list. To create the new list, a dummy node is created as a placeholder, and a pointer tail is set to it.

  - Then, a loop is initiated to compare each node in both lists. If the value of the current node in list1 is less than or equal to the value of the current node in list2, the tail node's Next pointer is set to point to the current node in list1, and list1 moves on to the next node in the list. Otherwise, the tail node's Next pointer is set to point to the current node in list2, and list2 moves on to the next node in the list. The tail node is then moved to the next node in the new list.

  - After the loop has completed, any remaining nodes in either list1 or list2 are added to the new list. If there are still nodes remaining in list1, the tail node's Next pointer is set to point to list1. If there are still nodes remaining in list2, the tail node's Next pointer is set to point to list2.

  - Finally, the function returns the Next pointer of the dummy node. This is because the first node in the new list is the Next node of the dummy node, which was created only as a placeholder and has no other significance in the new list. By returning the Next pointer of the dummy node, we are effectively returning the first node of the new list.

8. [removeDuplicates.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/removeDuplicates.go)
  -  Time Complexity: O(n log n) which is dominated by the sorting function.
   
     Space Complexity: O(1)
      
  - **Input and Output Examples:**
  
    **Example 1:**

    Input: nums = [1,1,2]
    
    Output: 2, nums = [1,2,_]
    
    Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
    It does not matter what you leave beyond the returned k (hence they are underscores).
    
    
    **Example 2:**

    Input: nums = [0,0,1,1,1,2,2,3,3,4]
    
    Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
    
    Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
    
    It does not matter what you leave beyond the returned k (hence they are underscores).


9. [lengthOfLastWord.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/lengthOfLastWord.go)
  -  Time Complexity: O(n)
   
     Space Complexity: O(n)
      
  - **Input and Output Examples:**

    **Example 1:**
    
    Input: s = "Hello World"
    
    Output: 5
    
    Explanation: The last word is "World" with length 5.
    
    **Example 2:**

    Input: s = "   fly me   to   the moon  "
    
    Output: 4
    
    Explanation: The last word is "moon" with length 4.


  - Given a string s consisting of words and spaces, return the length of the last word in the string.
  
  - A word is a maximal substring consisting of non-space characters only.
  
  - The function loops through each character in the input string and it will check if the character is a space (ASCII code 32). If it is a space, it means that it is going to be a new word and the new string will be emptied. Otherwise, the character is added to the current finStr variable.
  
 10. [interval.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/interval.go)
  -  The task is to combine overlapping intervals in a given list to create a new list that contains only intervals that do not overlap with each other.

  -  Time Complexity: O(n log n)
   
     Space Complexity: O(n)
      
  - **Input and Output Examples:**

    **Example 1:**
    
    Input: {1, 10}, {2, 9}, {5, 11}, {3, 4}
    
    Output: (1, 11)
 11. [determineIdenticalBinaryTree.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/determineIdenticalBinaryTree.go)
  -  The problem asks to determine if two binary trees are structurally identical, meaning they have the same shape and nodes with the same values.
  
  -  Compare each node of the two binary trees, starting from their roots and going down to their leaves. If the nodes being compared are equal, the function recursively calls itself on the left and right children of the nodes. If at any point during the recursion, two nodes being compared are not equal, the function returns false. If the function completes the recursion without returning false, it means that the two trees are identical, and the function returns true.

  -  Time Complexity: O(n)
   
     Space Complexity: O(n)
      
  - **Input and Output Examples:**

    **Example 1:**
    
    Input: Tree 1:
            1
           │   2
           │  │   4
           │      5
               3
              │   6
           Tree 2:
            1
           │   2
           │  │   4
           │      5
               3
              │   6

    
    
    Output: The two binary trees are identical.
 
  12. [isPalindromeStr.go]( https://github.com/bryanoliverh/CodePractice-Golang/blob/main/isPalindromeStr.go)
  -  Check whether the given string is a palindrome or not.

  -  Time Complexity: O(n)
   
     Space Complexity: O(n)
      
  - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: "A man a plan a canal Panama is a palindrome."
    
    Output: not a not a not is not a palindrome.
    

    **Example 2:**
    
    Input: "not a not a not"
    
    Output: not a not a not is not a palindrome.
    
13. [maxSubArray.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/maxSubArray.go)

  -  Create a function to compute the largest sum subarray of the input array.

  -  Time Complexity: O(n)
   
     Space Complexity: O(1)
      
  - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: [-2, 1, -3, 4, -1, 2, 1, -5, 4]
    
    Output: Indices 3 to 6: 4 -1 2 1  Largest Sum Subarray: 6
            
    **Example 2:**
     
     Input: [1, 2, 3, 4, 5]

     Output: Indices 0 to 4: 1 2 3 4 5 Largest Sum Subarray: 15

14. [printPeople.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/printPeople.go)

  -  Create a function to practice using linkedlist, struct, list, and Map.

  -  Time Complexity: O(n)
   
     Space Complexity: O(n)
      
  - **Input and Output Examples:**
    
    **Example 1:**
        
    Output: 
    ```     
            Name of All Registered People

            ID: 1, Name: John, Age: 17, Location: New York
            
            ID: 2, Name: Jane, Age: 22, Location: Los Angeles
            
            ID: 3, Name: Bob, Age: 30, Location: Chicago
            
            Name of People Above 20 yo:Name: John, Age: 17
            
            Name of People Above 20 yo:Name: Jane, Age: 22
            
            Name of People Above 20 yo:Name: Bob, Age: 30
            
15. [longestCommonPrefix.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/longestCommonPrefix.go)

  -  Create a function to find the longest common prefix string amongst an array of strings.


  -  Time Complexity: O(n*m) (m= the length of the shortest string in the strs slice for example the length of the longest common prefix, n= the total number of characters in all the strings in the strs slice).
   
     Space Complexity: O(1)
      
  - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: strs = ["flower","flow","flight"]
    
    Output: "fl"
    
    **Example 2:**
    
    Input: strs = ["dog","racecar","car"]
    
    Output: ""
 
 16. [longestCommonSubstring.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/longestCommonSubstring.go)

  -  Create a function to find the longest common substring string contained amongst an array of strings.

  -  Time Complexity: O(m*n^2) (m= the length of the first string in the strs slice, n refers to the total number of characters in all the strings in the strs slice).
   
     Space Complexity: O(m) (m= the length of the first string in the strs slice)
      
  - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: strs = ["helloeworld", "oewor", "worhelloe"]
    
    Output: "wor"        
 
 17. [addBinary.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/addBinary.go)

  -  Create a function to calculate an input from two binary strings.

  -  Time Complexity: O(n) 
   
     Space Complexity: O(n) 

 - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: a = "11", b = "1"
    
    Output: "100"   
        
    **Example 2:**
    
    Input: a = "1010", b = "1011"
    
    Output: "10101"   

 18. [indexFirstOccurence.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/indexFirstOccurence.go)

  -  Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

  -  The loop condition i <= len(haystack)-len(needle) ensures that the loop will only iterate up to the point where the remaining characters in haystack are greater than or equal to the length of needle. This is because there's no point in checking substrings that are shorter than the needle string. Inside the loop, haystack[i:i+len(needle)] is used to extract a substring of haystack starting from index i and with a length equal to the length of needle. This substring is then compared with the needle string using the equality operator ==. If the substring matches the needle string, the function immediately returns the value of i, indicating the index of the first occurrence of needle in haystack. If no match is found within the loop, the function will continue to the next iteration until all possible substrings of haystack have been checked. If no match is found at all, the function will reach the end and return -1 to indicate that needle is not part of haystack.

  -  Time Complexity: O((N-M)M), where N is the length of haystack and M is the length of needle.
   
     Space Complexity: O(1) 

 - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: haystack = "sadbutsad", needle = "sad"
    Output: 0
    Explanation: "sad" occurs at index 0 and 6. The first occurrence is at index 0, so we return 0.  
        
    **Example 2:**
    
    Input: haystack = "leetcode", needle = "leeto"
    Output: -1
    Explanation: "leeto" did not occur in "leetcode", so we return -1.  
 
 19. [removeElement.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/removeElement.go)

  -  Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val. Change the array nums such that the first k elements of nums contain the elements which are not equal to val. The remaining elements of nums are not important as well as the size of nums. Return k.

  -  Time Complexity: O(n), where n is the length of nums.
   
     Space Complexity: O(1) 

 - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: nums = [3,2,2,3], val = 3
    Output: 2, nums = [2,2,_,_]
    Explanation: Your function should return k = 2, with the first two elements of nums being 2. It does not matter what you leave beyond the returned k (hence they are underscores).
        
    **Example 2:**
    
    Input: nums = [0,1,2,2,3,0,4,2], val = 2
    Output: 5, nums = [0,1,4,0,3,_,_,_]
    Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4. Note that the five elements can be returned in any order. It does not matter what you leave beyond the returned k (hence they are underscores).

20. [reverseInt.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/reverseInt.go)

  -  Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0. Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

  -  Time Complexity: O(log(x))
   
     Space Complexity: O(1) 

 - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: x = 123
    Output: 321
    
    **Example 2:**
    
    Input: x = -123
    Output: -321
    
    **Example 3:**
    
    Input: x = 120
    Output: 21
    
 21. [removeNthFromEnd.go](https://github.com/bryanoliverh/CodePractice-Golang/blob/main/removeNthFromEnd.go)

  -  Given the head of a linked list, remove the nth node from the end of the list and return its head.

  -  By using &ListNode{Next: head}, you create a new ListNode instance with its Next field pointing to the head node. This way, dummy becomes a pointer to this new node, and its Next field connects to the original list starting from the head node.

  -  Time Complexity: O(N), N is the number of nodes in the linked list
   
     Space Complexity: O(1) 

 - **Input and Output Examples:**
    
    **Example 1:**
    
    Input: head = [1,2,3,4,5], n = 2
    Output: [1,2,3,5]
    
    **Example 2:**
    
    Input: head = [1], n = 1
    Output: []
    
    **Example 3:**
    
    Input: head = [1,2], n = 1
    Output: [1]
    
    
