# PathPyinder
PathPyinder is a pathfinding algorithm visualizer written in Python. Currently supported algorithms are Breadth-First Search, Depth-First Search, and the A* (A Star) Algorithm.


## Requirements
1. **Python** - Version 3.6 or higher
2. **[PySimpleGUI](https://pysimplegui.readthedocs.io/en/latest/)** - GUI wrapper library for tkinter. 
Install via: `pip install PySimpleGUI` or `pip3 install pysimplegui`


## Usage
Navigate to the root directory via terminal and launch PathPyinder with: `python pathpyinder.py`. If you have a Python 2.X and a 3.X installation on your machine, you may need to use the command `python3 pathpyinder.py`. The following GUI should open:

![PathPyinder GUI](assets/pathpyinder_gui.png "PathPyinder GUI")

### **Drawing Mazes:**
PathPyinder is interactive, so you can draw your own mazes. There are four types of maze nodes that can be drawn: **Wall**, **Path**, **Start**, **End**. Select which node to draw by clicking the buttons in the *Draw* frame of the GUI, and clicking or dragging somewhere in the maze. You can clear out a maze using the **Clear Maze** button at the bottom left of the interface. You can also fill up the entire grid with wall nodes using **Tools > Fill Maze**.

### **Selecting an Algorithm:**
Use the radio buttons in the 'Algorithm' frame to select which algorithm will be used to solve the maze. Dijkstra's algorithm was originally available as well, but since each node is equally acessible from every other node, the prioritization of routes that Dijkstra's algorithm provides never mattered, and it ended up looking just like Breadth-First Search.

### **Solving Mazes:**
Click the **Solve** button in the *Controls* frame of the GUI to start solving the maze. Keep in mind, a start node and end node have to exist for PathPyinder to attempt solving. You can adjust the speed that the algorithm iterates by using the speed slider. You can also pause the algorithm entirely iterate through it one step at a time using the **Pause** and **Play** buttons under the **Solve** button.

### **Resetting and Clearing Mazes:**
Click the **Reset** button at any time to stop solving, and reset the current maze to it's original, unsolved state.

Click the **Clear** button to stop solving, and erase the entire maze to an empty grid.

### **Saving and Loading Mazes:**
Save and load mazes via **File > Save Maze** and **File > Open Maze** in the menu bar. Mazes are saved as .txt files. There is a `/mazes` directory that includes some pre-built mazes.


## Default Settings
You can change some options that PathPyinder initializes with by editing `settings.txt`. This file has three lines in it, which correspond to:
* **Line 1:** The maze to load on startup. 
Valid values are:
  * `~/user/desktop/full_filepath_to_maze.txt` -> Will load a maze file from the given filepath.
  * `mazes/maze_filename.txt` -> Will load the maze from the relative filepath. Terminal must be in PathPyinder's root directory for this to work.
  * `None` -> Will load an empty grid on startup with default dimensions.
* **Line 2:** The algorithm that will be selected by default: Valid values are:
  * `bfs` -> Start with Breadth-First Search algorithm selected.
  * `dfs` -> Start with Depth-First Search algorithm selected.
  * `astar` -> Start with the A* algorithm selected.
* **Line 3:** The default speed at which the algorithm will run. These correspond to the speed slider. Valid values are:
  * `1`
  * `2`
  * `3`
  * `4`
  * `5`