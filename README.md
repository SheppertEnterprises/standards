# Python Coding Standards Comptus

In your README.md write at the top: "written to comptus standards"


# Directory Structure

The top directory should contain (and only contain) the following files/directories:

1. README.md
a file that explains the purpose of the project, and relevant information on how to use.

2. modules
This directory will contain all of the meat of the python code

3. data
This direcotry will contain all of the databases, saved files, json, etc.

4. main.py
Running this file will run the entire program but it is a file that contains almost no code, simply imports and runs functions from other modules.

5. config.py
OPTIONAL. In this file will rest all of the configuration if necessary.

6. other python files
OPTIONAL. If there are multiple programs that use the same modules, another file similarly written to main.py can exist in the top directory. For example, you have two flask applications that use the same bulk of the code. (rarely should this exist)

7. logs
OPTIONAL. This folder should contain all of the logs and output that the program spits out. This can be separated into directories if desired.

Nothing else (hidden files are okay ie .gitignore) should exist in the top directory, it should be clean.

# Coding Practices
  a. No code should be written twice. You should never be copying and pasting code, always import the function. If you find yourself wanting to copy and paste a function so that you can edit it to serve a different purpose, rethink that function and pass in parameters so that it can be used in both ways. When we debug/update code later, having copied code that has been slightly edited is a nightmare.
  
  b. Use a lot of commenting, but be succint in your notes.
  
    i. every function needs an explanation of what type of input it takes, and what it outputs from that input.
    
    ii. every variable that isn't obvious from the name needs an explanation on declaration
    
    iii. Code should be broken down into sections, and each overarching section should be declared and explained in a comment.
 
  c. Very rarely should a python file be longer than 200 lines (including comments). Functions should be sorted into files in a directory structure that makes sense to you and is explained in the README.md. If you find a single function becoming 200 lines and therefore requiring a file to be longer than 200 lines, most of the time what you are trying to do will make more sense to another coder if they see it broken down into smaller functions and sorted into directories rather than digging through a 2000-line file.
  
  d. Anytime code isn't optimized, a note should be made in the comments AND in the README about where it lacks optimization. ie. modules.loop.py should be multithreaded, but it isn't yet. It's okay to write code that isn't optimized, but if you realize that this is what you are doing, make a note of it.
  
  e. Try/Except should only ever be used when a specific error is named. Excepting general errors can be used for debugging purposes, but building on top of that to production often results in code that doesn't work the way we want it to.
  
  f. Global variables should never be used. If a configuration file exists, the parameters within should be passed in main.py as a parameter into other functions. Modules should never be importing anything from a configuration file, the functions therein should be as standalone as possible, and only rely on parameters passed in for configuration. This is extremely important for scaling and building new modules, as it allows us to clearly understand the inputs and outputs of functions.
