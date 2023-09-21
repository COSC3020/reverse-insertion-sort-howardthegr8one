[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-718a45dd9cf7e7f842a935f5ebbe5719a5e09af4491e668f4dbf3b35d5cca122.svg)](https://classroom.github.com/online_ide?assignment_repo_id=11908392&assignment_repo_type=AssignmentRepo)
# Reverse Insertion Sort

Consider the code for insertion sort we covered in class:

```javascript
function insertionSort(arr) {
  for(var i = 1; i < arr.length; i++) {
    var val = arr[i];
    var j;
    for(j = i; j > 0 && arr[j-1] > val; j--) {
      arr[j] = arr[j-1];
    }
    arr[j] = val;
  }
  return arr;
}
```

Change this function such that it works from the end of the array rather than
the beginning, `insertionSortReverse()` -- only the direction of
iterating over the elements is reversed, the array is still sorted the same way
(ascending). Add your code in `code.js`. Test your new function; I've provided
some basic testing code that uses [jsverify](https://jsverify.github.io/) in
`code.test.js`.

## Average-Case Time Complexity of Insertion Sort

In the lectures, we covered that insertion sort has best-case time complexity of
$\Theta(n)$ and worst-case time complexity of $\Theta(n^2)$. What is the
average-case time complexity ($\Theta$)?

Hint: Think about what happens in each iteration of the loop, and how often the
loop is executed. Keep in mind that for asymptotic analysis we don't care about
constant factors.

Describe your reasoning and the conclusion you've come to. Your reasoning is
most important -- you can easily find the answer, but you need to demonstrate
that you've understood the concept. Add your answer to this markdown file.

## My answer to the the average time complexity of Insertion Sort

A worst-case scenario is that the algorithm will ahve to reposition an element
from the end to the very front, therefore having $Theta(n)$ per iteration and
$\Theta(n^2)$ as we have nested for loops. 

The best-case scenario is that the given array is sorted, this results in each
iteration being $Theta(1)$ and the total time being $Theta(n)$ as the algorithm
must iterate through the entire n length of the given array. 

An average-case scenario would have to be an array that is partially sorted
(or completely random but still not sorted) and doesn't have the smallest 
element at the end of the array. This would result inthe algorithm still having
to iterate through nested for loops and thus the average-case would also be 
$Theta(n^2)$. The difference between the worst-case and the average-case is that
although they both have the same asymptotic time complexity, the average-case
scenario would technically be faster in practice. 
