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

