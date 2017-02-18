# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: "Naked Twins" heuristic helps us to reduce search space by applying idea similar to combined
   "only_choise" and "eliminate" strategies. The same effect as with "Naked Twins" could be achieved
   by doing one step of depth-search on one of twins elements and then doing elimination two times.
   "Naked Twins" helps to avoid depth-search in this case by doing elimination not for fixed element in a unit,
   but for a fixed pair in a unit. When we apply "Naked Twins" strategy we iterate over all units (unit is a 3x3
   block, diagonal, vertical column or horizontal row, each unit is 9 elements), in each unit we are
   looking for a pair of boxes such that each box contain exactly the same pair of probable digits, if
   such group exists we eliminate digits from the pair from all other boxes in a unit.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: We solve diagonal sudoku problem by adding 2 more constraints. As a result for some of boxes
   list of peers is extended and thus increased number of constraints. We define constraints by
   defining groups (= units) of boxes (boxes = elements of sudoku grid) to have only one box
   with each unique digit. In default sudoku units are: each horizontal row, each vertical column, each
   block of 3x3 boxes, so that each individual box is included into exactly 3 different units. Diagonal
   sudoku has 2 additional units: main diagonal (from left top to right bottom) and secondary diagonal
   (from top right to bottom left). To solve diagonal sudoku we should update each reduction strategy
   (only_choise, elimination, naked_twins) to also check uniqueness constraints for main and secondary
   diagonals. In the code change is trivial, just an update the code where list of different units is computed
   and a dictionary of neighbour boxes is computed.

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