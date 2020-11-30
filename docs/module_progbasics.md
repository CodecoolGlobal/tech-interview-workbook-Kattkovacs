# Programming Basics questions

## Computer science

### Data structures

1 What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
Lista adatstruktúra fogalma, list methodok.

Adat gyűjteményeket tárol egy változóban. Az adatok külnbőző típusúak lehetnek benne. Az elemeket index számon lehet elérni, mutable, változtathatóak az elemei.

Srote a collection of data in one variable, datas can be several types like integer, string, lists. You can reach element by index, and it's also mutable.
Methods: .append, extend, pop, insert, short, reverse, remove, count, index.

2 What is the difference between a list/array and a set?
Mi a különbség lista és set között?

Set: nem indexelt, rendezetlen, nem véltoztathatóak az értékei, (inmutable). Csak random tárolja az adatot, nem tárolható benne többször ugyanaz az elem.

Set is unindexed, unordered and you can not change items (inmutable). Because it just stores the data random, you can't store the same element more times.

3 What is the purpose and methods of a dictionary/map data structure?
Dictionary adatstruktúra fogalma, methodjai.

A dictionarykben kulcs:érték párosokat tárolunk. A kulcsoknak nem változtathatóaknak kell lenniük (nem lehet lista) és egyediek, az értékeket a kulcsok segítségével lehet elérni. Az érték bármilyen adattípus lehet és megismétlődhet.

In dictionaries key:value pairs are stored. Keys must be inmutable and must be unique, while values are allowed to be any data type and can be repeated. You can reach element by key.
Methods: keys, values, get, pop, update, copy, clear, remove.

### Algorithms

