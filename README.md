Summary exercise in Linux
Purpose:
●Operating system commands
Flow control
●Operators
●Functions
●Input/output to files
●Algorithmic thinking
Automation (task 2)
Task 1
General description:
In this exercise you will manage a record collection.
Each record has a unique name, and there may be more than one copy.
To manage the collection the following actions must be performed

Adding a record
Deleting a record
Search by name or part of it
Name update
Quantity update
Printing a total amount of records (summary of the amount of copies)
Printing the collection in a sorted manner
An orderly exit
Remarks:
The software must be planned in advance in a modular way, pay attention to the following points:
○ Code reuse (using functions)
○Attention to scoping - the familiarization spaces of variables (local and global)
○ Designing interfaces - how functions “talk” to each other.
○ Ease of maintenance and modification of the code
○Reasonable documentation
○Make sure that the names of functions and variables are clear and informative
●Each operation is implemented as a separate function and the entire software must be planned by dividing the functions and auxiliary functions.
● Must be implemented using as many operating system commands as possible.
● Must be realized with the help of as many auxiliary functions as possible.
The collection will be recorded in a text file with a tabular structure of two fields separated by a comma:
Attention Attention, the record file will be checked automatically, make sure that its structure is exactly the same
For the structure specified here!
RECORD_NAME, AMOUNT
●The name of the file that saves the data will be given as an external argument in the command line
scriptName recordFileName
●Any operation performed on the collection will be accompanied by a log file. Please note that the log is checked in a way
Automatic Make sure that the structure is aligned exactly with the structure specified here!
Input must be checked and error messages displayed on incorrect input (for example):
Input tests of the external arguments (exit with a message explaining the activation of the program)
●Menu options, an error and a request for re-input should be displayed
●The disc name field can only contain letters, numbers and spaces
●The number of records field can only contain whole and positive numbers.
● Pay attention to the user interface
○Clear and user-friendly language
○Response to all the required functionality (including an orderly exit)
○ Outputs about the success of an operation and an error in a way and in a language that is understandable to me
mortal.
planning:
It is recommended to plan some main functions before other main functions.
It is recommended to divide main functions into sub-functions (auxiliary functions) according to the identification of a certain behavior
common
As mentioned, implement as many auxiliary functions as possible.
The auxiliary functions must be designed as functions with one and only function and avoid closed functions that know
do everything
When planning functions, the following points should be considered:
What is the role of the function.
What is its input – is it passed through arguments or user input.
What are the “effects” of the function (saving to a file, displaying output to the user, etc.)
 What are the returned values ​​of the function.
Plan as much as possible on a sheet of paper using flowcharts and pseudo-code (you are expected to present the
your planning sketches).
A page and a pen are recommended and there is no need to be careful about the aesthetics and visibility of the drawings.
Your design should show
 the conduct of the program at the higher level (the menu algorithm)
Management for each option in the menu (algorithm for each main function).
Management of each sub-function. (algorithm for each auxiliary function)
The transfer of information to and from each function must be shown (input and output of a function can be
parameters and return value and also input from the user)
When designing the algorithm for each function, the following points should be considered
 Is the order of the instructions to solve the problem correct?
Are the instructions unambiguous?
Has I/O been configured correctly?
Has a clear end point been defined for the algorithm.
Main functions:
Attention - it is recommended to implement certain main functions before other main functions.

Adding a record. Parameters: name of the record, quantity
This function will add a record or update an existing record
○If there is more than one record matching the search result, a numbered menu with names will be displayed
The results of the candidates, and by typing an appropriate number, the corresponding record will be selected for addition. (Please note
The proposed menu will also have an option to add the search value itself as a new record)
○In case a record does not exist at all, a line will be added to the end of the file if the record does not exist
(hint: search did not return a result)
○ If it exists, the amount of records in the relevant record will be updated (without rewriting of
the file)
○At the end, a message will be displayed about the success of the task, a log file and a return to the main menu.
Deleting a record. Parameters: name of the record, quantity
This function will remove a record or update an existing record
○If there is more than one record matching the search result, a numbered menu will be displayed with the names of the results
the candidates and by typing an appropriate number, the corresponding record will be selected for deletion.
○If there are copies left, the amount of records in the relevant record will be updated (without writing
reloading the file)
○If there are no copies left, the record will be deleted without leaving a space line.
○An error message will be given if the record does not exist (hint: search did not return a result)
○An error message will be given if the quantity exceeds the existing one.
○At the end, a message will be displayed about the success or failure of the task, a log file and a return to the main menu.
Name update. Parameters: old name, new name.
This function will update a record name in an existing record
○If there is more than one record matching the search result, a numbered menu with names will be displayed
the results of the candidates and by typing an appropriate number, the record corresponding to the update will be selected
○An error message will be given if the record does not exist (hint: search did not return a result)
○At the end, a message will be displayed about the success or failure of the task, a blog entry and a return to the main menu.
Quantity update. Parameters: name, quantity
This function will update a quantity of records in an existing record
○If there is more than one record matching the search result, a numbered menu with names will be displayed
the results of the candidates and by typing a suitable number the record corresponding to the update will be selected.
○An error message will be given if the record does not exist (hint: search did not return a result)
○An error message will be given for an amount smaller than 1
○At the end, a message will be displayed about the success or failure of the task, a blog entry and a return to the main menu.
Printing a total amount of records. Parameters: None
This function will scan the file and summarize the total number of records in the database (total number of copies)
○If the total operation was successful and is greater than zero, a message must be displayed to the user about the amount
the records.
○If there are no records in the database, a customized and different message will be displayed
○At the end, a blog will be registered that includes the result and a return to the main menu.
Printing the collection in a sorted manner. Parameters: none
This function will print the file in lexicographic order (lexical order) according to the names of the discs
○If there are records in the database, the names and quantities of the entire database will be printed in a sorted manner
○If there are no records in the database, an adapted and different message will be displayed
○At the end, a blog will be registered that includes the result and a return to the main menu.
Writing to the log. Parameters: the event that happened and whether it ended successfully or failed and relevant values
for printing
This function will write the current event to a log file.
○Please note, the log will be checked automatically, make sure that the structure is aligned exactly with the structure
specified here!
○The file name will consist of the log file name, an underscore and the word log
recordFileName_log
○Each blog line indicates one event, and includes the date, time, name of the event and whether it ended
Good luck (except printing events)
example:
○ 28/2/2022 16:30:50 Insert Success
○Success/Failure
i. Failure
ii. Success
○ Name of the event:
i. Insert
ii. Delete
iii. Search
iv. UpdateName
v. UpdateAmount
vi. PrintAmount
vii. PrintAll
○Print events:
i. For quantity printing, the name of the event and the quantity of records (including 0) will be printed
○ 2/28/2022 16:50:47 PrintAmount AMOUNT
i. For printing the collection, blog lines will be printed as the number of records:
○ 28/2/2022 16:47:52 PrintAll RECORD_NAME1 AMOUNT
○ 28/2/2022 16:47:52 PrintAll RECORD_NAME2 AMOUNT
○ 28/2/2022 16:47:52 PrintAll RECORD_NAME3 AMOUNT
○ 28/2/2022 16:47:52 PrintAll RECORD_NAME4 AMOUNT
