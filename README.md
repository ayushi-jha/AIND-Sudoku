# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: The naked twins problem occurs when there is a pair of boxes in one unit (horizontal, vertical or square) which have the same two potential values. In such a case, each of the box in the pair is guaranteed to have one of only those two potential values, meaning that if one box takes the first potential value, the second box has to take the second potential value (as that is now the only value remaining with the second box) and vice versa. Considering expansion of tree in either case - where first potential value is taken by first box and second by second box, or second potential value is taken by first box and first by second box, it is evident that these potential values will never occur in any of the remaining boxes of the same unit. Thus, we can reduce our problem if we eliminate these two potential values from the remaining boxes. For example, if we consider the unit A1 to A9 (first horizontal row), and let's say that boxes A3 and A5 are 67, and box A7 is 1267. We know that 6 and 7 can only occur in A3 and A5 (A3 = 6 and A5 = 7 OR A3 = 7 and A5 = 6), so we can safely say that A7 will not have either 6 or 7, and thus eliminate 67 from A7. This is the naked twins problem, and with this constraint we can reduce the sudoku puzzle further.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: To solve the diagonal sudoku problem, we need only add a single extra constraint to take care of the diagonals of a sudoku. The diagonals of a sudoku can be considered as two units, and in simple terms can be denoted as "diag_units = [['A1','B2','C3','D4','E5','F6','G7','H8','I9',],['A9','B8','C7','D6','E5','F4','G3','H2','I1']]". This list consists of two diagonals, the first diagonal is from A1 to I9, and the second diagonal is from A9 to I1. This list can be added to the unitlist, which is a list of all units - horizontal, vertical and squares. So for the diagonal sudoku problem, only the constraint of the . 

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.