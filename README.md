[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/tqM-lrvp)
# CMPS 2200  Recitation 01

**Name (Team Member 1):** Jaret Solomon 


In this recitation, we will investigate asymptotic complexity. Additionally, we will get familiar with the various technologies we'll use for collaborative coding.

To complete this recitation, follow the instructions in this document. Some of your answers will go in this file, and others will require you to edit `main.py`. All tests are in `test_main.py`.

## Install Python Dependency

We need Python library of "tabulate" to visualize the results in a good shape. Please install it by running 'pip install tabulate' or 'pip install -r requirements.txt' in Shell Tab of Repl.  

## Running and testing your code

- To run tests, from the command-line shell, you can run
  + `pytest test_main.py` will run all tests
  + `pytest test_main.py::test_one` will just run `test_one`
  + We recommend running one test at a time as you are debugging.

## Turning in your work

- Once complete, click on the "Git" icon in the left pane on repl.it.
- Enter a commit message in the "what did you change?" text box
- Click "commit and push." This will push your code to your github repository.
- Although you are working as a team, please have each team member submit the same code to their repository. One person can copy the code to their repl.it and submit it from there.

## Comparing search algorithms

We'll compare the running times of `linear_search` and `binary_search` empirically.

`Binary Search`: Search a sorted array by repeatedly dividing the search interval in half. Begin with an interval covering the whole array. If the value of the search key is less than the item in the middle of the interval, narrow the interval to the lower half. Otherwise, narrow it to the upper half. Repeatedly check until the value is found or the interval is empty.

- [ ] 1. In `main.py`, the implementation of `linear_search` is already complete. Your task is to implement `binary_search`. Implement a recursive solution using the helper function `_binary_search`. 

- [ ] 2. Test that your function is correct by calling from the command-line `pytest test_main.py::test_binary_search`

- [ ] 3. Write at least two additional test cases in `test_binary_search` and confirm they pass.

- [ ] 4. Describe the worst case input value of `key` for `linear_search`? for `binary_search`? 

the worst case input value of key for linear search is the value at the last index or if the value is not within the list. This requires the search to check all possible indexes.

The worst case input value of key for binary search is a value that is not within the list causing the algorithm to continuously halve and search for a value until empty. The other worst case is if the value is at the inner most position in the search tree, producing the same result as if the value was not present.

- [ ] 5. Describe the best case input value of `key` for `linear_search`? for `binary_search`? 

the best case input value for linear search is if the key value is at the first index. The linear search begins from the first element and stops at the first element.

the best case input value of key for binary search is the value at mid = left + (right - left) // 2. This would only use one comparison before exiting and returning the value.

- [ ] 6. Complete the `time_search` function to compute the running time of a search function. Note that this is an example of a "higher order" function, since one of its parameters is another function.

- [ ] 7. Complete the `compare_search` function to compare the running times of linear search and binary search. Confirm the implementation by running `pytest test_main.py::test_compare_search`, which contains some simple checks.

- [ ] 8. Call `print_results(compare_search())` and paste the results here:

|            n |   linear |   binary |
|--------------|----------|----------|
|       10.000 |    0.001 |    0.003 |
|      100.000 |    0.003 |    0.001 |
|     1000.000 |    0.025 |    0.001 |
|    10000.000 |    0.256 |    0.002 |
|   100000.000 |    2.520 |    0.003 |
|  1000000.000 |   22.217 |    0.008 |
| 10000000.000 |  223.674 |    0.044 |



**TODO: add your timing results here**

- [ ] 9. The theoretical worst-case running time of linear search is $O(n)$ and binary search is $O(log_2(n))$. Do these theoretical running times match your empirical results? Why or why not?

These results match my empirical results because linear search increases linearly as n gets larger

//create graph with n as x and linear/binary as y




- [ ] 10. Binary search assumes the input list is already sorted. Assume it takes $\Theta(n^2)$ time to sort a list of length $n$. Suppose you know ahead of time that you will search the same list $k$ times. 
  + What is worst-case complexity of searching a list of $n$ elements $k$ times using linear search? 

  linear_search worst case—when the key is not in the list—the time complexity is O(n)
  
  
  + For binary search? worst case—when the key is in the inner most part of the list, or not in the list—the time complexity is $O(log_2n)$
   
  + For what values of $k$ is it more efficient to first sort and then use binary search versus just using linear search without sorting? **TODO: your answer goes here**


When searching a list of length n, unless the value k is in the beginning of the list, it is more efficient to sort the list and use binary search. The time complexity of these cases is linear_search being $O(n)$ and Binary_search being $O(1)$. However if the value k is in the beginning of the list, it is more efficient to use linear search rather than sort and use binary search. The time complexity of these cases is being linear_search $O(1)$ and Binary_search being $O(log_2n)$.



previous answers:

{ 
when K is the smallest or largest in the list, sorting and then using binary search ($O(log_2n)$) is more efficient than linear search in an unsorted list($O(n)$).

when searching a list from smallest to largest and the key is smallest or largest in the list, it is most efficient to use binary search, because the worst time complexity of linear search is $O(n)$. And Binary search for this same list would be $O(log_2n)$ which is more efficient than $O(n)$. 
} 



