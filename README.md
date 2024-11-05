# Chaitana-s-Colossal-Coaster
Exercise Learning Goals
This learning exercise helped evolve your knowledge of List Methods.

You've unlocked 1 concept:

Lo
Loops
You've unlocked 68 exercises:

Icon for exercise called Making the Grade
Making the Grade
Icon for exercise called High Scores
High Scores
Icon for exercise called Matrix
Matrix
Icon for exercise called Twelve Days
Twelve Days
Icon for exercise called Grade School
Grade School
Icon for exercise called Luhn
Luhn
Icon for exercise called Tournament
Tournament
Icon for exercise called Book Store
Book Store
Icon for exercise called Palindrome Products
Palindrome Products
Icon for exercise called Saddle Points
Saddle Points
Icon for exercise called Prime Factors
Prime Factors
Icon for exercise called Pythagorean Triplet
Pythagorean Triplet
Icon for exercise called Simple Cipher
Simple Cipher
Icon for exercise called Meetup
Meetup
Icon for exercise called Sieve
Sieve
Icon for exercise called Tree Building
Tree Building
Icon for exercise called Go Counting
Go Counting
Icon for exercise called React
React
Icon for exercise called Largest Series Product
Largest Series Product
Icon for exercise called OCR Numbers
OCR Numbers
Icon for exercise called Poker
Poker
Icon for exercise called Rectangles
Rectangles
Icon for exercise called Scale Generator
Scale Generator
Icon for exercise called Atbash Cipher
Atbash Cipher
Icon for exercise called Binary Search Tree
Binary Search Tree
Icon for exercise called Affine Cipher
Affine Cipher
Icon for exercise called Binary Search
Binary Search
Icon for exercise called Variable Length Quantity
Variable Length Quantity
Icon for exercise called Two Bucket
Two Bucket
Icon for exercise called Crypto Square
Crypto Square
Icon for exercise called House
House
Icon for exercise called List Ops
List Ops
Icon for exercise called Roman Numerals
Roman Numerals
Icon for exercise called Change
Change
Icon for exercise called DOT DSL
DOT DSL
Icon for exercise called Knapsack
Knapsack
Icon for exercise called Circular Buffer
Circular Buffer
Icon for exercise called Run-Length Encoding
Run-Length Encoding
Icon for exercise called Transpose
Transpose
Icon for exercise called Bowling
Bowling
Icon for exercise called Forth
Forth
Icon for exercise called Ledger
Ledger
Icon for exercise called Word Search
Word Search
Icon for exercise called Satellite
Satellite
Icon for exercise called Zipper
Zipper
Icon for exercise called POV
POV
Icon for exercise called Food Chain
Food Chain
Icon for exercise called Dominoes
Dominoes
Icon for exercise called REST API
REST API
Icon for exercise called Nth Prime
Nth Prime
Icon for exercise called Rail Fence Cipher
Rail Fence Cipher
Icon for exercise called Zebra Puzzle
Zebra Puzzle
Icon for exercise called Custom Set
Custom Set
Icon for exercise called PaaS I/O
PaaS I/O
Icon for exercise called Alphametics
Alphametics
Icon for exercise called D&D Character
D&D Character
Icon for exercise called Space Age
Space Age
Icon for exercise called Hangman
Hangman
Icon for exercise called SGF Parsing
SGF Parsing
Icon for exercise called Anagram
Anagram
Icon for exercise called Secret Handshake
Secret Handshake
Icon for exercise called Bottle Song
Bottle Song
Icon for exercise called Killer Sudoku Helper
Killer Sudoku Helper
Icon for exercise called Resistor Color Trio
Resistor Color Trio
Icon for exercise called Resistor Color Expert
Resistor Color Expert
Icon for exercise called Flatten Array
Flatten Array
Icon for exercise called Matching Brackets
Matching Brackets
Icon for exercise called Eliud's Eggs
Eliud's Eggs
Introduction
A list is a mutable collection of items in sequence. Like most collections (see the built-ins tuple, dict and set), lists can hold reference to any (or multiple) data type(s) - including other lists. Lists can be copied in whole or in part via slice notation or through the use of <list>.copy(). Like any sequence, elements within lists are referenced by 0-based index number from the left, or -1-based index number from the right.

Lists support both common and mutable sequence operations such as min(<list>)/max(<list>), <list>.index(), <list>.append() and <list>.reverse(). Elements inside a list can be iterated over using the for item in <list> construct. for index, item in enumerate(<list>) can be used when both the element index and element value are needed.

Python also provides many useful list-methods for working with lists. A selection of these list methods is covered below.

Note that when you manipulate a list with a list-method, you alter the list object that has been passed. If you do not wish to mutate the original list, you will need to at least make a shallow copy of it via slice or <list>.copy().

