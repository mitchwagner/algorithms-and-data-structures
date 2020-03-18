# Introduction
Per Niklaus Wirth, Algorithms + Data Structures = Programs. This
repository, developed for personal edification, tracks implementations
of these building blocks in various programming languages, each in its
own subrepository.

## Repository Structure
One can, of course, specify an algorithm at varying levels of
abstraction.  Consider the following instructions:

1. Insert elements into a structure. Sort the elements in the
   structure.

2. Insert elements into a list. Sort the elements in the list.

3. Insert elements into an array list. Sort the elements using Bubble
   Sort.

Note that in the foremost statement, we've been very imprecise and can
say very little about the algorithm, while in the lattermost, we've
included perhaps unnecessary detail. In general, the second set of
instructions is the most sensible level of specification, and this
repository and its children are structured accordingly.

At the top level, the repository for each language will be divided
into two folders: `algorithms` and `data structures`. This project
takes the view that, although there are many operations one may
perform over a given data structure, data structures are fundamentally
static things- definitions, at some level of abstraction, of the
semantic meaning of data. As such, the `data structures` folder will
contain such definitions- it may specify a common interface for a
particular data structure, for example- in addition to the structures
themselves.

The `data structures` folder will also contain implementations of
fundamental functions- those that require knowledge of the structure
itself.

In contrast, the focus of the `algorithms` folder will be
circumscribed to higher-order constructs that can be parameterized by
various data structures. For example, an algorithm in this folder may
require as input something that conforms to the interface of a list,
without concern as to whether it comes in the form of a linked list or
an array list. Additionally, the algorithms here may instantiate
additional data structures for internal bookkeeping, and it may be
desirable to allow the specification of the implementation to be used.

To offer a concrete example, the `data structures` folder might
contain a definition of a list interface, containing the various list
operations (get, insert, append, sort, contains, etc.). Note that even
a fundamental function like "sort" may be implemented in many
different ways- algorithms like bubble sort or insertion sort should
be implemented here, as well as binary search. The `algorithms` folder
should be reserved for something like the scan-line polygon-filling
algorithm, which accepts lists as parameters.

Essentially, if your code interacts directly on top of a data
structure, it should go in the `data structures` folder. If, instead,
your code interfacts with data structure only via interfaces, then it
should be incldued in the `algorithms` folder.
