
# CS 61A: The Structure and Interpretation of Computer Programs

## Miscellaneous Resources

### Tree Recursion
Check out this link for more tree recursion practice: https://practice.geeksforgeeks.org/topic-tags

1. Given a number n, generate all distinct ways to write n as the sum of positive integers. For example, with n = 4, the options are 4, 3 + 1, 2 + 2, 2 + 1 + 1, and 1 + 1 + 1 + 1.
2. Write a recursive function that checks whether a string is a palindrome (a palindrome is a string that's the same when reads forwards and backwards.)

3. Write a procedure that computes elements of Pascal's triangle by means of a recursive process. Define the procedure pascal(row, column) which takes a row and a column, and finds the value at that position in the triangle.

4. Consider the subset_sum problem: you are given a list of integers and a number k. Is there a subset of the list that adds up to k?

5. We will now write one of the faster sorting algorithms commonly used, named Mergesort. Merge sort works like this:
	
	a. If there’s only one (or zero) item(s) in the sequence, it’s
	already sorted!
	b. If there’s more than one item, then we can split the sequence in
	half, sort each half recursively, then merge the results (using the
	merge procedure from earlier in the notes). The result will be a	sorted sequence.

Using the described algorithm, write a function mergesort(s) that takes an unsorted sequence s and sorts it.

6. Complete the definition of towers_of_hanoi which prints out the steps to solve this puzzle for any number of n disks starting from the start rod and moving them to the end rod.

```python
def towers_of_hanoi(n, start, end):
	…

def move_disk(start, end):
	…
```

7. Implement Binary Search recursively.

### The Link Class (given on exam)

```python
class Link:	
	def __init__(self, first, rest=empty):
        assert rest is Link.empty or isinstance(rest, Link) 
        self.first = first
        self.rest = rest
	
def __repr__(self):
    if self.rest is Link.empty:				
        return "Link({})".format(self.first)				
    else: 					
        return "Link({}, {})".format(self.first, self.rest)
```

### The Link Class (customized)

```python
class Link:
    def __init__(self, first = None, rest = None):
        self.first = first
        self.rest = rest
        
    def __repr__(self):
        # empty link ---> None 
        if self.first == None:
            return "()"
        else:
            return 'Link' + '(' + str(self.first) + "," + self.rest.__repr__() + ')'
            
    def multiply(self, n):
        if self.rest.first == None:
            self.first = n * self.first
        else:
            self.first = n * self.first
            self.rest.multiply(n)
            
    def a_multiply(self, n):
        # if self == Link.empty
        if self.rest.first == None:
            return Link(self.first * n)
        else:
            return Link(self.first * n, self.rest.a_multiply(n))
            
    def skip_node(self, n = 1):
        if self.first == None:
            return Link()
        elif self.rest.first == None:
            return Link(self.first, Link())
        else:
            return Link(self.first, self.rest.rest.skip_node(n))
        
        
x = Link(5, Link(7, Link(9, Link(6, Link(8, Link())))))
y = [5,7,9,6]
print(x.a_multiply(3))
print(x)
print(x.skip_node())
```

### Additional Link Problems

Note 1: The term ‘list’ refers to linked list.
Note 2: You may use methods you have created in the previous problems to support your code for later problems.

Create a method that…  
1. adds an element to the beginning of the list (mutator)
	variant: deletes an element from the beginning and returns it
2. adds an element to the end of the list (mutator)
	variant: deletes an element from the end and returns it
3. returns a new linked list that skips ‘n’ nodes from the original linked list
4. counts the number of times an element occurs in the list
5. ‘deletes’ all instances of an element from the list
6. insert element at the nth position (mutator)
7. takes a sorted list and inserts an element in the sorted position (mutator)
8. given a list, returns a new list that contains all of the nodes in sorted order
9. appends the elements of another linked list onto the end of the original one
10. find the length of the longest consecutive sequence of elements that is strictly increasing
11. remove all duplicates from a sorted list
12. reverse the order of the elements in the list
13. Refer to this Stanford link and this interview problems link for more problems.

### OOP

Source: https://stackoverflow.com/questions/245800/oop-problems-to-use-for-coding-tests-during-interviews

1) Create model classes that will properly represent the following constructs:
<br>
Define a Shape object, where the object is any two dimensional figure, and has the following characteristics: a name, a perimeter, and a surface area.
<br>
Define a Circle, retaining and accurately outputting the values of the aforementioned characteristics of a Shape.
<br>
Define a Triangle. This time, the name of the triangle should take into account if it is equilateral (all 3 sides are the same length), isosceles (only 2 sides are the same length), or scalene (no 2 sides are the same).
<br>
Continue with the quadrilaterals!



2) We need to control access to a customer web site.
<br>
each customer may have one or more people to access the site
<br>
different people from different customers may be able to view different parts of the site
<br>
the same person may work for more than one customer
<br>
customers want to manage permissions based on the person, department, team, or project
<br>
Design a solution for this using object-oriented technique.



3) (Are you smarter than a CS Grad?) Write a program that prints the numbers from 1 to 100. But for multiples of three print "Fizz" instead of the number and for the multiples of five print "Buzz". For numbers which are multiples of both three and five print "FizzBuzz."



4) Make a rough class diagram of the game Pacman. What classes would you need? What class / instance variables are necessary? Would some classes depend on the others?

### Tree Data Structures
Source: https://www.careercup.com/page?pid=trees-and-graphs-interview-questions

Directions: For each problem, write a new method for the Tree class. You can only use the methods already given or a method from the problems above.

```python
class Tree:
	
	def __init__(self, label, branches):
		self.label = label
		self.branches = branches

	def is_leaf(self):
		if not self.branches:
			return True
		return False

	def branches(self):
		return self.branches

	def label(self):
		return self.label
```

1. Minimum tree height (i.e. shortest branch from root node)
2. Largest integer value in the tree
3. Are two trees equal?
4. Traverse all of the elements of the tree in whatever order you want… using iteration
5. Find the minimum sum of any branch from root to leaf.
6. Find the maximum sum among all elements in the tree (don’t have to be in the same branch).
7. Given a Tree where each node contains an attribute e.g. color (R,G,B... etc), find the subtree with the maximum number of attributes. 

```python
Input: 
G 
/ \ 
B  R 
/ \ / \ 
B B R R 
/ \ / \ 
B R R R 

Output: 
R 
/ \ 
R R 
\ / \ 
R R R
```
