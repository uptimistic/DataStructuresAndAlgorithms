# DataStructures And Algorithms
Documentation of Data Strcutures and Algorithms Implemented in Python Programming Language(list of respurces below are in no particular oder):

Resources/References Used :
1. [Problem Solving with Algorithms and Data Structures using Python](https://runestone.academy/runestone/books/published/pythonds/index.html)
2. [Practical Algorithms and Data Structures](https://bradfieldcs.com/algos/)
3. [Algorithm Design Manual- 3rd Edition released 2020](https://www.algorist.com/)
4. [CLRS Intro to Algorithms, MIT Press ](https://edutechlearners.com/download/Introduction_to_algorithms-3rd%20Edition.pdf)
5. [Al Swwagart python cheat sheet](https://www.pythoncheatsheet.org/)
6. [Official Python Tutorial](https://docs.python.org/3/tutorial/index.html)
7. [Cracking the Coding Interview Part VI, Part IX( Chapters 1-4,7-8,10,16)](https://acrobat.adobe.com/link/review?uri=urn:aaid:scds:US:609efe13-dcab-4cbd-a304-d976e45a5e8c)
8. [GeekforGeeks company specific preparations](https://www.geeksforgeeks.org/company-preparation/)
9. [Hackerank](https://www.hackerrank.com/dashboard)

10. [Leetcode](https://leetcode.com/problemset/all/)

11. [TechieDelight- 500+ Data Structures & Algorithms with solution ](https://www.techiedelight.com/data-structures-and-algorithms-problems/)

12. [A Common-Sense Guide to Data Structures and Algorithms - Level Up Your Core Programming Skills](https://github.com/bat67/awesome-algorithm-books/blob/master/classic%20algorithms/A%20Common-Sense%20Guide%20to%20Data%20Structures%20and%20Algorithms%20-%20Level%20Up%20Your%20Core%20Programming%20Skills.epub)

13. [Data Structures and Algorithms with Python- Kent Lee](https://github.com/priscilj/Hadoop-related-books/blob/master/Data%20Structures%20and%20Algorithms%20with%20Python%20By%20Kent%20D.%20Lee%2C%20Steve%20Hubbard%202015%20Springer.pdf)
14. [Data Structure & Algorithms Visualizations- VisuAlgo](https://visualgo.net/en)
15. [Data Structure & Algorithms Visualizations- usfca.edu](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html)
16. [[Data Structure & Algorithms- Goodrich](http://index-of.es/Varios-2/Data%20Structures%20and%20Algorithms%20in%20Python.pdf)
17. [VISUALIZE CODE RUN-pythontutor ](http://pythontutor.com/visualize.html#mode=edit)

***************************************************************************************************************

----
ALGORITHM IMPLEMENTATION 
---
1. Two Sum
```python
def two_sum(nums, target):
    """
    Given an array of integers 'nums' and an integer 'target', 
    return indices of the two numbers such that they add up to 'target'.

    Example:
    nums = [2, 7, 11, 15], target = 9
    Output: [0, 1] (because nums[0] + nums[1] = 2 + 7 = 9)
    """

    # Create a dictionary to store each number in 'nums' as the key and its index as the value
    num_dict = {}

    # Iterate through 'nums'
    for i in range(len(nums)):
        # Check if 'target' minus the current number is already in the dictionary
        complement = target - nums[i]
        if complement in num_dict:
            # If so, return the current index and the index of the complement
            return [num_dict[complement], i]
        # If not, add the current number and its index to the dictionary
        num_dict[nums[i]] = i

    # If no solution is found, return an empty list
    return []

```
---
```python
def two_sum(nums, target):
    """
    Given an array of integers, return indices of the two numbers such that they add up to a specific target.

    :param nums: list[int]
    :param target: int
    :return: list[int]
    """
    num_map = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in num_map:
            return [num_map[complement], i]
        num_map[num] = i
    return []

```
---
This function takes a list of integers ```nums``` and a target integer ```target``` as input, and returns a pair of indices of numbers in the list that sum to the target, if such a pair exists. If no such pair exists, it returns ```None```.

The algorithm works by iterating through the list of numbers and storing the indices of the numbers we've seen so far in a dictionary. For each number, we calculate its complement (i.e., the number we need to add to it to get the target). If we've seen the complement before (i.e., it's in the dictionary), we've found a pair that sums to the target and we return the indices of the two numbers. If we haven't seen the complement before, we store the current number and its index in the dictionary and continue iterating. If we've iterated through the entire list and haven't found a pair that sums to the target, we return ```None```.

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]

Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

Example 2:
Input: nums = [3,2,4], target = 6
Output: [1,2]

Example 3:
Input: nums = [3,3], target = 6
Output: [0,1]

```python
def twoSum(nums, target):
    """
    :type nums: List[int]
    :type target: int
    :rtype: List[int]
    """
    # Create a dictionary to store the indices of the numbers we've seen so far
    seen = {}
    
    # Iterate through the list of numbers
    for i in range(len(nums)):
        
        # Calculate the complement of the current number
        complement = target - nums[i]
        
        # If we've seen the complement before, we've found a pair that sums to the target
        if complement in seen:
            return [seen[complement], i]
        
        # Otherwise, store the current number and its index in the dictionary
        seen[nums[i]] = i
    
    # If we've iterated through the entire list and haven't found a pair that sums to the target, return None
    return None

```
---
The function takes in an array ```nums``` and a target number ```target```, and returns a list of two indices of the numbers in ```nums``` that add up to ```target```. If no such pair of numbers exists, it returns an empty list.

The time complexity of this implementation is O(n), where n is the length of the input array ```nums```. This is because we only loop through the array once, and the dictionary lookup operation takes O(1) time on average.
```python
def two_sum(nums, target):
    # Create a dictionary to store the complement of each number and its index
    complement_dict = {}
    # Loop through the array
    for i in range(len(nums)):
        # Check if the complement of the current number exists in the dictionary
        if nums[i] in complement_dict:
            # If it does, return the indices of the two numbers that add up to the target
            return [complement_dict[nums[i]], i]
        else:
            # If it doesn't, add the complement of the current number and its index to the dictionary
            complement_dict[target - nums[i]] = i
    # If no solution is found, return an empty list
    return []

```
---
The Two Sum problem on LeetCode is a classic algorithmic problem that asks the following:

Given an array of integers ```nums``` and an integer ```target```, return indices of the two numbers such that they add up to ```target```.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Here's the Python code to solve the Two Sum problem on LeetCode:

This solution uses a hash map to store the indices of the numbers as we iterate through the array. We calculate the complement of each number with respect to the target and check if it's already in the hash map. If it is, we return the indices of the two numbers that add up to the target. If not, we add the current number and its index to the hash map and continue iterating. The time complexity of this solution is O(n), where n is the length of the array
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        hash_map = {}
        for i, num in enumerate(nums):
            complement = target - num
            if complement in hash_map:
                return [hash_map[complement], i]
            hash_map[num] = i

```

---
Original Implementation based on combined understanding of the above solution iterations
```python
def twoSum(givenList, target):
        #This extract comes from the problem statement 

        """
        This extract comes from the problem statement 
        sample list to work on given in the problem 
        Input: nums = [2,7,11,15], target = 9
        Output: [0,1]
        Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
        """

        # start with an empty dictionary bucket { } - this uses the idea of 
        twoSumDict = { }

        # generate a key value pair for the item in the list(same as for index in range len(givenList))
        for listIndex, listItem in enumerate(givenList):

            #find complement for each iteration in the twoSumDict and if complement is absent,
            # store the iteration vaue as a key and its index as a value 

            complement = target - listItem

            if complement in twoSumDict:

                return [twoSumDict[complement],listIndex]

            else:
                 
                twoSumDict[listItem]=listIndex

        return None # if the iteration condition above doesnt yield naything
givenList = [2,7,11,15]
target = 9
        
print(twoSum(givenList,target))  
```
---
121. Best Time to Buy and Sell Stock
---
```python
 def maxProfit(prices: List[int]) -> int:
    maxGap = 0
    left, right = 0, 1
    while right < len(prices):
        if prices[left] < prices[right]:
            maxGap = max(maxGap, prices[right] - prices[left])
            right += 1
        else:
            left, right = right, right + 1

    return maxGap

```
---
169. Majority Element
---
```python



class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        freq_map = {}
        for num in nums:
            if num not in freq_map:
                freq_map[num] = 0
            freq_map[num] += 1
            
        for num, freq in freq_map.items():
            if freq > len(nums) // 2:
                return num

```
---