4 Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
def fibonacci (num_of_element):
fibonacci_numbes = [0,1]
for numbers in range(num_of_element-2):
fibonacci_numbes.append(fibonacci_numbes[numbers+fibonacci_numbes[numbers+1])
return fibonacci_numbes

5 How do you find a max value in a list/array if you can’t use any built-in functions?
def max_element (list_of_numbers):
max_value = list_of_numbers[0]
for number in list_of_numbers:
if number >= max_value:
max_value = number
return max_value

6 How do you find the average of values in a list/array if you can’t use any built-in functions?
def avg (list_of_numbers):
sum_of_numbers = 0
for number in list_of_numbers:
sum_of_numbers += number
return avarage = sum_of_numbers/len(list_of_numbers)

7 What do we call an _in-place_ sort?
The sort() method, which modifies the original list, instead of creating another one like sorted().

8 Explain an algorithm which sorts a list!
This simple sorting algorithm iterates over a list, comparing elements in pairs and swapping them until the larger elements "bubble up" to the end of the list, and the smaller elements stay at the "bottom".

### Programming paradigms - procedural

9 What is the call stack?
A call stack az egy adatszerkezet, ami információt tárol egy program aktív alprogramjairól.
Úgy kell elképzelni, mint egy vermet, amelybe bepakoljuk a szükséges alprogramokat.
A tetején van az éppen végrehajtás alatt álló rész, amely kikerül onnan, ha elkészült.
Minden funkcióhívás új keretet tol a híváskötegre (stack), és minden alkalommal, amikor egy funkcióhívás visszatér, a keret felpattan.

Call stack is a stack data structure that stores information about the active subroutines of a computer program.

10 What is “Stack overflow”?
Amikor a stack adatszerket túl hosszú, ekkor a “stack owerflow” hiba merül fel, amely gyakran a program összeomlásához vezet.

When the stack is too long. Stack overflow occurs. Stack overflow is an error, which usually causes the program to crash.

11 What are the main parts of a function?
Függvény neve, mellette zárójelben a bejövő paramétere(i), alatta a függvény teste. Nem minden esetben van visszatérési értéke.
def name () between "()" some input parameter:  
 indentation body

### Programming languages - Python

12 How do you use a dictionary in Python?
dic = { key1 : value1, key2 : value2} like in real life, unique keys and you can reach the values by it's key
Add new value (and key): mydict[key] = "value"
Remove key-value pairs with the del operator: del mydict[key]
Remove all items: mydict.clear()
The len() function gives the number of pairs
Sort:
for key, value in sorted(mydict.items()):
print key, value

13 What does it mean that an object is immutable in Python?
You can not modify it after the creation. (mean, if you change it, you will change the memory adress too, so the original data doesn't changed)
Mutable:
list, dict, set
Immutable:
int, float, bool, string, unicode, tuple
string1 = "Welcome"
tuple1 = (0, 1, 2, 3)
Exception:
tup = ([1, 2, 3], ‘myname’)
The tuple itself isn’t mutable but contain items that are mutable.

14 What is conditional expression in Python?
A Python programban az if statement az, amivel végre lehet hajtani az ilyen típusú döntéshozatalt. Lehetővé teszi egy kifejezés vagy utasításcsoportok feltételes végrehajtását egy kifejezés értéke alapján.
if, elif, else

15 What are different types of arguments in Python?
Default argument (statement = True), keyword argument (statement), Arbitary argument (\*statement)
Default argument:
A függvény argumentuma felveszi az alap értéket, ha a függvény nem változtat az argumentumok értékén.
Default values indicate that the function argument will take that value if no argument value is passed during function call.
def student(firstname, lastname ='Mark', standard ='Fifth'):
print(firstname, lastname, 'studies in', standard, 'Standard')
Keyword argument:

16 What is variable shadowing? (context: variable scope)
Variable shadowing is when a variable in a certain scope has the same name as another variable outside that scope. So the local overwrite the global (or even built-in)

17 What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
index error

18 What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
Local(L): Defined inside function/class
Enclosed(E): Defined inside enclosing functions(Nested function concept)
Global(G): Defined at the uppermost level
Built-in(B): Reserved names in Python builtin modules

19 If you need to access the iterator variable after a for loop, how would you do it in Python?
create a list and append it in the loop

20 What type of elements can a list contain in Python?
Any (int,float,str,bol)

21 What is slice operator in Python and how to use?
slice elements slice(start,stop,step)

22 What arithmetic operators (+,_,-,/) can be used on lists in Python? What do they do?
+,_

23 What is the purpose of the in and not in membership operators in Python?
to tell is something in (or not in) a list, or string

24 What does the + operator mean when used with strings in Python?
add the second to the end of the first

25 Explain f strings in Python?
formated string (to put variables into the sring)

26 Name 4 iterable types in Python!
list, dict, string, set

27 What is the difference between list/set/dictionary comprehension and a generator expression in Python?
In list=set/dict/ comprehension square brackets are used, while a generator expression is surrounded by round parentheses. A generator expression is more memory efficient, since while list comprehension produces an entire list, generator expression produces one item at a time.

28 Does the order of the function definitions matter in Python? Why?
No, because it just run when we call it.

29 What does unpacking mean in Python?
Unpacking is used when we want to use for e.g. a list (or other types of data sturcture) containing the parameters of a function. In this case we cannot simply pass the list to the function, we have to unpack the list by including a * sign, like that: function(*list).

30 What happens when you try to assign the result of a function which has no return statement to a variable in Python?
got None

## Software engineering

### Debugging

31 What techniques can you use while debugging a program in Python?
rubber duck, print/trace debugging, debugger

32 What does step over, step into and step out mean while using the debugger?
step over,into,out of a function

33 How can you start to debug a program from a certain line using the debugger?
put the breakepoint to there

### Version control

34 What are the advantages of using a version control system?
you know who did what and when (you can follow the lifetime of the prog) and backup

35 What is the difference between the working directory, the staging area and the repository in git?
Working directory: where you are currently working, it is an untracked area of git, 'git add' puts the files to the staging area. Staging area: where git starts to track the changes in the files, 'git commit' puts the files to the repository. Git repository: where all the files are saved from your git directory.

36 What are remote repositories in git?
Remote repositories are used to store files in a server that is accessible to multiple people working on the same project, instead of a local repository, which is only accessible by one person. For e.g.: Github repositories.

37 Why does a merge conflict occur?
Merge conflict occurs when two commits made changes on the same object/function and git cannot decide which to implement in the merge.

38 Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
git add -- git commit -- git push

39 What does it mean atomic commits and descriptive commit messages?
atomic is meaning often commit after every small changes, descriptive means that the commit is a short descriptive commit about the changes (atomic: often, descriptive: how short,understandable)

40 What’s the difference between git and GitHub?
git is the version control system, github is a cloud hosting system

## Software design

### Clean code

41 What does clean code mean?
Clean code is code that is easy to understand and easy to change.

42 What steps do we usually do during a clean code refactoring?
Read through the whole code Summarize what is the purpose of the script in one sentence. Run the code to see what is the end result The code should keep runnable and show the same content when you finish the refactor Remove clutter Format your code Delete comments Remove complexity improper variable scopes Remove cleverness Remove the 3 D's

### Error handling

43 What is exception handling?
When the program can't do something, and stops you can handle that situation.

44 What are the basics of exception handling in Python?
try, except.

45 In which case should we catch an exception? Why?
if the try can't run

46 What can/should we do with an exception in the ‘except’ block?

47 What does the else and finally statement do in a try-except block in Python?
Else runs if try runed
Finally always runs after try/except

## Software Development Methodologies

48 What is the main goal of a retrospective meeting?
The goal of retrospectives is helping teams to improve their working culture.

## Programming environment

### Unix

49 What is UNIX and what is Linux?
Unix is a is a multiuser and multitasking computer operating system. Nowadays UNIX is more like a trademark which means the family of operating systems.
Linux is an open source operating system. Today there are a lots of versions of Linux and we call them distributions.

50 What do we call the shell in Linux?
The shell is the command interpretor in an operating system such as Linux, it is a program that executes other programs. It provides a computer user an interface to the system so the user can run different commands or utilities/tools with some input data.

51 What does root means in a Linux environment?
Root is the user name or account that by default has access to all commands and files in the operating system.

52 How do you access your personal files in Linux?
from home directory

53 How can you install an application in Linux?
In the terminal use "sudo apt install + application name" command.

54 What is package management in Linux, what are repositories?
PM is for softwer intalling or maintaning, repos are servers that contains the pcakages

55 How do you navigate in the filesystem with the command line?
There are some commands:
cd - change directory ("cd + directory name" takes to the "directory name" directors)
cd .. - navigate one directory level up
pwd - print the working directory
ls - print the items in the working directory

56 What does the following commands do: mkdir, rm, cat, cp, touch?
mkdir command create new directories if they do not already exist on the file systems
rm delete file
cat print the file with the standard output
cp copy the file with a new filename
touch make a new file (empty)

57 How can you look up what does a command do in Linux if you have no internet connection?
Use the help command (like "cd –help")

58 What does the following commands do: head, tail, more, less?
head/tail print the first/last 10 lines of the file
more displays the file in a scrollabe mose
less display one schreen file content in a time.

59 How do you download a file from internet using the terminal?
With the comman "wget + URL" with a new name "wget -o filename URL"

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!

#### What is the difference between a list/array and a set?

#### What is the purpose and methods of a dictionary/map data structure?

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.

#### How do you find a max value in a list/array if you can’t use any built-in functions?

#### How do you find the average of values in a list/array if you can’t use any built-in functions?

#### What do we call an _in-place_ sort?

#### Explain an algorithm which sorts a list!

### Programming paradigms - procedural

#### What is the call stack?

#### What is “Stack overflow”?

#### What are the main parts of a function?

### Programming languages - Python

#### How do you use a dictionary in Python?

#### What does it mean that an object is immutable in Python?

#### What is conditional expression in Python?

#### What are different types of arguments in Python?

#### What is variable shadowing? (context: variable scope)

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?

#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?

#### If you need to access the iterator variable after a for loop, how would you do it in Python?

#### What type of elements can a list contain in Python?

#### What is slice operator in Python and how to use?

#### What arithmetic operators (+,\*,-,/) can be used on lists in Python? What do they do?

#### What is the purpose of the in and not in membership operators in Python?

#### What does the + operator mean when used with strings in Python?

#### Explain f strings in Python?

#### Name 4 iterable types in Python!

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?

#### Does the order of the function definitions matter in Python? Why?

#### What does unpacking mean in Python?

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?

#### What does step over, step into and step out mean while using the debugger?

#### How can you start to debug a program from a certain line using the debugger?

### Version control

#### What are the advantages of using a version control system?

#### What is the difference between the working directory, the staging area and the repository in git?

#### What are remote repositories in git?

#### Why does a merge conflict occur?

#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?

#### What does it mean atomic commits and descriptive commit messages?

#### What’s the difference between git and GitHub?

## Software design

### Clean code

#### What does clean code mean?

#### What steps do we usually do during a clean code refactoring?

### Error handling

#### What is exception handling?

#### What are the basics of exception handling in Python?

#### In which case should we catch an exception? Why?

#### What can/should we do with an exception in the ‘except’ block?

#### What does the else and finally statement do in a try-except block in Python?

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

## Programming environment

### Unix

#### What is UNIX and what is Linux?

#### What do we call the shell in Linux?

#### What does root means in a Linux environment?

#### How do you access your personal files in Linux?

#### How can you install an application in Linux?

#### What is package management in Linux, what are repositories?

#### How do you navigate in the filesystem with the command line?

#### What does the following commands do: mkdir, rm, cat, cp, touch?

#### How can you look up what does a command do in Linux if you have no internet connection?

#### What does the following commands do: head, tail, more, less?

#### How do you download a file from internet using the terminal?

# ............

# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!

The list is the most versatile compound data type. It can be indexed and sliced, and since it's a mutable type, its contents can be changed as needed. Nested lists can be useful for representing matrices or similar constructs.

List methods:

- `my_list.append(x)`:
  Add an item to the end of the list. Equivalent to `a[len(a):] = [x]`.
- `my_list.extend(iterable)`:
  Extend the list by appending all the items from the iterable. Equivalent to `a[len(a):] = iterable`.
- `my_list.insert(i, x)`:
  Insert an item at a given position. The first argument is the index before which to insert. `a.insert(len(a), x)` is equivalent to `a.append(x)`.
- `my_list.remove(x)`:
  Remove the first item from the list whose value is equal to `x`.
- `my_list.pop(i=optional)`:
  Remove the item at the given position in the list, and return it. If no index is specified, `a.pop()` removes and returns the last item in the list.
- `my_list.clear()`:
  Remove all items from the list. Equivalent to `del a[:]`.
- `my_list.index(x, start=optional, end=optional)`:
  Return index in the list of the first item whose value is equal to `x`. The optional arguments start and end are interpreted as in the slice notation and are used to limit the search to a particular subsequence of the list. The returned index is computed relative to the beginning of the full sequence rather than the start argument.
- `my_list.count(x)`:
  Return the number of times `x` appears in the list.
- `my_list.sort(key=None, reverse=False)`:
  Sort the items of the list _in place_.
- `my_list.reverse()`:
  Reverse the elements of the list _in place_.
- `my_list.copy()`:
  Return a _shallow copy_ of the list. Equivalent to `a[:]`.

#### What is the difference between a list/array and a set?

A set is an (mutable,) unordered collection with no duplicate elements. Basic uses include membership testing and eliminating duplicate entries. Sets are not iterable.

Sets, (unlike lists) support mathematical operations like:

- **union**:
  - letters in a or b or both
  - `a.union(b)`
  - `a | b`
- **intersection**:
  - letters in both a and b
  - `a.intersection(b)`
  - `a & b`
- **difference**:
  - letters in a but not in b
  - `a.difference(b)`
  - `a - b`
- **symmetric difference**:
  - letters in a or b but not both
  - `a.symmetric_difference(b)`
  - `a ^ b`

#### What is the purpose and methods of a dictionary/map data structure?

The dictionary is a mutable data type. Dictionaries are indexed by keys, which can be any immutable type. Strings and numbers can always be keys. Tuples can be used as keys if they contain only strings, numbers or tuples; if a tuple contains any mutable object either directly or indirectly, it cannot be used as a key.
A dictionary is a set of key-value pairs, with the requirement that the keys are unique (within one dictionary).
The main operations on a dictionary are storing a value with some key and extracting the value given the key. It is also possible to delete a key-value pair with the del statement. If you store a value using a key that is already in use, the old value associated with that key is forgotten.

Dictionary methods:

- `list(my_dict)`:
  Return a list of all the keys in the dictionary, in insertion order.
- `sorted(my_dict)`:
  Return a list of all the keys in the dictionary, in a specified order.
- `my_dict.clear()`:
  Remove all the elements from the dictionary.
- `my_dict.copy()`:
  Return a copy of the dictionary.
- `my_dict.get(k)`:
  Return the value of the specified key `k`.
- `my_dict.keys()`:
  Return a list containing the dictionary's keys.
- `my_dict.values()`:
  Return a list of all the values in the dictionary.
- `my_dict.items()`:
  Return a list containing a tuple for each key-value pair.
- `my_dict.pop(k)`:
  Remove and return the element with the specified key `k`.
- `my_dict.popitem()`:
  Remove and return a tuple of the last inserted key-value pair.
- `my_dict.setdefault(k, v)`:
  Return a value of the specified key `k`. If the key does not exist, insert the key with the specified value `v`.
- `my_dict.update({k: v, k: v, ...})`:
  Update the dictionary with the specified key-value pairs. If a key already extists, the old value associated with that key is forgotten.
- `my_dict.fromkeys(x, y)`:
  Return a dictionary with the specified keys and values. Here, `x` could represent a list `['key1', 'key2', ...]` of keys, `y` could represent an integer value `1`.

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.

**Iterative**:

```python
def fibonacci_iterative(n):
    if (n <= 1):
        return n

    fib = 1
    prev_fib = 0

    for _ in range(1, n):
        temp = fib
        fib += prev_fib
        prev_fib = temp

    return fib
```

**Recursive** with memoization:

```python
def fibonacci_recursive_memoization(n, memo=dict()):
    if (n <= 1):
        return n

    if (n in memo):
        return memo.get(n)

    fib = fibonacci_recursive_memoization(n - 1, memo) + fibonacci_recursive_memoization(n - 2, memo)
    memo[n] = fib

    return fib
```

#### How do you find a max value in a list/array if you can’t use any built-in functions?

```python
def get_max(numbers):
    max = None

    for number in numbers:
        if max == None:
            max = number
        elif (number > max):
            max = number

    return max
```

#### How do you find the average of values in a list/array if you can’t use any built-in functions?

```python
def get_average_numbers(numbers):
    length = 0
    sum = 0

    for number in numbers:
        length += 1
        sum += number

    return sum / length
```

#### What do we call an _in-place_ sort?

A method like `list.sort()` modifies the object (rather than create and modify a new one).

#### Explain an algorithm which sorts a list!

A bubble-sort algorithm iterates through the given list, and compares each element's value to the next element's value. Given the list is to be sorted in ascending order, the algorithm switches the elements' places every time an element's value is greater than the value of the next element.

```python
def bubble_sort(numbers):
    counter = 0
    while (counter < len(numbers) - 1):
        counter = 0

        for i in range(len(numbers) - 1):
            if (numbers[i] > numbers[i + 1]):
                numbers[i], numbers[i + 1] = numbers[i + 1], numbers[i]
            else:
                counter += 1
            i += 1

    return numbers
```

### Programming paradigms - procedural

#### What is the call stack?

The call stack is a dynamic data structure, maintained inside the computer's RAM by the operating system. Its purpose is to control the way procedures and functions call each other, and to control the way they pass parameters to each other. A call stack is maintained for each task, and each thread.

#### What is “Stack overflow”?

A stack overflow occurs if the call stack pointer exceeds the stack bound. The call stack may consist of a limited amount of address space, often determined at the start of the program. The size of the call stack depends on many factors, including programming language, machine (CPU) architecture, multi-threading, and amount of available memory. When a program attempts to use more space than is available on the call stack (that is, when it attempts to access memory beyond the call stack's bounds, which is essentially a buffer overflow), the stack is said to overflow, typically resulting in a program crash.
Common causes of stack overflow: excessively deep or infinite recursion, very large stack variables.

#### What are the main parts of a function?

A function head that defines the function, and the function body that contains the function's logic.

Function Head:

- `def` statement
- function name
- parentheses (if there are parameters, containing those)

Function Body:

- statements
- expressions
- arguments
- variables
- (function calls, parameters)

### Programming languages - Python

#### How do you use a dictionary in Python?

To initialize a dictionary with vaues:

- `my_dict = {'a': 1, 'b': 2, 'c': 3}`
- `my_dict = dict(a=1, b=2, c=3)`

#### What does it mean that an object is immutable in Python?

Immutable objects cannot be modified in-place.

#### What is conditional expression in Python?

A conditional statement results in a defined outcome when a certain condition is met (the expression's Boolean value is `True`).

Conditional expressions:

- `if`
- `else`
- `elif`

#### What are different types of arguments in Python?

- Default arguments (assigning default values with `=`)
- Keyword arguments (assigning values, disregarding argument positions)
- Arbitrary arguments (using packing/unpacking with `*`, `**`)

#### What is variable shadowing? (context: variable scope)

_Variable shadowing_ occurs when a variable declared in a certain scope (decision block, method, or inner class) has the _same name_ as a variable declared in an outer scope.
At the level of identifiers (names, rather than variables), this is known as _name masking_.

This outer variable (name) is said to be _shadowed_ (_masked_) by the inner variable (name).

This can lead to confusion, as it may be unclear which variable subsequent uses of the shadowed variable name refer to, which depends on the name resolution rules of the language.

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?

If you delete/drop an item from a list while iterating over it, the results will be inaccurate. Due to the changed contents (indices), the loop will skip some elements and/or end prematurely.

If we add to the list while iterating over it, it could result in an infinite loop.

#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?

LEGB stands for:

1. Local: Defined inside function/class.
2. Enclosed: Defined inside enclosing functions (nested functions concept).
3. Global: Defined at the uppermost level.
4. Built-in: Reserved names in Python built-in modules.

LEGB is the hierarchy in which python looks for variables (and functions as well).

Variables have different lifetimes, depending on their definition. E.g. a local variable exists as long as the function (in which it is defined) is being executed.

The golden rule means that variables should only be accessible where they are used. Avoiding using global variables as much as possible is standard.

#### If you need to access the iterator variable after a for loop, how would you do it in Python?

I can simply use the iterator variable after the loop has ended.

#### What type of elements can a list contain in Python?

Lists can contain any built-in data type.

#### What is slice operator in Python and how to use?

Using a slice operator does not change the list in-place but creates a new object.

- `list[start:end:step]` -- Creates a new list from the elements between `start` and `end`(the end index is non-inclusive).
- `list[:]` -- Creates a new (independent) copy of the list. Modifying this list won't affect the original list.
- `list[::-1]` -- Reverses the list.

#### What arithmetic operators (+,\*,-,/) can be used on lists in Python? What do they do?

- The `+` operator concatenates two lists. In other words, it appends one list's elements to another's.
- The `*` operator multiplies a list's elements by an integer.
- The `-` and `/` operators are unsupported and result in an error.

#### What is the purpose of the in and not in membership operators in Python?

Membership operators are operators used to validate the membership of a value. It tests for membership in a sequence (such as strings, lists, or tuples).

- `in`: Evaluates to `True` if the specified object exists in the specified sequence, evaluates to `False` otherwise.
- `not in`: Reverse of the `in` operator.
- `is`: Evaluates to `True` if the variables on either side of the operator point to the same object, and `False` otherwise.
- `is not`: Reverse of the `is` operator.

#### What does the + operator mean when used with strings in Python?

The `+` operator concatenates two strings.

#### Explain f strings in Python?

`f"{variable}"`

Also called _formatted string literals_, the **f-string** is a new and improved way to format strings in Python. It is a string literal that has an f at the beginning and curly braces containing expressions that will be replaced with their values. The expressions are evaluated at runtime and then formatted using the _format_ protocol.

#### Name 4 iterable types in Python!

- String
- List
- Tuple
- Dictionary

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?

List/set/dictionary comprehensions create the entire collection at once, while generators can evaluate elements on demand.

The `yield` statement "saves" the state of the function (rather than terminating it as the `return` statement) and can be used when the generator is called again.

The difference is that while a `return` statement terminates a function entirely, `yield` statement pauses the function saving all its states and later continues from there on successive calls.

Generators are slower but use less memory. (They can also represent infinite streams).

#### Does the order of the function definitions matter in Python? Why?

What matters is that we declare all functions that interact with each other before we call any of them (because they get executed only when called).

#### What does unpacking mean in Python?

**Unpacking**: We can use `*` to unpack the list so that all elements of it can be passed as different parameters.
Functions can use the elements of an _unpacked_ collection as parameters. (Most data structures use 1 asterisk, dictionaries use 2).

```python
def my_func(a, b, c):
    ...


my_func(*my_list)
my_func(**my_dict)
```

**Packing**: When we don't know how many arguments need to be passed to a python function, we can use _packing_ to pack all arguments in a tuple.

```python
def my_list_func(*args):
    args = list(args)
    ...


my_list_func(1, 2, 3)
```

```python
def my_list_func(**kwargs):
    ...


my_dict_func(a=1, b=2, c=3)
```

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

`None` is assigned as a result.

It's the return value of the function, which you print out. If there is no `return` statement (or just a `return` without an argument), an implicit `return None` is added to the end of a function.

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?

You can use doctest, a linter (PEP8), the `print()` statement (poor man's debugger), and the text editor's / IDE's Debug tool.

Among the various techniques for debugging are:

- a linter (e.g. PEP8, flake8)
- the `print()` statement (poor man's debugger)
- Debug tool in text editor / IDE
- doctest: The _doctest_ module searches for pieces of text that look like interactive Python sessions, and then executes those sessions to verify that they work exactly as shown.

#### What does step over, step into and step out mean while using the debugger?

- Step over: Steps over a line. If the line is a function, it gets executed and returned in the debug menu.
- Step into: Steps into the next function and continue debugging there.
- Step out: Returns to the line where the function was called.

#### How can you start to debug a program from a certain line using the debugger?

By putting a breakpoint into that line. The program will run up to the breakpoint, and start debugging from there.

### Version control

#### What are the advantages of using a version control system?

You can record and follow every change throughout the project. Multiple people can work on the same code at the same time. If something goes wrong, you can always go back to a previous version.

#### What is the difference between the working directory, the staging area and the repository in git?

1. Working directory:
   Contains the files that are untracked by Git (still "in the works").

2. Staging area:
   Contains the files that are added from the working directory. Git keeps track of any change that happens to these files.

3. Local git repository:
   The .git/ directory inside a project. Contains the files that are pushed from the staging area. This repository tracks all changes made to files in your project, building history over time. If you delete the .git/ folder, you destroy your whole project's history.

#### What are remote repositories in git?

Remote repositories store all the versions of a project in the cloud, e.g. GitHub.

#### Why does a merge conflict occur?

Merge conflicts occur when competing changes are made to the same line of a file, or when one person edits a file and another person deletes the same file.

#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?

```bash
touch new_file
git add new_file
git commit -m "Add new file"
git push origin master
```

#### What does it mean atomic commits and descriptive commit messages?

Atomic commits:
When you commit every logical block that you wrote.

Descriptive commit messages:
When the commit messages are meaningful, concise and easy to read.

#### What’s the difference between git and GitHub?

Git (global information tracker):

- A version control system used for tracking changes in source code during software development.
- Emphasis on speed, data integrity and support for distributed, non-linear workflows.
- Every change, or **commit**, has a unique ID (or **hash**) linked to its parent. Furthermore, you can create **branches**, which have a different history than your master branch, with their own commits; these can then be merged back into the master.

Github is a website used for hosting git repositories in the cloud (via the git protocol).

## Software design

### Clean code

#### What does clean code mean?

Your code is DRY. Easy to read, easy to understand, easy to maintain. No dead code, no repetition, no clutter.

#### What steps do we usually do during a clean code refactoring?

- First we need to try and understand the code.
- Then we start with checking _variable_ and _function names_, and replace them if needed.
- Then we eliminate _global variables_ and _magic numbers_.
- In the end, the code should be free of _clutter_, _complexity_ and _cleverness_.

### Error handling

#### What is exception handling?

Exception handling is the process of responding to the occurrence of _exceptions_ often disrupting the normal flow of program execution. Instead of crashing, the program _handles_ exceptions in a more graceful way.

#### What are the basics of exception handling in Python?

We use _try-except_ blocks.

If the `try` block runs to failure, it jumps to the except block rather than crashing.
The `except` block contains the logic that deals with the exception gracefully.

#### In which case should we catch an exception? Why?

We should catch only well defined, foreseeable exceptions to maintain flow control. Defining broader exceptions may cause the program to not work as expected.

#### What can/should we do with an exception in the ‘except’ block?

We should tell the program how to continue executing our code. E.g. to print an error message and jump back to the try block.

#### What does the else and finally statement do in a try-except block in Python?

The `else` block is executed when the except block doesn't catch an exception.
The `finally` block is always executed.

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

A _retrospective_ should take place after a _peer review_ and before the next _sprint planning_. It is an opportunity for the team (Scrum Team?) to inspect itself and create a plan (with action items) for improvements to be enacted during the next sprint.

- What went well in the sprint?
- What could be improved?
- What will we commit to improve in the next sprint? Action items...

## Programming environment

### Unix

#### What is UNIX and what is Linux?

UNIX is a family of multitasking multiuser computer operating systems from the 70's. It has a modular design and a _command line interface (CLI)_.

Linux is a family of open source _Unix-like_ operating systems based on the _Linux kernel_ (first released in 1991 by Linus Torvalds).

Linux is free (open source), but UNIX is licensed. Unix-like systems are very similar to UNIX, even though they are not certified to be UNIX systems. Linux also has a GUI (Graphical User Interface).

#### What do we call the shell in Linux?

The shell is a program that takes operations from the user and gives it to the OS.

A shell provides a command line user interface for Unix-like operating systems. The shell is both an _interactive command language_ and a _scripting language_, and is used by the operating system to control the execution of the system using shell scripts.

_GNU BASH / Bash (Bourne Again Shell)_. It's not part of the kernel, but it uses it to run itself. It is also called simply the _terminal_.

Bash is a free Unix shell and command language. It is the default login shell for most Linux distros and macOS (up until Mojave).

Bash is a command processor that runs in a text window where the user types commands that cause actions. Bash can also read and execute commands from a file (shell script).

#### What does root means in a Linux environment?

An account that has access to all commands and files. It is usually referred to as the superuser.
`sudo`

There's also a root directory, all of the directories and files are in there.
`cd /`

#### How do you access your personal files in Linux?

Personal files are in the Home directory.
`cd ~`

#### How can you install an application in Linux?

You can download and install it from the Ubuntu Software Center (or equivalent), or download it using the terminal.

- `sudo apt-get install <application name>` (Ubuntu)
- `brew install <application name>` (macOS)

#### What is package management in Linux, what are repositories?

Package management keeps track of the users' software packages. It tells the user whenever there's a new version of an installed software is available.

The repository is storage location where new softwares get installed and existing softwares get updated by the OS, also this is where the OS updates itself.

#### How do you navigate in the filesystem with the command line?

- `pwd`: Print working directory.
- `ls`: List items.
- `cd`: Change directory.

#### What does the following commands do: mkdir, rm, cat, cp, touch?

- `mkdir`: Create new folder (directory).
- `rm`: Remove file or folder (directory).
- `cat`: Concatenate files and print to standard output.
- `cp`: Copy file or folder (directory).
- `touch`: Create new file.

#### How can you look up what does a command do in Linux if you have no internet connection?

- `man <command name>`
- `<command name> --help`

#### What does the following commands do: head, tail, more, less?

- `head`: Print the first 10 lines to standard output.
- `tail`: Print the last 10 lines to standard output.
- `more`: View one screenful of text at a time.
- `less`: Similar to more, but faster, and you can navigate through the file. Better for large files.

#### How do you download a file from internet using the terminal?

`wget <URL>`
