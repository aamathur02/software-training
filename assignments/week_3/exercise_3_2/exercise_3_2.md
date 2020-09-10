# Exercise 3.2

Welcome to exercise 3.2. This exercise will test your ability to create and use pointers. This exercise will expect you to know all the information in the Codecademy C++ course through the References and Pointers section. Our own video on Resources, Lifetime, and Ownership is not needed but will help you get a better understanding of pointers and their use.

# Exercise Statement

In this exercise you will finish writing the code needed to create a linked list. A linked list is a data structure that holds data, similar to a vector. A linked list is made up of nodes in a line each which contains two pieces of information:
1. Whatever data you want to store in the linked list (in this case a string)
2. A pointer to the next data
However, the linked list itself does not keep track of the pointer of each piece of data, but instead only keeps track of the first, or head, node. From the head pointer it is possible to iterate through and access the entire list. You will be creating some functions that help use a linked list, this includes functions that remove data and add new data at specific locations and also one to print the whole list out. 

# Starting Off

We have given you a linked_list.hpp header file which contains the class definitions of both the Node class, which stores a name as a string and the pointer to the next node, and the LinkedList class. LinkedList will have one private variable call head, which is a pointer to a Node. Its public members are all methods and are add_to_front, add_to_back, add_at_index, remove_from_front, remove_from_back, remove_from_index, and print_names. It will be your task to define these functions in linked_list.cpp. There is also a constructor which has been done for you. In the linked_list.cpp file you will see the constructors for both Node and LinkedList have been defined for you, but the rest of the functions have empty definitions. 

```c++
#include <string>
#include <vector>

class Node {
public:
    std::string name;
    Node *next;
};

class LinkedList {
private:
    Node *head;
public:

    LinkedList();

    void add_to_front(std::string name);

    void add_to_back(std::string name);

    void add_at_index(std::string name, int index);

    void remove_from_front();

    void remove_from_back();

    void remove_at_index(int index);

    void print_names();

};
```

# Steps
### add_to_front:
1. Create a new variable that is a pointer to a Node
2. Set the name of the name of the new node to the name parameter passed into the function
3. Set the new node’s next variable to the head pointer of the linked list
4. Set the head of the linked list to the new node pointer
### add_to_back:
1. Create a new variable that is a pointer to a Node
2. Set the name of new node pointer to be the name parameter and set its next pointer to NULL
3. Create an if else statement that checks if the linked list is empty by checking if the head is NULL
4. Within the if statement create a variable that is a pointer to a Node and define set it to the head pointer called curr
5. Within the if statement create a while loop that sets curr to its next pointer while the next pointer of curr is not NULL
6. Outside of the loop and inside the if statement set curr’s next pointer to be the new node pointer
7. In the else statement set head to be the new node pointer
### add_at_index:
1. Create a new variable that is a pointer to a Node
2. Set the name of new node pointer to be the name parameter
3. Create an if else statement that checks if the index is not 0
4. In the if statement create a variable that is a pointer to a Node and define set it to the head pointer called curr
5. In the if statement create a for loop that iterates index-1 number of times that sets curr to its next pointer
6. Outside of the loop in the if statement set the new node’s next pointer to curr’s next pointer
7. In the if statement set curr’s next pointer to the new node pointer
8. In the else statement use the same technique in add to front to make the new node pointer the head
9. remove_from_front:
10. Create an if statement that checks that the linked list is not empty
11. Within the if statement set head to head’s next pointer
### remove_from_back:
1. Create an if statement that checks if the linked list is empty
2. Within the if statement write an if else statement that checks if a second node exists
3. Within this if statement create a node pointer called curr that points to the first node
4. Create a while loop which sets curr to its next pointer while the node after curr’s next pointer is not NULL
5. Outside of this loop set curr’s next pointer to NULL
6. In the else statement set head to NULL
### remove_at_index: 
1. Create an if statement to check if the linked list is empty
2. Create an if else statement to check that index is not 0
3. In the if statement define a variable called curr and use it with a loop iterate through the linked list to the index-1 position
4. Set curr’s next pointer to curr’s next node’s next pointer
5. In the else statement set head to be head’s next pointer
### print_names:
1. Using a new pointer to the head iterate through the linked list with a while loop with
2. Within the while loop create a print statement which prints the name of the current node with a tab after it (“\t” will create a tab)
3. After all the names get printed, print a new lines so the list is on its own line

# Expected Results:
After compiling and running main.cpp (remember to link the other files) the following should be printed onto the terminal:
```
Kyle    
Daniel  Kyle    
Hussain Daniel  Kyle    
Hussain Kyle    
Hussain Kyle    Oswin   
Hussain Kyle    Jason   Oswin   
Hussain Kyle    Jason   
Hussain Kyle    Jason   Woodward    
Kyle    Jason   Woodward    
```