Adding Items
To add an item to the end or "right-hand side" of an existing list, use <list>.append(<item>):

>>> numbers = [1, 2, 3]
>>> numbers.append(9)

>>> numbers
[1, 2, 3, 9]
Rather than appending, <list>.insert() gives you the ability to add the item to a specific index in the list. It takes 2 parameters:

the <index> at which you want the item to be inserted.
the <item> to be inserted.
Note: If the given index is 0, the item will be added to the start ("left-hand side") of the list. If the supplied index is greater than the final index on the list, the item will be added in the final position -- the equivalent of using <list>.append(<item>).

>>> numbers = [1, 2, 3]
>>> numbers.insert(0, -2)

>>> numbers
[-2, 1, 2, 3]

>>> numbers.insert(1, 0)

>>> numbers
[-2, 0, 1, 2, 3]
<list>.extend(<item>) can be used to combine an existing list with the elements from another iterable (for example, a set, tuple, str, or list). The iterable is unpacked and elements are appended in order (Using <list>.append(<item>) in this circumstance would add the entire iterable as a single item.).

>>> numbers = [1, 2, 3]
>>> other_numbers = [5, 6, 7]

>>> numbers.extend(other_numbers)

>>> numbers
[1, 2, 3, 5, 6, 7]

>>> numbers.extend([8, 9])

>>> numbers
[1, 2, 3, 5, 6, 7, 8, 9]

>>> numbers.append([8,9])

>>> numbers
[1, 2, 3, 5, 6, 7, 8, 9, [8, 9]]
Removing Items
To delete an item from a list use <list>.remove(<item>), passing the item to be removed as an argument. <list>.remove(<item>) will throw a ValueError if the item is not present in the list.

>>> numbers = [1, 2, 3]
>>> numbers.remove(2)

>>> numbers
[1, 3]

# Trying to remove a value that is not in the list throws a ValueError
>>> numbers.remove(0)
ValueError: list.remove(x): x not in list
Alternatively, using the <list>.pop(<index>) method will both remove and return an element for use.

<list>.pop(<index>) takes one optional parameter: the index of the item to be removed and returned. If the (optional) index argument is not specified, the final element of the list will be removed and returned. If the index specified is higher than the final item index, an IndexError is raised.

>>> numbers = [1, 2, 3]

>>> numbers.pop(0)
1

>>> numbers
[2, 3]

>>> numbers.pop()
3

>>> numbers
[2]

>>> numbers.pop(1)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: pop index out of range
All elements can be removed from a list with list.clear(). It doesn't take any parameters.

>>> numbers = [1, 2, 3]
>>> numbers.clear()

>>> numbers
[]
Reversing and reordering
The <list>.reverse() method will reverse the order of elements in-place.

>>> numbers = [1, 2, 3]
>>> numbers.reverse()

>>> numbers
[3, 2, 1]
A list can be re-ordered in place with the help of <list>.sort(). Default sort order is ascending from the left. The Python docs offer additional tips and techniques for sorting.

Note
From 2002 to 2022, Python used an algorithm called Timsort internally to arrange lists, but switched to Powersort from Python 3.11 onward.

>>> names = ["Tony", "Natasha", "Thor", "Bruce"]

# The default sort order is *ascending*.
>>> names.sort()

>>> names
["Bruce", "Natasha", "Thor", "Tony"]
If a descending order is desired, pass the reverse=True argument:

>>> names = ["Tony", "Natasha", "Thor", "Bruce"]
>>> names.sort(reverse=True)

>>> names
["Tony", "Thor", "Natasha", "Bruce"]
For cases where mutating the original list is undesirable, the built-in sorted(<iterable>) function can be used to return a sorted copy.

>>> names = ["Tony", "Natasha", "Thor", "Bruce"]

>>> sorted(names)
['Bruce', 'Natasha', 'Thor', 'Tony']
Occurrences of an item in a list
The number of occurrences of an element in a list can be calculated with the help of list.count(<item>). It takes the item to be counted as its argument and returns the total number of times that element appears in the list.

>>> items = [1, 4, 7, 8, 2, 9, 2, 1, 1, 0, 4, 3]

>>> items.count(1)
3
Finding the index of items
<list>.index(<item>) will return the index number of the first occurrence of an item passed in. If there are no occurrences, a ValueError is raised. If the exact position of an item isn't needed, the built-in in operator is more efficient for checking if a list contains a given value.

Indexing is zero-based from the left, so the position of the "first" item is 0. Indexing will also work from the right, beginning with -1.

>>> items = [7, 4, 1, 0, 2, 5]

>>> items.index(4)
1

>>> items.index(10)
ValueError: 10 is not in list
start and end indices can also be provided to narrow the search to a specific section of the list:

>>> names = ["Tina", "Leo", "Thomas", "Tina", "Emily", "Justin"]

