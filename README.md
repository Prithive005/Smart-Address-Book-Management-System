# Smart Address Book Management System

A Java-based console application for managing contacts using **Data Structures, Algorithms, and File Handling**.

## Overview

The Smart Address Book Management System provides an efficient way to store, search, delete, and manage contacts.

The project demonstrates how multiple data structures can work together, with each structure being used for a specific operation.

## Features

* Add contacts
* View all contacts
* Search contacts by name
* Delete contacts
* Undo add/delete operations
* Track recent searches
* Prefix-based contact suggestions
* Save contacts to a file
* Load saved contacts automatically
* Store contact creation date and time

## Data Structures

| Data Structure     | Purpose                |
| ------------------ | ---------------------- |
| Doubly Linked List | Stores contacts        |
| HashMap            | Fast contact searching |
| Stack              | Undo operations        |
| Queue              | Recent search history  |
| Trie               | Contact suggestions    |

## How It Works

'
                 Address Book
                      │
        ┌─────────────┼─────────────┐
        │             │             │
   Linked List     HashMap        Trie
   Contact Store   Search      Suggestions
        │
      Stack
       Undo
        │
      Queue
 Recent Searches
        │
     File I/O
   Data Persistence
`

### Contact Storage

Contacts are stored in a **Doubly Linked List**, allowing each contact to maintain links to both the previous and next contact.

### Fast Search

A **HashMap** maps contact names to their corresponding linked-list nodes, providing average **O(1)** search.

### Undo

A **Stack** stores add and delete actions.

``
Last Action → First Action to Undo


This follows the **LIFO** principle.

### Recent Searches

A **Queue** maintains the five most recent successful searches using the **FIFO** principle.

### Contact Suggestions

A **Trie** stores contact names character by character. DFS is used after reaching the requested prefix to find matching contacts.

Example:

``text
Prefix: "pri"

Suggestions:
Pranav
Prithiv
Priya
``

## Complexity

| Operation     | Time Complexity |
| ------------- | --------------: |
| Search        |    O(1) average |
| Delete        |    O(1) average |
| Display       |            O(n) |
| Trie Insert   |            O(L) |
| Prefix Search |        O(P + k) |
| Undo          |    O(1) average |
| Recent Search |            O(1) |
| Save          |            O(n) |

Where:

* `n` = number of contacts
* `L` = length of contact name
* `P` = prefix length
* `k` = number of matching suggestions

## Technologies

* **Java**
* Data Structures & Algorithms
* Object-Oriented Programming
* Java Collections Framework
* File Handling
* Recursion
* Exception Handling

## Project Structure


Smart-Address-Book-Management-System/
│
├── Main.java
├── README.md
├── .gitignore
└── contacts.txt


## Requirements

* Java JDK 17 or later

Check your Java installation:

``bash
java -version
javac -version


## Run the Project

### 1. Clone the repository


git clone https://github.com/Prithive005/Smart-Address-Book-Management-System.git


### 2. Navigate to the project

``
cd Smart-Address-Book-Management-System

### 3. Compile

``bash
javac Main.java
`

### 4. Run

bash
java Main


## Application Menu


┌──────────────────────────────┐
│          PHONE BOOK          │
├──────────────────────────────┤
│ 1. Add Contact               │
│ 2. View Contacts             │
│ 3. Search Contact            │
│ 4. Delete Contact            │
│ 5. Exit                      │
│ 6. Undo                      │
│ 7. Recent Searches           │
│ 8. Suggest Contacts          │
└──────────────────────────────┘


## Data Persistence

Contact information is stored locally in:


contacts.txt


When the application starts, previously saved contacts are loaded automatically.

Each record stores:

``
Name, Phone, Creation Time
 

## Key Concept

The main concept demonstrated by this project is the **combined use of multiple data structures**:

``text
Doubly Linked List → Contact Storage
HashMap            → Fast Search
Trie               → Suggestions
Stack              → Undo
Queue              → Recent Searches
File I/O           → Persistence
``````````
