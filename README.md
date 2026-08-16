# Student Management System – DSA Project

A menu-driven **Student Management System in Python** built to practice core **Data Structures and Algorithms (DSA)** concepts.

The project uses multiple data structures for different tasks:

* **Singly Linked List** for registered students
* **Stack** for undoing deleted students
* **Queue** for students waiting for registration
* **Bubble Sort, Selection Sort, and Insertion Sort** for sorting students by marks

## Project Objective

The main goal of this project is to understand how common data structures work internally instead of relying only on Python's built-in implementations.

The system demonstrates how linked lists, stacks, queues, searching, deletion, and sorting algorithms can be used together in one practical application.

## Data Structures Used

### 1. Student Linked List

Registered students are stored in a **singly linked list**.

Each student node contains:

```python
student_id
name
marks
next
```

Example:

```text
head
 ↓
[101, Ali, 78] → [102, Sara, 91] → [103, Ahmed, 67] → None
                                                       ↑
                                                      tail
```

The linked list supports:

* Add student
* Display students
* Search student by ID
* Delete student by ID
* Sort students by marks

## 2. Undo Stack

Deleted students are stored in a **stack** so the most recently deleted student can be restored.

A stack follows:

```text
LIFO
Last In, First Out
```

Example:

```text
top
 ↓
Student 103
 ↓
Student 102
 ↓
Student 101
```

If Undo is selected, `Student 103` is restored first.

The stack supports:

* `push()`
* `pop()`
* `peek()`
* `is_empty()`

## 3. Student Waiting Queue

Students waiting for registration are stored in a **queue**.

A queue follows:

```text
FIFO
First In, First Out
```

Example:

```text
front                     rear
 ↓                          ↓
Ali → Sara → Ahmed → None
```

Ali entered the queue first, so Ali will be processed first.

When a student is processed:

```text
Waiting Queue
      ↓
dequeue()
      ↓
Registration
      ↓
Student Linked List
```

The queue supports:

* `enqueue()`
* `dequeue()`
* `peek()`
* `is_empty()`

## Sorting Algorithms

Students can be sorted according to their marks using three algorithms.

### Bubble Sort

Bubble Sort compares adjacent students and swaps them when they are in the wrong order.

Example:

```text
20 → 19 → 30

20 > 19

19 → 20 → 30
```

### Selection Sort

Selection Sort finds the student with the minimum marks from the remaining portion of the list and places that student in the correct position.

Example:

```text
20 → 30 → 15 → 25

Minimum = 15

15 → 30 → 20 → 25
```

The process continues until the list is sorted.

### Insertion Sort

Insertion Sort keeps part of the list sorted and inserts each new element into its correct position.

Example:

```text
[19, 20, 30] | 15
```

After inserting `15`:

```text
[15, 19, 20, 30]
```

## Main Features

The system includes the following menu options:

```text
1. Add Student
2. Display Students
3. Search Student by ID
4. Delete Student
5. Undo Last Delete
6. Bubble Sort by Marks
7. Selection Sort by Marks
8. Insertion Sort by Marks
9. Add Student to Waiting Queue
10. Process Next Student
11. View Next Student in Queue
12. Exit
```

## System Flow

```text
                  Student Management System
                           |
        -------------------------------------------
        |                  |                     |
   Waiting Queue      Student List          Undo Stack
        |                  |                     |
 New Students       Registered Students    Deleted Students
        |                  |                     |
    dequeue()          Add/Search/Delete        pop()
        |                  |                     |
        └──────────→ Registration ←──────────────┘
```

## Example Workflow

A new student arrives for registration:

```text
Ali
```

Ali is added to the waiting queue:

```text
front/rear
    ↓
   Ali
```

Another student arrives:

```text
front        rear
 ↓             ↓
Ali → Sara → None
```

When the next student is processed:

```text
Ali
```

is removed from the queue and added to the registered student list.

```text
Waiting Queue:

Sara → None
```

```text
Student List:

Ali → None
```

If Ali is deleted:

```text
Student List:

None
```

Ali is saved in the undo stack:

```text
Undo Stack:

top
 ↓
Ali
```

Selecting Undo restores Ali to the student list.

## DSA Concepts Practiced

This project covers:

* Python classes and objects
* References
* Nodes
* Singly linked lists
* Head and tail references
* Linked-list traversal
* Searching
* Insertion
* Deletion
* Stack ADT
* LIFO
* Queue ADT
* FIFO
* Bubble Sort
* Selection Sort
* Insertion Sort
* Basic time-complexity analysis

## Time Complexity

| Operation             | Time Complexity |
| --------------------- | --------------: |
| Add student with tail |            O(1) |
| Display students      |            O(n) |
| Search student        |            O(n) |
| Delete student by ID  |            O(n) |
| Stack push            |            O(1) |
| Stack pop             |            O(1) |
| Queue enqueue         |            O(1) |
| Queue dequeue         |            O(1) |
| Bubble Sort           |           O(n²) |
| Selection Sort        |           O(n²) |
| Insertion Sort        |           O(n²) |

## Technologies Used

* Python 3
* Object-Oriented Programming
* Data Structures and Algorithms

No external libraries are required.

## Running the Project

Clone the repository:

```bash
git clone https://github.com/Zakria774/Student_management_system.git
```

Move into the project directory:

```bash
cd student-management-system
```

Run the Python program:

```bash
python main.py
```

Depending on your system, you may need:

```bash
python3 main.py
```

## Suggested Project Structure

```text
student-management-system/
│
├── main.py
└── README.md
```

The entire program can initially remain inside `main.py`.

As the project grows, it can later be separated into files such as:

```text
student-management-system/
│
├── main.py
├── student.py
├── linked_list.py
├── stack.py
├── queue.py
└── README.md
```

## Future Improvements

Possible improvements include:

* Prevent duplicate student IDs
* Update student information
* Sort students by name or ID
* Display the waiting queue
* Keep multiple undo operations
* Add redo functionality
* Save student records to a file
* Load records when the program starts
* Add validation for marks and IDs
* Add a graphical user interface
* Add additional sorting algorithms

## Learning Purpose

This project is designed primarily for **DSA practice**.

Built-in structures such as Python's `deque`, automatic sorting with `sort()`, or other ready-made implementations are intentionally avoided where possible so that the underlying algorithms and data structures can be implemented manually.

## Author

Developed as a Python Data Structures and Algorithms learning project.
