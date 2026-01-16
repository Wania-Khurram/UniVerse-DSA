#  University Management System (The DS Flex)

> "Because managing a university manually is so 1999."

A comprehensive C++ console application that simulates a university backend. It handles everything from student logins to navigating the campus map, all built from scratch using **User-Defined Data Structures**. No STL containers were harmed (mostly) in the making of this project.

##  What's Under the Hood?

This isn't just a management system; it's a Data Structures showcase. Here’s the breakdown of the logic:

| Feature | Data Structure Used | Why? (The Logic) |
| :--- | :--- | :--- |
| **User Auth** | `Hash Table` (Chaining) | Because looking up a user in O(1) is a flex. Collisions handled via Linked List. |
| **Campus Map** | `Graph` (Adjacency List) | Nodes are buildings, edges are paths. Supports **BFS** & **DFS** traversals. |
| **Room Booking** | `AVL Tree` | Self-balancing tree ensures searching for a room never gets slow, unlike the campus wifi. |
| **Complaints** | `Queue` | First In, First Out. First person to complain gets served first. Fair play. |
| **Messaging** | `Stack` | LIFO. The last message you received is the first one you see. |

##  Features

* **Secure Login/Register:** Role-based access (Admin, Student, Teacher).
* **Campus Navigation:** Add buildings/paths and traverse the map to find your way from the Cafeteria to the CS Block.
* **Room Scheduling:** Reserve labs or classrooms without fighting over them physically.
* **Complaint Portal:** Raise issues about the AC not working (again).
* **Direct Messaging:** Send notes to other users.

##  How to Run

1.  **Clone the repo:**
    ```bash
    git clone [https://github.com/your-username/uni-management-system.git](https://github.com/your-username/uni-management-system.git)
    ```
2.  **Compile the code:**
    ```bash
    g++ main.cpp -o uni_system
    ```
3.  **Run the executable:**
    ```bash
    ./uni_system
    ```
    *(Or just hit F5 in VS Code)*

##  Code Snippet (AVL Tree Rotation)

We don't do lopsided trees here. We rotate.

```cpp
AVLNode* rotateRight(AVLNode* y) {
    AVLNode* x = y->left;
    AVLNode* T2 = x->right;

    x->right = y;
    y->left = T2;

    y->height = max(height(y->left), height(y->right)) + 1;
    x->height = max(height(x->left), height(x->right)) + 1;

    return x;
}
