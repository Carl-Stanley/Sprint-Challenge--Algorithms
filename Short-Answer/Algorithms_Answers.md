#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a) O(n) There is a 1 loop that will terminate based on how many times it increments A to equal N. Then the runtime for this psuedocode will grow the same rate as N. If N is 1 the loop will only have to run 1 time. If N is 2, the it will loop 2 times. If N is 10, it loops 10 times. Then continues....



b) O(n^2) - would be O(n log n) looping through the same input list twice with the for and while loops, then this makes this code block an O(n^2) solution. The runtime for this code will grow exponentially as the number of inputs increase and probably isn't a good solution if the numbers of inputs will be a large number. For instance if n is 2, this loop will only need to run 1 time. If n is 4, the loop will need to run 8 times. If n is 10, will need to run 40 times. If n is 25, this loop will run 125 times. You can see the runtime is increasing at a much faster rate than the rate than n increases.



c) O(n) This is a recursive solution , and it loops based on the number of bunnies. Based upon the number of bunnies we have (n) will determine how many times we have to call this function. We can test this by increasing our number of inputs and checking how many times the function is called. With 2 bunnies we will notice the function is called 2 times. If we input 4, we will notice the function is called 4 times. Same with 10 bunnies, we loop through the function 10 times.


## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode AND give the runtime complexity of your solution.

A list of floors, with eggs dropping?

Check the length of n. If it's less than or equal to 1 return the value of n Find the halfway point in your list. Divide the list at the halfway point into 2 lists. If thee floor we are in is in the first list, call the egg drop function and start all over again with the first half of the list. If we are on a floor in the second list, call the egg drop function and start with the second half of the list.

Runtime: O(log n). The code appears to process in an efficient manner. The Difference of inputs is huge, but the rate of our runtime is not increasing at the same rate of our input. It is growing some though which is why it should not be set as O(n).


Code or Psuedocode:


def egg_drop(n, f):
    if len(n) <= 1:
      return n
    
    mid = len(n)
    x = n[:mid]
    y = n[mid:]
    if f <= x[-1]:
      return egg_drop2(x, f)
    elif f >= y[0]:
      return egg_drop2(y, f)
    else:
      return "No such floor exists in the building!"

