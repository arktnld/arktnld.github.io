---
layout: post
title:  "Data Structure"
date:   2021-05-18 15:04:30 -0300
categories: jekyll update
---
Data Structure
===============
**Data Structure** give us organization, storage, and access.

**Data** Is an information that is stored or processed by a computer.

**Data Type** An attribute of data that describes the values it can have and how the data can be used.

Types of Data
---------------

**Common Types of Data**
- Numbers
- Letters
- True and False

**Numbers**
- Whole Numbers (short, int and long).
- Decimal Numbers(double and float).
- Signed (Positive and negative values).
- Unsigned (Only positive values).

**Boolean** A Boolean is a true or false value. A Boolean is one bit.

**Primitive Types**

`variableName -> data`

- int
- doubles
- longs
- floats
- shorts
- booleans
- chars

**Referenced Types**

`variableName -> memoryAddress -> value`

- String
- Data Structures

**Pointers**
```
Example:
Collection A    Collection B
3 -> 00000011   (5) -> 00000010
1 -> 00000001   4 -> 00000100
(5) -> 00000010
```
The fives in each collection can have the same memory allocation.

Each programming language determines what access you have to memory management tools.
C++ (manage pointers, memory, and data)
Java and Python (memory management handled for you)

# Arrays
--------
Collection of elements, where each item is identified by an index or key.
Try to access an index that doesn't exist will give a error with the phase "index out of bounds".

Arrays Provide: Organization, storage and access.

**Jagged Arrays**
A jagged array can have elements of different dimensions and sizes.

Example:
```
|   |   |   |   |   |
|---|---|---|---|---|
| 1 | 3 | 8 |
| 1 | 2 |
| 9 | 0 |
| 10| 11 | 4 | 20 | 50
| 30|
```

This jagged array have 5 fixed rows and variable number of columns.

**Resizable Arrays**
Java and C++ basic arrays cannot be resized.
Ruby and JavaScript basic arrays can be resized.

- Immutable: basic array data that cannot change. Example: Java basic arrays.
- Mutable: Java classes give us resizable versions like arrayList.

**ArrayList**
- An arrayList is an array under the surface
- Focus less on maintaining data structures and more on creating \
Example: myArrayList.add(2, 10); -> inserts the value 10 at index 2

```mermaid
graph LR
A[add, push] -->B[adding to the back of the array]
C[add, push] -->D[adding to the back of the array]
style A fill:#eee,stroke:#594,stroke-width:4px
style B fill:#eee,stroke:#555,stroke-width:2px
style C fill:#eee,stroke:#29f,stroke-width:4px
style D fill:#eee,stroke:#555,stroke-width:2px
```

Insert functionality in Non-mutable Arrays, can be done in two ways.
1. If basic array is big enough: Items are shuffled down and a new item is added.
2. If basic array is not big enough: All contents copied into a new, bigger basic \
array, and new items are also copied over with it.

This can have major performance improvements.

# Search Arrays
---------------

**How can we search?**
- Check every item
- If matched, return true
- If no match (after searching the entire structure), return false

**Searching Outcomes**
- Best case: it's the first item
- Worst case: not in the array

**Array Search Reminders**
- Linear search occurs behind the scenes
- indexOf has no information about your data
- Check every element

You can also sort items to make search even faster.

**Sort Arrays**

Sorting with Programming Language
- Call sorting function to your collection of objects
- Pass your data structure as a parameter to a sorting function

# Big O Notation
----------------
Notation used to describe the performance or complexity of an algorithm.

**Operations**
- Access
- Updated
- Insert
- Search
- Delete
- Sort

**O(1) Time**
- Consistent duration of algorithm execution in same time \
(or space) regardless of the size of the input.
- Also called "constant time"

**Outcomes: Insertion**
----

```mermaid
flowchart TD
A[Best-Case\nScenario]---B(Large enough array)-->C["O(1) time\n(constant time)"]
D[Worst-Case\nScenario]---E(array is full)-->F["O(n) time\n(linear time)"]
style A fill:#1ad,stroke:#555,stroke-width:2px
style D fill:#1ad,stroke:#555,stroke-width:2px
style B fill:#bbb,stroke:#555,stroke-width:2px
style E fill:#bbb,stroke:#555,stroke-width:2px
style C fill:#0c9,stroke:#555,stroke-width:2px
style F fill:#fc0,stroke:#555,stroke-width:2px
```

**Outcomes: Search**
----

```mermaid
flowchart TD
A[Best-Case\nScenario]-->B(compare to Item)-->C["O(1) time\n(constant time)"]
D[Worst-Case\nScenario]-->E(Item does not exists)-->F["O(n) time\n(linear time)"]
style A fill:#1ad,stroke:#555,stroke-width:2px
style D fill:#1ad,stroke:#555,stroke-width:2px
style B fill:#bbb,stroke:#555,stroke-width:2px
style E fill:#bbb,stroke:#555,stroke-width:2px
style C fill:#0c9,stroke:#555,stroke-width:2px
style F fill:#fc0,stroke:#555,stroke-width:2px
```

