# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: In Constraint Propagation we are using local constraints in a space, in this case, the constraints of each square,
 in order to dramatically reduce the search space.
  In this solution in addition to the constraints of "eliminate" and "only choice" we used also the naked twins.
  In the naked twins technique, we found every place where there are 2 squares in the same unit with length of 2 and have the same value,
  (the value is digits that represent the current possibilities we found for the square)
  In those cases, we can be sure that those 2 digits of the twins can't be in  the value of any other square of their shared unit,
  so we can remove those 2 digits from all of the twins common peers(which means they are in the same unit as both of the twins),
  and by doing so we reduce the search space and improving the Constraint Propagation process which we started by "eliminate" and "only choice".


# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: In order to use constraint propagation to solve the diagonal sudoku problem we just need to execute all the constraints which we run on the regular sudoku units (rows, cols, square units) also on the 2 new units the 2 diagonal.
In practice, we just have to add 2 new units to the unitlist which also changes the dictionary of units / peers respectively.
Now, after this change, because all our constraints are running on the unit/peers level, they will run automatically on the 2 new diagonal's units, so in this way, we actually added the diagonals to the sudoku set of constraints.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solution.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Submission
Before submitting your solution to a reviewer, you are required to submit your project to Udacity's Project Assistant, which will provide some initial feedback.  

The setup is simple.  If you have not installed the client tool already, then you may do so with the command `pip install udacity-pa`.  

To submit your code to the project assistant, run `udacity submit` from within the top-level directory of this project.  You will be prompted for a username and password.  If you login using google or facebook, visit [this link](https://project-assistant.udacity.com/auth_tokens/jwt_login for alternate login instructions.

This process will create a zipfile in your top-level directory named sudoku-<id>.zip.  This is the file that you should submit to the Udacity reviews system.