>>> names.index("Tina")
0

>>> names.index("Tina", 2, 5)
3
Instructions
Chaitana owns a very popular theme park. She only has one ride in the very center of beautifully landscaped grounds: The Biggest Roller Coaster in the World(TM). Although there is only this one attraction, people travel from all over the world and stand in line for hours for the opportunity to ride Chaitana's hypercoaster.

There are two queues for this ride, each represented as a list:

Normal Queue
Express Queue (also known as the Fast-track) - where people pay extra for priority access.
You have been asked to write some code to better manage the guests at the park. You need to implement the following functions as soon as possible before the guests (and your boss, Chaitana!) get cranky.

1. Add me to the queue
Define the add_me_to_the_queue() function that takes 4 parameters <express_queue>, <normal_queue>, <ticket_type>, <person_name> and returns the appropriate queue updated with the person's name.

<ticket_type> is an int with 1 == express_queue and 0 == normal_queue.
<person_name> is the name (as a str) of the person to be added to the respective queue.
>>> add_me_to_the_queue(express_queue=["Tony", "Bruce"], normal_queue=["RobotGuy", "WW"], ticket_type=1, person_name="RichieRich")
...
["Tony", "Bruce", "RichieRich"]

>>> add_me_to_the_queue(express_queue=["Tony", "Bruce"], normal_queue=["RobotGuy", "WW"], ticket_type=0, person_name="HawkEye")
....
["RobotGuy", "WW", "HawkEye"]
2. Where are my friends?
One person arrived late at the park but wants to join the queue where their friends are waiting. But they have no idea where their friends are standing and there isn't any phone reception to call them.

Define the find_my_friend() function that takes 2 parameters queue and friend_name and returns the position in the queue of the person's name.

<queue> is the list of people standing in the queue.
<friend_name> is the name of the friend whose index (place in the queue) you need to find.
Remember: Indexing starts at 0 from the left, and -1 from the right.

>>> find_my_friend(queue=["Natasha", "Steve", "T'challa", "Wanda", "Rocket"], friend_name="Steve")
...
1
3. Can I please join them?
Now that their friends have been found (in task #2 above), the late arriver would like to join them at their place in the queue. Define the add_me_with_my_friends() function that takes 3 parameters queue, index, and person_name.

<queue> is the list of people standing in the queue.
<index> is the position at which the new person should be added.
<person_name> is the name of the person to add at the index position.
Return the queue updated with the late arrivals name.

>>> add_me_with_my_friends(queue=["Natasha", "Steve", "T'challa", "Wanda", "Rocket"], index=1, person_name="Bucky")
...
["Natasha", "Bucky", "Steve", "T'challa", "Wanda", "Rocket"]
4. Mean person in the queue
You just heard from the queue that there is a really mean person shoving, shouting, and making trouble. You need to throw that miscreant out for bad behavior!

Define the remove_the_mean_person() function that takes 2 parameters queue and person_name.

<queue> is the list of people standing in the queue.
<person_name> is the name of the person that needs to be kicked out.
Return the queue updated without the mean person's name.

>>> remove_the_mean_person(queue=["Natasha", "Steve", "Eltran", "Wanda", "Rocket"], person_name="Eltran")
...
["Natasha", "Steve", "Wanda", "Rocket"]
5. Namefellows
You may not have seen two unrelated people who look exactly the same, but you have definitely seen unrelated people with the exact same name (namefellows)! Today, it looks like there are a lot of them in attendance. You want to know how many times a particular name occurs in the queue.

Define the how_many_namefellows() function that takes 2 parameters queue and person_name.

<queue> is the list of people standing in the queue.
<person_name> is the name you think might occur more than once in the queue.
Return the number of occurrences of person_name, as an int.

>>> how_many_namefellows(queue=["Natasha", "Steve", "Eltran", "Natasha", "Rocket"], person_name="Natasha")
...
2
6. Remove the last person
Sadly, it's overcrowded at the park today and you need to remove the last person in the normal line (you will give them a voucher to come back in the fast-track on another day). You will have to define the function remove_the_last_person() that takes 1 parameter queue, which is the list of people standing in the queue.

You should update the list and also return the name of the person who was removed, so you can write them a voucher.

>>> remove_the_last_person(queue=["Natasha", "Steve", "Eltran", "Natasha", "Rocket"])
...
'Rocket'
7. Sort the Queue List
For administrative purposes, you need to get all the names in a given queue in alphabetical order.

Define the sorted_names() function that takes 1 argument, queue, (the list of people standing in the queue), and returns a sorted copy of the list.

>>> sorted_names(queue=["Natasha", "Steve", "Eltran", "Natasha", "Rocket"])
...
['Eltran', 'Natasha', 'Natasha', 'Rocket', 'Steve']
