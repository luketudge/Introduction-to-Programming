# Glossary

Like any other specialists, computer programmers use a lot of arcane vocabulary. Although some of this vocabulary could be simplified to everyday words that mean almost the same things, it is worth knowing the following basic technical terms, for a few reasons:

* You are more likely to find the answers to your programming questions in internet searches if you formulate your search using the right terms.
* The answers you find in internet searches will mostly be written using these terms.
* Once you start working in programming, you will need to talk about the workings of your programs with other programmers.

## alias

This term has more or less the same meaning in programming as it does in everyday English. An alias is an alternative name for something. In Python, aliases occur most commonly when [importing](#import) [modules](#module). A module can be imported under an alias instead of under its normal name, using the `as` [keyword](#keyword). We might do this in order to make it quicker to type the name of the module later, or simply as a matter of convention. For example, numpy is often imported under the alias 'np':


```python
import numpy as np
```

## API

Sometimes the developers of computer programs would like their programs to be able to access information from websites or other programs hosted on the internet. For example, someone who is developing a smartphone app for navigating the Paris metro system needs some way for their app to retrieve information about train times from the metro's own [servers](#server). The administrators of the Paris metro's website may provide a structured method by which other applications can access its data. Such a method is termed an 'Application Programming Interface' (API). The makers of other apps can then use the rules of the API to submit requests for information, and these requests will be answered in a particular format according to the rules of the API.

## argument

An argument is the input to a [function](#function). When we use a function, we place any arguments that we want to give it in the parentheses following the function name. A function can have no arguments, or just one, or many. In the case of more than one argument, the arguments are separated by commas. For example the `print()` function can have multiple arguments:


```python
name = 'Mildred'
middle_initial = 'L'
surname = 'Bonk'
print(name, middle_initial, surname)
```

    Mildred L Bonk


## array

In computing, a collection of multiple [values](#value) that are organized as a sort of 'grid' is called an array. There is no array [type](#type) in basic Python, but the *numpy* [package](#package) adds arrays to Python.

For example, we could use a numpy array to represent the state of a game of tic-tac-toe as an array of [integers](#integer) indicating whether each square of the game grid has been marked by player 1 (`1`), by player 2 (`-1`), or has not been marked (`0`):


```python
import numpy
ttt = numpy.array([[-1, 0, 1], [0, -1, 0], [1, 0, 1]])
ttt
```




    array([[-1,  0,  1],
           [ 0, -1,  0],
           [ 1,  0,  1]])



This array has two dimensions (rows and columns), but arrays may have more or fewer dimensions. To [index](#index) one or more values from an array, multiple indices may be needed, one for each dimension. By convention, the first dimension is the rows, the second is the columns (though some other programming languages use the opposite convention). So for example to get the first two values from the second row:


```python
ttt[1, :2]
```




    array([ 0, -1])



## assertion

An assertion is a statement that 'asserts' that a particular statement is true, in the same sense of the English verb 'to assert'. If the asserted statement is true, nothing happens and the program may continue as normal, but if it is not true, then an [exception](#exception) is raised.

Assertions can be used to make sure that a program is running as expected at a crucial point, because to continue otherwise would be time-consuming or would make the problem more difficult to diagnose later. Assertions are also commonly used in test programs that check the correct functioning of another program.

There are a few different ways to write assertions in Python, but the simplest is using the `assert` [keyword](#keyword) together with the statement to be checked. For example:


```python
assert 2 + 2 == 4
```

## assignment

If one part of our program generates a piece of information, we may want to store that information and use it in some later part of our program. In this case, we can 'assign' the information into a [variable](#variable). This just means storing something under that variable name. In Python, assignment is done with the equals `=` symbol. Whatever results from the right-hand side is assigned into the variable name on the left-hand side.

## attribute

An attribute is like a variable that is 'attached' to another variable, providing some additional information or functionality. We can access attributes using a `.`. This is the same [syntax](#syntax) as for accessing a [method](#method). Indeed, methods are a kind of attribute.

## boolean

A [variable](#variable) of boolean data [type](#type) (abbreviated to `bool` in Python) stores either of the two possible [values](#value) `True` or `False`. Boolean values often result from a Python command that checks a given condition, for example `2 > 1` [evaluates](#evaluate) to `True` because `2` is indeed greater than `1`:


```python
2 > 1
```




    True



(The term 'boolean' is derived from the name of [George Boole](https://en.wikipedia.org/wiki/George_Boole), who developed various mathematical methods for working with logical True/False values.)

## broadcasting

When working with [arrays](#array), we can apply mathematical operations to two arrays that have the same shape. In this case, the values in the two arrays will be 'matched up' to produce a new array of the same shape whose values are the results of the mathematical operation applied to each pair of values:


```python
import numpy
a = numpy.array([[1, 2, 3], [4, 5, 6]])
b = numpy.array([[7, 8, 9], [10, 11, 12]])
a
```




    array([[1, 2, 3],
           [4, 5, 6]])




```python
b
```




    array([[ 7,  8,  9],
           [10, 11, 12]])




```python
a + b
```




    array([[ 8, 10, 12],
           [14, 16, 18]])



This can work even if one of the arrays is smaller than the other. The smaller array is first repeated (or sometimes we say 'stretched') so that it is equal in shape to the larger array. This is known as 'broadcasting' the smaller array onto the larger one.

For example if we combine an array that is 2 rows by 3 columns with an array that is only 1 row by 3 columns:


```python
c = numpy.array([7, 8, 9])
c
```




    array([7, 8, 9])




```python
a + c
```




    array([[ 8, 10, 12],
           [11, 13, 15]])



## bug

A bug is an aspect of a program that does not work as desired. For example, a [function](#function) might give the wrong [return value](#return), or part of the program might unexpectedly raise an [exception](#exception).

## builtin

Python provides a few fundamental [functions](#function) that are already available from the start. These are termed built-in functions, or 'builtins'. The `print()` function is one example of a builtin. You can read a full list of them [here](https://docs.python.org/3/library/functions.html#built-in-functions).

## call

To 'call' a [function](#function) simply means to run that function and make it do its work. The [syntax](#syntax) for calling a function is to place parentheses `()` after the function name, and optionally to place any input [arguments](#argument) inside the parentheses.

(See the entry on [functions](#function) for an example of a 'function call'.)

## client

A computer, or a program on a computer, that sends out a request over the internet for some information, is called a 'client'. The computer at the other end of the internet connection that supplies the requested information is called the '[server](#server)'. The most common client application on a personal computer is a web browser like Firefox or Chrome.

## coercion

Sometimes, a computer program may convert some values of one data [type](#type) into another data type in order to be able to perform some calculations or operations with those values, even if the user of the program has not explicitly asked for the data to be converted. In this case, we sometimes say that the data have been 'coerced' to a new type.

## comment

A comment is a human-language piece of text that we insert into our Python program. We indicate a comment by prepending the hash character `#`. The Python [interpreter](#interpreter) just ignores any line beginning with a hash character, so we can write whatever we like in our comments; they do not have to be valid Python commands. Comments have a few uses:

* 'headings' to organize sections of the program
* short explanations of how parts of the program work (where this is not otherwise obvious)
* reminders to ourselves and collaborators of problems or parts of the program that need attention

## commit

In [version control](#versioning), 'committing' changes to a project means confirming those changes as the next new part of the project. Used as a noun, a 'commit' refers to all the changes that were made when committing.

When working with a database, 'committing' also refers to writing any current changes to the database.

## comprehension

A comprehension is a technique for creating multiple values by writing a 'formula' that generates those values, instead of writing them all out one by one. The [syntax](#syntax) for a comprehension uses the [keywords](#keyword) `for` and `in`.

A 'list comprehension' creates the items in a new [list](#list). For example, the formula might apply some Python command `for` every entry `in` some other existing list, and store the result in a new list:


```python
shopping = ['eggs', 'bacon', 'black pudding', 'sausages']
[item[0] for item in shopping]
```




    ['e', 'b', 'b', 's']



There are also comprehensions for creating [dictionaries](#dictionary).

## concatenate

In computing, to 'concatenate' means to stick together one after the other. So for example the result of concatenating the [strings](#string) `'Hello '` and `'world!'` is `'Hello world!'`.

## condition

A condition is a [control statement](#control) that ensures that part of our program will run only if a certain statement is true, and optionally what should be run if that statement is false. A condition begins with the [keyword](#keyword) `if`. For example:


```python
if 2 + 2 == 4:
    print('Math is currently working correctly in this universe.')
else:
    print('Nothing is forbidden, everything is permitted.')
```

    Math is currently working correctly in this universe.


## control

'Control' (or sometimes 'flow control') refers to controlling which parts of our program are run under which circumstances. A 'control statement' is a command that determines when a particular part of our program is run. [Indentation](#indentation) is used to mark which lines of the program are controlled by the control statement.

Examples of control statements include [conditions](#condition), [loops](#loop), and statements for handling [exceptions](#exception).

## csv

'CSV' stands for 'Comma Separated Values' and refers to a text file format for storing spreadsheet data. In a CSV file, the comma character is used as a [separator](#separator) between the columns of the spreadsheet.

For example, the contents of a simple CSV file might look like this when viewed in a text editor:

```
Name,Age,Location
Mildred,22,USA
Ishmael,19,USA
Sherlock,39,GB
```

In some cases, the separator may be the semicolon character instead:

```
Name;Age;Location
Mildred;22;USA
Ishmael;19;USA
Sherlock;39;GB
```

## dataframe

A structure that stores data in rows and columns is sometimes termed a 'dataframe' in computing. A more everyday term is simply 'table'. Typically, each row of a data frame represents one 'observation', which may be for example a customer, a purchase, a visit to a webpage, etc. Each column represents one piece of information recorded for that observation, such as a date, a time, a price, a rating. etc.

## delimiter

See [separator](#separator).

## dependency

If program A needs to use program B, then anyone who uses program A also needs to have program B installed on their computer. In such a case, we say that program A 'depends' on program B (and conversely, that program B is a 'dependency' of program A). For example, if we write a Python program that [imports](#import) the `pandas` [package](#package), then `pandas` is a dependency of our program; users of our program will need to have installed `pandas`.

## dictionary

A dictionary (abbreviated to 'dict' in Python) is a [data type](#type) that can store multiple values. It does so by storing the values under labels, termed '[keys](#key)'.

The [syntax](#syntax) for creating a dictionary is to place pairs of keys and values inside the 'curly braces' `{}`, separating each key from its associated value with a colon `:` and separating each pair from the next with a comma:


```python
info = {'name':'Mildred', 'age':22, 'location':'USA'}
```

The keys of the dictionary can then be used as [indices](#index) to retrieve the values. For example:


```python
info['age']
```




    22



## diff

'diff' is just an abbreviation of 'difference', but in the terminology of [version control](#versioning), i refers to the difference between one version of a file and the next version. When working on a programming project and making changes, it is a good idea to review the 'diffs' that our changes have produced before we [commit](#commit) those changes to the version history of the project.

## directory

Another term for a folder in a computer's file system.

## docstring

A docstring is a [string](#string) (i.e. a piece of text) that provides some human-readable information about the workings of our program. We can write docstrings into our programs o help the users of our programs understand what the program does and how they should use it. We indicate a docstring in our program by enclosing it in 'triple quotes' (`""" """`). A docstring at the top of a *.py* file provides information about the whole file, and a docstring underneath the definition of a [function](#function) provides information about that function.

## DRY

'Don't Repeat Yourself' is a principle that can help with developing flexible programs that can more easily be extended, or can more easily be fixed when mistakes are discovered. A feature of a program that is repeated in many places will need to be found and changed in many places if you decide it must be changed. This opens up a lot of scope for mistakes.

## dunder

The 'double underscore' `__ __` is sometimes abbreviated to 'dunder', because people who have to say 'double underscore' a lot are usually very busy people and need to save every second they can. Python uses double underscores surrounding a name to indicate that that name is involved in the 'behind the scenes' workings of Python and is not usually intended to be used directly.

If a [method](#method) is enclosed in double underscores, that method determines something about the behavior of a particular [data type](#type) in different circumstances. For example, the `__add__()` method determines what happens when a variable of that type is used in conjunction with the `+` [operator](#operator). So:

```python
x.__add__(1)
```

is what happens behind the scenes when we write:

```python
x + 1
```

If a [variable](#variable) is enclosed in double underscores, that variable determines something about the organization of a program. For example, the `__file__` variable stores the [path](#path) to the file that the current program is in.

## encoding

Computers store information in the form of numbers. If we want to store text in a computer, we need some way of allocating each text character a unique number, so that when we read the text data, we turn the stored numbers back into the correct characters. A system for allocating a unique number to each character is known as a 'text encoding'. If we need to transfer text data from one computer to another, we need to make sure that the computer reading the data uses the same encoding for reading as the computer that wrote the data used for writing it.

There are many different text encodings, but the two most important ones to be aware of are:

* [ASCII](https://en.wikipedia.org/wiki/ASCII). This system is universally agreed upon and standard across all normal computers, but it only covers the English alphabet. We cannot use ASCII for non-English characters such as `'à'` or for Devanagari, Sinhalese, emojis, etc.
* [UTF-8](https://en.wikipedia.org/wiki/UTF-8). This system includes many symbols in many writing systems and is by far the most widely-used on the internet. It is also usually the default encoding on Linux [operating systems](#os). For characters that are defined in the ASCII encoding, UTF-8 uses the same system as ASCII, so for these characters the two encodings are equivalent.

Some [operating systems](#os), most notably Windows and macOS, do not always use UTF-8 by default to encode non-ASCII characters. They may instead use a variety of other encodings with names like 'Latin-1', 'ISO-8859', or 'Windows-1252'. Some of these are equivalent for certain subsets of characters, and only become incompatible for a few obscure characters, such as special kinds of quote mark. And to add yet more to the confusion, these various non-UTF-8 encodings are frequently given the wrong name, even in official places such as the documentation for Windows.

## error

Sometimes our program fails and cannot be completed, either because we have not written the program according to the allowed [syntax](#syntax) or because an [exception](#exception) occurs that our program cannot handle. In this case, our program will stop running and Python will display a message with some information about the 'error' that occurred. Any parts of the program that follow the occurrence of the error will not be carried out.

An example error message:

```
  File "my_first_program.py", line 9
    Python, please do some amazing machine learning.
                    ^
SyntaxError: invalid syntax
```

## evaluate

To evaluate a command or expression means to 'work out' its result. So the result of evaluating the Python expression `round(1.618 * 2)` is `3`. The Python interpreter first evaluates `1.618 * 2` and gets `3.236`, then evaluates `round(3.236)` and gets `3`. We sometimes say that a certain expression 'evaluates to' its result. So for example `round(1.618 * 2)` evaluates to `3`, and `2 + 2 == 5` evaluates to `False`.

## exception

Sometimes something 'exceptional' happens during the running of our program. These things are not necessarily fatal for our program, but need to be dealt with in order for our program to continue running as normal. Example exceptions include unexpected input from the user (such as entering a word when our program expects a number), or trying to open a file that has been moved or deleted. When an exception occurs, we say that our program has '[raised](#raise)' an exception.

Python distinguishes among various different kinds of exception. Some of the most common ones that we are likely to encounter are:

* `NameError`: We have tried to use a [variable](#variable), but no variable with that name has been [assigned](#assignment) yet.
* `IndexError`: We have used an [index](#index) that goes beyond the length of whatever we are trying to apply the index to (e.g. a [list](#list)).
* `ValueError`: We have supplied an invalid input [value](#value) to a [function](#function).
* `TypeError`: We have tried to do something with a particular [data type](#type), but that thing only works for a different data type.
* `FileNotFoundError`: We have tried to open a file that does not exist.

We can handle exceptions with a [control statement](#control) that instructs Python to 'try' one action, but to carry out a different action if the first action raises an exception. For example:


```python
try:
    open('melville-moby_dick.txt')
except FileNotFoundError:
    print('The file is not there.')
```

    The file is not there.


If an exception is raised and we have not specified in our program what to do about it, then the result is an [error](#error) and our program stops.

## float

In Python, and in computing in general, 'float' is a term for a non-whole number, such as 1.618. This is one of the basic data [types](#type) that Python can represent. It is distinguished from whole numbers (or [integers](#integer)) such as 1, 2, 3, etc. Strictly speaking, the term 'float' does not refer to non-whole numbers in general but rather to a specific method for storing non-whole numbers in computers, called '[floating-point arithmetic](https://en.wikipedia.org/wiki/Floating-point_arithmetic)'. But for basic purposes we can take the term 'float' to mean simply 'non-whole number'.

## function

A function is a sequence of commands that performs a particular action (or multiple actions), and can be used in programs again and again. `print()` is an example of a function, and the action it performs is to display text for the user. Functions can come from many places. Some, such as `print()`, are already [built in](#builtin) to Python, but we can also create our own functions, or [import](#import) them from a program somebody else has written. When we run a function, we say that we [call](#call) the function. A function can have input [arguments](#argument). It may also have a [return value](#return), which we can [assign](#assignment) into a variable.

In the example below, we call the `len()` function with the argument `'floccinaucinihilipilification'`, and it returns the value `29` (which we then assign into the variable `word_length`).


```python
word_length = len('floccinaucinihilipilification')
print(word_length)
```

    29


## grayscale

In image processing, an image without color (i.e. only in shades of gray), is often called a 'grayscale' image.

## HTML

HyperText Markup Language is the main [markup language](#markup) in which web pages are written. HTML works by enclosing text inside 'tags' that instruct the web browser to display that text in a particular way, for example by coloring it, turning it into a clickable link, etc.

## IDE

An Integrated Development Environment (or IDE) is a computer application that makes the process of programming easier. A typical IDE provides a text editor for writing the actual program, along with various tools for running the program, checking its contents for mistakes, searching for help, etc. [Spyder](https://www.spyder-ide.org/) is the Python IDE that we use in this class.

## import

The contents of a [module](#module) contained in one file can be 'brought in' to the current program file using the Python [keyword](#keyword) `import`. This is known as 'importing' the module, in the same sense as importing foreign goods into a country.

Once imported, the contents of a module are available under the module's [namespace](#namespace).

## indentation

Python uses indentation (spaces at the beginning of a line) to mark some lines of a program as 'belonging to' a preceding [control statement](#control) that determines when or how often those lines should be run.

This use of indentation is fairly specific to Python. In most other programming languages indentation is optional, and is used only for visual clarity; parentheses or other characters are used to control the structure of the program instead.

## index

An 'index' is the position of a particular item in a [sequence](#sequence), such as in a [list](#list) or a [tuple](#tuple). Python's indexing system begins at 0. So the index of the first item in a sequence is 0, the index of the second item is 1, and so on. We can use indices to refer to an item that is stored in a sequence. The Python [syntax](#syntax) for using an index is to place it in square parentheses `[]` after the name of the variable that stores the sequence. So to print out the third item in a list we can type:


```python
shopping = ['eggs', 'bacon', 'black pudding', 'sausages']
print(shopping[2])
```

    black pudding


## integer

An integer is a whole number. So 2 is an integer, but 1.618 is not. 'Integer' (abbreviated to `int` in Python) is one of the basic data [types](#type) that Python can represent. A non-whole number is instead called a '[float](#float)'.

## interpreter

A Python interpreter is a computer program that takes our text files of Python commands and turns them into machine code instructions that our computer can understand. We do not especially need to know about or get involved in this process ourselves. Instead, we write our programs as text files of Python commands, and the interpreter takes care of getting our computer to understand them. Strictly, the term 'Python' itself refers to the Python programming language, i.e. a specific set of [syntactical rules](#syntax) that converts text commands into computer actions, but in practice many people use 'Python' to refer also to a Python interpreter program.

## IO

In computing, 'IO' is an abbreviation of 'Input/Output', and refers to anything to do with getting information into and out of a computer program or system. For example, a program may get input from a human being typing at the keyboard or by reading from a text file, and it may send output to the screen or write it into a text file.

## iterable

A [data type](#type) is 'iterable' if it contains multiple values, and it is possible to 'go through' those values one by one. 'Going through' the values in an iterable is called 'iterating'. [Strings](#string) are iterable (we can iterate through their characters), and so are [lists](#list) and [tuples](#tuple) (we can iterate through their items). The most common way of iterating is to use a [loop](#loop).

## JSON

JavaScript Object Notation (JSON) is a text file format for storing data. It stores data as a group of nested [lists](#list) and [dictionaries](#dictionary) that contain [strings](#string) and numbers, using the same [syntax](#syntax) as Python. As the name suggests, JSON was inspired by the JavaScript programming language, but the syntax of this language was itself inspired by Python and by other similar programming languages. The JSON format is commonly used for transferring data between programs written in different languages, or for transferring data over the internet.

## key

The 'keys' of a dictionary are the labels under which the values in the dictionary are stored. See the entry on [dictionaries](#dictionary) for a more detailed explanation of this term.

## keyword

A keyword (sometimes also referred to as 'reserved word') is a word that has a special fixed meaning for Python. For example, the keyword `del` deletes something from Python's memory. We cannot use keywords as the names of [variables](#variable) (hence the term 'reserved word'). For a full list of all the keywords in Python, see [here](https://docs.python.org/3/reference/lexical_analysis.html#keywords).

## list

A list is a kind of [sequence](#sequence); it can store multiple [values](#value) arranged in order. The [syntax](#syntax) for creating a list is to enclose the values in the sequence inside square parentheses `[]` and separate the values with commas. For example:


```python
shopping = ['eggs', 'bacon', 'black pudding', 'sausages']
```

Lists are very similar to [tuples](#tuple), another kind of sequence. The difference is that tuples are [immutable](#mutability), whereas lists are [mutable](#list).

## locale

Computer users want to be able to interact with their computer in way that takes into account certain pieces of information about the user's language and location. For example, the user may want dates and currency amounts displayed in a certain format, or they may want to see the time displayed in their time zone. A computer's [operating system](#os) may store this user-specific information and make it available to all programs so that they can use it to customize the user's experience. This bundle of information is often termed a 'locale'.

Among other things, the locale may contain information on the user's preferred [encoding](#encoding) for reading and writing text files, or their preferred decimal point character (in some lamguages it is a dot, in others it is a comma).

## loop

A loop is a [control statement](#control) that repeats certain lines of a program multiple times.

Loops can use the `for` and `in` [keywords](#keyword) to repeat the given actions for every item in an [iterable](#iterable). For example:


```python
shopping = ['eggs', 'bacon', 'black pudding', 'sausages']

for item in shopping:
    print(item)
```

    eggs
    bacon
    black pudding
    sausages


Or they can use the `while` [keyword](#keyword) to repeat the given actions until a particular condition is no longer fulfilled.

## mapping

See [dictionary](#dictionary).

## markup

A 'markup language' is a programming language that adds extra combinations of symbols to normal text, in order to instruct a computer program to display that text in a certain way. For example, the markup language [HTML](#html) tells a web browser how to display the text of a webpage.

## matrix

In math, a matrix is a collection of numbers (or occasionally other things) arranged in rows and columns. For example, the following matrix has 2 rows and 8 columns (so is termed a '2 x 8' matrix):

$$
\begin{bmatrix}
0 & 0 & 1 & 2 & 2 & 1 & 0 & 2 \\
0 & 6 & 6 & 5 & 4 & 3 & 3 & 0 \\
\end{bmatrix}
$$

Matrices are useful for representing geometric transformations, among other things, and have applications in fields like statistics, engineering, and quantum physics.

Matrices consisting of only a single row or a single column are often called row or column [vectors](#vector). In computing, matrices can be represented using [arrays](#array).

## method

A method is a [function](#function) that is defined specially for variables of one data [type](#type). For example, there is a [string](#string) method called `upper()`, which [returns](#return) an all UPPERCASE version of the string. This function is not defined for other data types such as numbers. The [syntax](#syntax) for using a method is to access it via the variable that we want to apply it to, by placing a `.` after the name of the variable. For example to get an uppercase version of a string variable using the `upper()` method:


```python
name = 'Mildred'
name.upper()
```




    'MILDRED'



## module

A 'module' is simply any text file containing Python commands. However, in practice the term 'module' tends to be reserved for files that do not in themselves run any program that accomplishes a task or produces an output, but instead serve merely to define various [functions](#function) or [variables](#variable) that can be used in other programs. (Compare the term '[script](#script)'.)

The contents of a module can be incorporated into another program file by [importing](#import) them. We may write our own modules, or we may make use of pre-made modules that are either built in to Python or are provided as part of additional [packages](#package) that we have installed.

## mutability

If a [type](#type) is 'mutable', this means that a [variable](#variable) of that type can have its contents changed or updated without having to be completely overwritten and [re-assigned](#assignment). For example, [lists](#list) are mutable, because applying a list [method](#method) can change the contents of the list without us assigning any result back into the list with `=`. When a mutable variable is changed even though we have not re-assigned it, we sometimes say that it has been changed 'in-place'.

The list in the following example is changed in-place by the `.reverse()` method:


```python
shopping = ['eggs', 'bacon', 'black pudding', 'sausages']
shopping.reverse()

shopping
```




    ['sausages', 'black pudding', 'bacon', 'eggs']



The opposite of 'mutable' is 'immutable'. [Strings](#string), [integers](#integer), [floats](#float), and [tuples](#tuple), for example, are all immutable, since their contents can never be changed unless we overwrite them in a new assignment using `=`.

The string in the following example is not changed by calling its `.upper()` method:


```python
name = 'Mildred'
name.upper()

name
```




    'Mildred'



Only here is it changed, because of the re-assignment with `=`:


```python
name = 'Mildred'
name = name.upper()

name
```




    'MILDRED'



('Mutable' [means 'changeable'](https://www.etymonline.com/word/mutable), and has the same origin as 'mutant', as in the *Teenage Mutant Ninja Turtles*.)

## namespace

We can think of our current Python program as creating a sort of 'workspace' in our computer's temporary memory, where all the [variables](#variable), [functions](#function), etc. created in the program are stored and held ready for use as the program runs. Within this main workspace we may have separate 'subspaces' that store some of these things together under a common name, for example because they have a common origin or because they all need to refer to one another in order to function properly. Such a subspace is known as a 'namespace'.

When we [import](#import) a [module](#module), its contents are available under a namespace that by default has the same name as the file containing the module.

To access things that are stored in a namespace rather than in the main workspace of our program, we simply prepend the name of the namespace, followed by a dot. So for example to use a function called `useful_function()` from a namespace called `my_module`:

```python
my_module.useful_function()
```

## NaN

'Not a Number' (NaN) is an abbreviation often used in computing and data analysis to stand for a piece of information that is missing or undefined, but could in principle have been a number. For example, [logarithm](https://en.wikipedia.org/wiki/Logarithm) functions normally output numbers, but they are undefined for negative inputs, so a computing system might choose to represent the result of asking for a logarithm of a negative number as a 'NaN' (and perhaps also issue a warning message).

There is no NaN value provided in basic Python, but there is one included in the `numpy` [package](#package):


```python
import numpy
numpy.log(-1)
```

    /home/lt/GitHub/introduction-to-programming/venv/lib/python3.6/site-packages/ipykernel_launcher.py:2: RuntimeWarning: invalid value encountered in log
      





    nan



## newline

When we view a text file that is written over multiple lines, we just see the separate lines of text neatly displayed in our text editor or word processor. But behind the scenes our computer does not actually store lines of text in separate 'rows' of its memory. It needs instead some way of storing information about where one line ends and the next begins. This is achieved by the use of a 'newline character' to represent the break between one line and the next. This character is not explicitly shown in a normal text editor, but it is there in the file. In some word processors, such as OpenOffice and Microsoft Word, you can opt to see the newline characters explicitly, and they are typically shown as a '[pilcrow](https://en.wikipedia.org/wiki/Pilcrow)' (¶).

If we want to include a newline character in a [string](#string) in Python, we can represent it with the character combination `'\n'`. These two characters together are interpreted as a single character meaning 'start a new line here':


```python
message = 'Hello,\nworld!'
print(message)
```

    Hello,
    world!


## none

The `None` [data type](#type) in Python is used to indicate something that is undefined or has no particular content.

## operator

An operator is a symbol that produces some result when written in an expression along with some other components. For example, the `+` operator produces the sum of two numbers:


```python
2 + 2
```




    4



Some operators may have different effects depending on the [type](#type) of the other components of the expression. For example, if used with [strings](#string) instead of numbers the `+` operator [concatenates](#concatenate) the strings.


```python
'a' + 'b'
```




    'ab'



## OS

The Operating System (abbreviated to 'OS') for a computer is the 'main program' that runs on that computer when it starts, and within which all other programs run. The operating system handles the tasks that are common to all programs, such as locating files, connecting to external devices, and so on. The most popular types of operating system are Microsoft Windows, macOS, and Linux.

## package

A package is a program that adds to the functionality of an existing program. For example, Python packages add new [modules](#module) to a Python installation.

A 'package manager' is a program that downloads, installs, and updates packages. For example, one of the functions of [Anaconda](https://www.anaconda.com/distribution) is to act as a package manager for Python and other data science software.

## parse

The process of interpreting structured text (for example [HTML](#html), [JSON](#json), or a Python file itself) and dividing it up into meaningful functional units is known as 'parsing' the text. This is the same sense in which linguists use the term when they talk about 'parsing' natural human language.

## path

The location of a file within the directory system of a computer is known as that file's 'path'. This is the same sense of 'path' as in the English phrase 'a path through the woods'; a file's path describes a series of turnings to take in the file system in order to get to that file.

Different [operating systems](#os) describe paths in different ways. Linux uses the forward slash character `/` as a [separator](#separator) between each branch in the path. So an example path looks like this:

```
/home/mildred/Documents/my_program.py
```

Windows uses the backslash `\` as the separator and starts with a letter identifying the drive on which the file is located. For example:

```
C:\Users\Mildred\Documents\my_program.py
```

Paths can be 'absolute', which means that they describe the full path to a file starting all the way back from the base of the directory system (sometimes called the 'root' directory). Or they can be 'relative', which means that they describe the path to a file starting from some other directory than the root directory, usually the directory that we are currently working in.

## pull

In [version control](#versioning), updating your copy of a [repository](#repository) to incorporate changes that have been made in another copy of the repository (for example one stored online) is termed 'pulling' the changes from the other repository.

## push

In [version control](#versioning), sending changes from your computer's copy of a [repository](#repository) to another copy (for example one stored online) is termed 'pushing' the changes to the other repository.

## raise

When an [exception](#exception) occurs during the running of a program, we say that the program has 'raised an exception'. (See the entry on [exceptions](#exception) for more details.) This is similar to the use of the word 'raise' in English in phrases like 'to raise an issue'.

We can also deliberately instruct our program to raise an exception, using the `raise` [keyword](#keyword). For example:


```python
raise ValueError('That is an invalid value.')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-29-72fb548a5442> in <module>
    ----> 1 raise ValueError('That is an invalid value.')
    

    ValueError: That is an invalid value.


## readme

A 'readme' file is a file containing some explanatory text about how to use a program, how it works, etc. This file is the starting point for someone who is looking at the files of a program and wondering what to do with them.

## refactor

Sometimes we may want to change the structure of a program, but without actually changing its behavior. For example, we may want our program to be more clearly readable, or to be easier to modify. Reorganizing a program without changing any of its behavior is termed 'refactoring' the program.

## regression

A situation in which a change to one part of a program unexpectedly breaks other aspects of the program.

## repository

A repository (sometimes abbreviated to 'repo') is a place where the various files constituting a computer program are stored, usually online. People who want to install a program can fetch the current version of the program from its repository.

There are various internet platforms that host repositories. [GitHub](https://github.com/) is one of the most popular. The Python Package Index ([PyPI](https://pypi.org/)) is a repository specifically for Python [packages](#package).

## return

[Functions](#function) usually finish by outputting some kind of result. For example, the `len()` function outputs the length of its argument, and the `round()` function outputs the result of rounding its argument to the nearest whole number. We say that when a function has finished its work, the function 'returns', and whatever it gives us when it has finished is the function's 'return value'. For example the return value of `len('floccinaucinihilipilification')` is `29`, and the return value of `round(1.618)` is `2`.

## RGB

In computing, colors are often described as a sequence of three numbers. This sequence represents a color as an additive mixture of three 'base' colors red, green, and blue (RGB), where each of the three numbers represents the 'amount' of each base color in the mixed color. The numbers in an RGB sequence may have different scales, but most commonly they are integers on a scale from 0 to 255.

Some example RGB sequences:

* *(255,0,0)*: pure bright red
* *(255,0,255)*: purple (mixture of red and blue)
* *(0,0,0)*: black (no colors)
* *(127,127,127)*: grey (middling amount of each color)
* *(255,255,255)*: white (all the colors)

Sometimes an additional number is included at the end of the RGB sequence, representing the degree of transparency that the color should have if it is overlaid on an image.

## scalar

A 'scalar' is simply a single number, such as `100` or `1.618`. This term is used in order to distinguish single numbers from collections of multiple numbers such as [vectors](#vector) or [matrices](#matrix).

## scraping

The process of automatically fetching pages from the internet and extracting information from them is often known as 'scraping' the internet.

## script

A script is a text file containing commands that are intended to be run, in order, as a program. The sense of 'script' here is the same as in an actor's script, which tells them what to say and do. Not all text files containing commands are scripts. Some may instead be [modules](#module), which do not of themselves run a specific program, but instead provide extra components that other programs may make use of.

## separator

A separator is a character that is used to separate different parts of a piece of text. Separators can occur in many different contexts:

*Python commands*. For example, the comma character is used as the separator for multiple [arguments](#argument) to a [function](#function) in Python.

*File paths*. A separator character is used to divide the various directories that lead to the location of a file in a file [path](#path).

*Spreadsheet files*. A separator is used in some text file formats to separate the columns of a spreadsheet. For example, in the [csv](#csv) file format, a comma separates the columns.

You may occasionally also encounter the term 'delimiter' used with essentially the same meaning as 'separator'. Technically, a delimiter character marks the limits of some entity (i.e. its beginning and its end). For example, the quote marks `''` mark the beginning and end of a [string](#string). But since delimiting an entity can in a certain sense also be thought of as separating it from its surroundings, the two terms are often effectively synonyms and the distinction is one that only matters to the sort of person whose mission in life is to make sure nobody is wrong on the internet.

## server

A server is a computer on the internet that provides information, such as web pages, to other computers. The other computers using this service, called [clients](#client), send a request to the server for a particular piece of information, and the server sends a response either delivering that information or explaining why it could not be delivered.

## sequence

Sequences are data [types](#type) that can store more than one [value](#value), and arrange those values in a given order. [Tuples](#tuple) and [lists](#list) are examples of sequences.

## slice

A slice is a subsection of a [sequence](#sequence). We can get a slice out of a sequence by giving a range of numbers as the [index](#index). The [syntax](#syntax) for this is to separate the beginning and end of the range with the colon character `:`. The end of a slice is interpreted as meaning 'up-to-but-not-including'.

For example to get a slice of a list containing entries `1` and `2` (i.e. 'from `1` up to but not including `3`'):


```python
shopping = ['eggs', 'bacon', 'black pudding', 'sausages']

shopping[1:3]
```




    ['bacon', 'black pudding']



## SQL

Structured Query Language (SQL) is a programming language that is very widely used for managing databases. SQL provides commands that are broadly of three different types:

* Define the relations and constraints that give a database its structure (sometimes called the 'schema' of the database).
* Modify the data in the database, for example by inserting, deleting, or changing information.
* Fetch different combinations of information from the database (usually called 'querying' the database).

## string

In computing 'string' essentially means a piece of text (because a piece of text is a 'string' of characters). The string is one of the basic data [types](#type) in Python. We indicate that we want Python to treat something as a string by enclosing it in quote marks `''` (or `""`). The term 'string' is abbreviated to `str` in Python.

## syntax

Syntax refers to the rules governing what constitutes a valid command in a programming language. If we write a program that violates Python's syntax, then the Python interpreter will not be able to understand it, and instead will complain of a 'syntax [error](#error)'.

# TDD

TDD stands for 'Test-Driven Development', an approach to software development in which the developer first writes a test that will check that their change to the main program works as desired, and only then moves on to writing that change to the main program.

## tuple

A tuple is a kind of [sequence](#sequence); it can store multiple [values](#value) arranged in order. The [syntax](#syntax) for creating a tuple is simply to separate the values in the sequence using commas (and for clarity, we can and should also place a pair of parentheses around the whole sequence, though this is not always absolutely necessary). For example:


```python
grades = (5.0, 4.0, 3.7, 3.3, 3.0, 2.7, 2.3, 2.0, 1.7, 1.3, 1.0, 0.9)
```

Tuples are very similar to [lists](#list), another kind of sequence. The difference is that tuples are [immutable](#mutability), whereas lists are [mutable](#list).

## type

Computer programs can handle information in different forms. For example, some pieces of information may be in the form of text, some may be numbers, and some may be more complex things such as a link to a file on the computer's disk, or a connection to a website. When we create or refer to information in our Python programs, Python needs to be able to know what type of information it is. Python has various [syntactical](#syntax) rules for determining what type a new variable is when we create one in our program. For example, quote marks `''` indicate a [string](#string) (i.e. text).

## URL

A 'Uniform Resource Locator' is a piece of text that indicates how a 'resource' (e.g. some data or computing service on the internet) can be accessed. More commonly we refer to a URL as a 'web address'. An example URL is `https://en.wikipedia.org/wiki/Python_(programming_language)`.

## value

The contents stored in a [variable](#variable) are often called its 'value'. For example, `name` might be a [string](#string) variable whose value is `'Mildred'`, and `height` might be a [float](#float) variable whose value is `1.96`.

## variable

A variable is a name that stores some information for the duration of our program. We choose the name ourselves, and [assign](#assignment) into that name whatever information we wish to store. We can then use the variable in subsequent steps of the program. For example:


```python
x = 2
print(x ** 0.5)
```

    1.4142135623730951


## vector

In math, a vector is a collection of numbers (or occasionally other things) arranged one after the other in a specific order. For example:

$$
\begin{bmatrix}
0 & 6 & 6 & 5 & 4 & 3 & 3 & 0 \\
\end{bmatrix}
$$

A vector is a special case of a [matrix](#matrix) that has either only a single row (a 'row vector') or a single column (a 'column vector').

## versioning

'Versioning', or more often 'version control' is the process of tracking the changes we make in successive versions of a computer program. This is important because we may sometimes need to check whether we and our colleagues are working on the same version of a program, or we may need to go back to an earlier version when we discover that our latest fabulous improvements have in fact completely broken everything.

## whitespace

Any text characters that appear simply as blank space are termed 'whitespace' characters. The most common whitespace character is of course simply the space, but there are others, such as the [newline character](#newline) and the tab.

## wildcard

A wildcard is a symbol used in computing to stand for 'everything' or 'anything'. Wildcards are common to many programming languages, not just Python. The most common wildcard symbol is the asterisk (or 'star') `*`. Wildcards can be used together with other characters to refer to 'all things that match a particular pattern'. For example, when referring to file names, the expression `*.txt` means 'all files ending in *.txt*'.
