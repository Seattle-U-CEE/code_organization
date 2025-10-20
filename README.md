# **Impromptu lesson on organizing code (written quickly because Canvas isn’t working)**

**Code repositories**  We have a place for storing code for this project on GitHub.

You should separate into groups of 2, then create a code repository by accepting the Github Classroom invitation at a website I will provide.  I HOPE you are able to create private repositories each of which has three members, me and your two team members.

# Classes

Classes group data and functions into logical groupings. Specific grouped instances are referred to as objects.  Classes provide tools (e.g., the __init__ function) to help you keep your data and methods organized.

**Example**  See example at [https://realpython.com/python3-object-oriented-programming/](https://realpython.com/python3-object-oriented-programming/)

### Discussion questions:

What is the difference between a class and an object?

If you wanted to create an object that has a specific property that might be different from properties of other objects in the class, how would you pass this property to the object?  Would you use a class variable or an instance variable?

If you want to define what is displayed on the screen when you “print()” an object, what do you need to do?

What is the term “self” used to represent?  Is it an object or an instance?  

# Organizing Code using Modules

You can import functions, variables, and classes using modules.  Modules are folders that include a file called __init__.py.  Importing the folder then allows you to also import any of the sub-modules in the folder (so the individual .py folders).  If organized as a class, then you can import the classes. You’ll typically have a __main__.py function that will run when you start the name of the module from the command line.  For instance, __main__.py usually includes a main() function that runs automatically and controls program operation.  The advantage is that if you just “Import” the module, nothing runs—but you can still run something from the command line.

Example built-in modules you will use in this project:

## threading.Timer

this allows you to call a function periodically. The Timer object passes the appropriate parameters to the function call after a set interval.  The start() method starts the countdown. In our code, it is implemented by calling a function that calls itself, meaning the same thing happens at regular intervals. Other code can operate in the meantime.  It is used to 1) change state of an LED (so to blink), 2) monitor the button, and 3) update the time for the clock.

## global
Defines a variable as a global variable, meaning your objects and methods have access to it even if it isn’t passed. This is a bit scary, BTW, but it can be helpful.

## ArgumentParser

ArgumentParser is an object that provides methods for passing arguments to the program when you start the program from the command line.  For example, you can start your program with the built-in -h argument, indicating that you want help on the arguments for the program.

**To use**: from argparse import ArgumentParser

Then, at the command line:

">>> program.py -h

this will then go through the add_argument lines and give you all the help=’message’ messages.  You should add_argument to define all the messages you can pass to start the program in a different mode.  In the example code, there is already a message for starting in timer mode or stopwatch mode.  You’ll need to use the data that is passed when starting in timer model.  Look at the way the clock gets the initial time for clock mode and implement something similar for the timer. Note that it can be particularly helpful to define what is going on in the __init__ function of the method.

## Documenting your code with Docstrings

It is VERY helpful to define what is going on in all your objects and methods using docstrings (that is, text delineated by the three apostrophes, ‘‘‘ ’’’).

There are different formats for docstring documentation.  I recommend using Google format (see [https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html))

The basic idea is that a doc-string comes at the beginning of the file, after a comment line, then at the beginning of each class, function, or (in some cases) variable defined in the program. The docstring at the beginning of the program describes in general, in one line, what it does, then provides a multiple line elaboration, then provides an example of useage, then defines attributes.  It is good practice for the basic doc-string to define the variable and intended type in the Attributes: section.  This can be done at the variable level, but I think it makes more sense to do it at the module, class, and/or function level.

Each function or class would have a one-line description (on the same line as the ‘’’) then a multiple line description, then a list of arguments in the Args: section, then a list of what is returned in the Returns: section.  Handle the methods inside the class like you handle functions above.

**Examples of how I’ve used these are here:**

[https://github.com/jwlauer/CTD/blob/master/pyboard/conductivity4pole.py](https://github.com/jwlauer/CTD/blob/master/pyboard/conductivity4pole.py)

[https://github.com/jwlauer/CTD/blob/master/pyboard/logger_ctd.py](https://github.com/jwlauer/CTD/blob/master/pyboard/logger_ctd.py)

[https://github.com/jwlauer/EnvironmentalSensing/blob/master/Pressure/ms_pressure.py](https://github.com/jwlauer/EnvironmentalSensing/blob/master/Pressure/ms_pressure.py)

## Flowcharting.

It can be critical to visually represent your code logic using a flowchart.  This reference provides a description of the basic symbols.

[https://www.geeksforgeeks.org/competitive-programming/an-introduction-to-flowcharts/](https://www.geeksforgeeks.org/competitive-programming/an-introduction-to-flowcharts/)

You can create one using an online tool at the following site:

[https://app.diagrams.net/](https://app.diagrams.net/)

You should work with your teammate to develop a flowchart of the implementation of your stopwatch and timer functions on the clock.