**Outcomes: Deletion**
----

```mermaid
flowchart TD
A[Best-Case\nScenario]-->B(Location and delete item)-->C["O(1) time\n(constant time)"]
D[Worst-Case\nScenario]-->E(Search, then locate,then delete item)-->F["O(n) time\n(linear time)"]
style A fill:#1ad,stroke:#555,stroke-width:2px
style D fill:#1ad,stroke:#555,stroke-width:2px
style B fill:#bbb,stroke:#555,stroke-width:2px
style E fill:#bbb,stroke:#555,stroke-width:2px
style C fill:#0c9,stroke:#555,stroke-width:2px
style F fill:#fc0,stroke:#555,stroke-width:2px
```

# Linked List
-------------

**Node** contains data and a pointer.

**Singly List** only have pointers point to next note in the list.

**Double List** have next and previews pointer, can go forward and backward.

**ArrayList**
- Has behavior of a list on the surface
- Stored as an array under the hood

**C#** and **C++** Have a double linkedList.

No built-in linked lists for **Swift**, **Ruby**, and **JavaScript**. But there are third party equivalents.

**Python** lists are not really lists, they are resizable arrays. No built-in linked list implementation.

# Stacks and Queues
-------------------

**Stacks** follow a Last in, First Out (LIFO). Great for programs where \
you need to reverse things. Keeping track of state.

- **Push** add an item to stack.
- **Pop** remove last item from stack.
- **Peek** check the last item of stack without removing it.

**Queue** follow a First in, First Out (FIFO). Good for treads.

- **Enqueue** is when an item is added to a list.
- **Dequeue** is when an item is removed from the list.
- **Peek** see the first item in the queue without removing it.

**Priority Queue** each element has a priority associated with it.

| a             | t            | w               | r
|---            |---           |---              |--
| high priority | low priority | medium priority | high priority

- **a** dequeued first
- Then **r** dequeued
- Then **w** dequeued
- Then **t** dequeued

**D-E-Q-U-E-K** it's a double-ended queue have a stack and queue at the same time. Items can \
be added or removed from either end Items can be added or removed from either end.

# Hash
------

**Associative Array** is Collection of key-value pairs.

Key --> Value
>Key:Value

State --> Capital
>California:Sacramento

**Associated Array Rules**
- Key-value pairs are bound together
- Each key must be unique
- Order isn't important
- Values are accessed with the key
- Values do not need to be unique

**Hashing** is a way of take some raw data and mixing together to \
make a small single data. It's a data conversion process.

**Hash Inputs**
- Characters
- Objects
- Numbers

**Hash output**
- A integer
- They are not reversible

**Collision** occur anytime two inputs produce the same hash value.

**Hash table** is an implementation of the associative array \
abstract data structure.

# Trees and Graphs

**Set**

- A collection of unique items
- Order doesn't matter
- None of the elements are duplicated

**How Set Works**

1. Take an object.
2. Hash the object.
3. Store the object using the index.
4. Repeat and check if object is stored.

**Tree Data Structure** child nodes with the same parent are siblings.

```mermaid
flowchart TD
    1((1 Root\nNode))-->2((2))
    1((1 Root\nNode))-->3((3))
    2((2 Parent\nNode))-->4((4))
    2((2 Parent\nNode))-->5((5))
    3((3))-->6((6))
    3((3))-->7((7))
    4((4 Child\nNode))-->8((8))
    4((4 Child\nNode))-->9((9))
    5((5))-->10((10))
    5((5))-->11((11))
    6((6))-->12((12))
    6((6))-->13((13))
    7((7))-->14((14))
    7((7))-->15((15))
```
>**Constrain:** max two child nodes from any given node.

**What Each Note Can Have**
- Many children
- Just one child
- No children

**Binary Search Tree** have an additional constraint, order.

- Left child node < Parent node
- Right child node > Parent node

```mermaid
flowchart TD
    1((30))-->2(( ))
    1((30))-->3(( ))
    2((20))-->4(( ))
    2((20))-->5(( ))
    3((40))-->6(( ))
    3((40))-->7(( ))
    4(( ))-->8(( ))
    4(( ))-->9(( ))
    5((25))-->10(( ))
    5((25))-->11(( ))
    6((35))-->12(( ))
    6((35))-->13(( ))
    7((50))-->14(( ))
    7((50))-->15((60))
    15((60))-->16(( ))
    15((60))-->17((70))
```

**Heap** is a data structure implemented as a binary tree.

**Priority Queue**
- Order doesn't matter
- Heaps are used to implement

**Binary Search Tree:** maintain sorted order while staying fast for insertion, deletion, and accessing.
**Heaps** are types of binary tree there are great for priority queues.

# Conclusion

Every data structure have their pros and cons and there is no \
perfect data structure.

**Depends on:**
- What do you want to store?
- How do you want to store it?
- How do you want to access it?
