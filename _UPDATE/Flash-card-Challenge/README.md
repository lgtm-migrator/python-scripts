# Project

    Write a flash card quizzer from scratch

## Goals:

- practice breaking down a problem and solving it in Python from scratch
- practice command line option parsing
- practice reading from files
- practice working with dictionaries and for loops

## Problem statement:

    Write a Python script that takes a file containing flash card questions and answers as an argument
    and quizzes the user based on the contents of that file until the user quits the program. Questions
    should be selected randomly (as opposed to going in order through the file), and the user should
    type in their guess. The script should say whether or not a guess is correct and provide the correct
    answer if an incorrect answer is given.

    The file will contain flash card challenges in the form:

```
	question,answer
	question,answer
	question,answer
	question,answer
	...
```

    For example, a state capitals flash card file might have the form:

```
	Alabama,Montgomery
	Alaska,Juneau
	Arizona,Phoenix
	...
```

    Running the quizzer script with this file might look like this:

```
	$ python quizzer.py state_capitals.txt
	Texas? Austin
	Correct! Nice job.
	New Mexico? Santa Fe
	Correct! Nice job.
	Oregon? Portland
	Incorrect. The correct answer is Salem.
	Virginia? Richmond
	Correct! Nice job.
	Virginia? Exit
	Goodbye
```

## Breaking down the problem

### Step 1: Get the questions from a fixed flash card file

    Download: http://web.mit.edu/jesstess/www/IntermediatePythonWorkshop/state_capitals.txt

    Write the code to open and read state_capitals.txt (we'll deal with getting a variable
    filename from the user later). Create a dictionary, where each comma-separated question and
    answer become a key and value in the dictionary. Note that each line in the file ends in a
    newline, which you'll need to remove from the word.

Step 1 resources:

- File I/O: http://docs.python.org/tutorial/inputoutput.html#reading-and-writing-files
- Stripping characters (like whitespace and newlines) from a string: http://docs.python.org/library/stdtypes.html#str.strip

### Step 2: Randomly select questions from the question dictionary

    Write a while loop that loops forever and at each iteration through the loop randomly
    selects a key/value pair from the questions dictionary and prints the question.

    To randomly select a key from the dictionary, you can use the random module, and in
    particular the random.choice function.

    When you run your script, to break out of the while loop you can press Control and then
    (while still holding down Control) c.

Step 2 resources:

- While loops: http://en.wikibooks.org/wiki/Python_Programming/Flow_control#While_loops
- Dictionary manipulation: http://docs.python.org/tutorial/datastructures.html#dictionaries
  In particular, look at getting a list of the dictionary's keys using the keys method.
- Selecting a random value from a list using the random module: http://docs.python.org/library/random.html#random.choice

### Step 3: Get and check the user's answer

    Inside your while loop, write the code that gets an answer from the user and compares it to
    the answer retrieved from the questions dictionary. If the answer is correct, say so. If
    the answer is incorrect, say so and print the correct answer.

    You can get input from a user using the raw_input function.

    It is up to you how strict you want to be with a user's answer. Do you want capitalization
    to matter?

Step 3 resources:

- using raw_input to get data from the user: http://docs.python.org/library/functions.html#raw_input

### Step 4: Allow the user to quit the program

    The while loop currently runs forever. Pick a special phrase (like "Exit") that the user
    can type instead of an answer that signals that they want to quit the program. When that
    special phrase is given, print a goodbye message and break out of the while loop to end the
    program.

Step 4 resources:

- Using the break keyword to break out of a loop: http://docs.python.org/tutorial/controlflow.html#break-and-continue-statements-and-else-clauses-on-loops
- Making decisions with if, elif, and else: http://docs.python.org/tutorial/controlflow.html#if-statements
  Step 5: Get the quiz questions file from the user

  Write the code to get the quiz questions file from a command line argument. Handle the case
  where a user forgets to supply a file; in this case, print an error message saying they
  need to supply a file, and then exit the program using the exit() function.

Step 5 resources:

- Command line argument parsing: http://docs.python.org/library/argparse.html#module-argparse
- Getting and checking the number of command line arguments: http://docs.python.org/library/sys.html

<FINISHED>
