#  Queue Data Structures in cpp   


queue is FIFO(first in first out) data structure which mean the elements that are at the front of the queue will be push out first for process.   

###  real life example:   
1. queue in the bank
  people who are standing at the front of that queue wii be serve first and continue the order of the queue.
2. [fiil the second example]
3. [fill the third example]

### when to use queue in programming  
whenever you need things to happend in the exact order they were called but your computer cannot keep up with the speed and execute those things face enough then you are going to put those things in a queue.  

The most common example of this is the way that printer work. when you send multiple pages to the print all of the pages will be waiting in a queue and they will be waiting for their turn to be printed. It will print frist page from the queue and continue print pages from the queue by order and last page print last.     

in the code   

in order to be able to use stlq queue you need to include(import) library call "queue"    
```cpp 
#include<queue>
```

let's see how to create queue of intergers   
```cpp
    queue<int> myQueue;  // Declare an empty queue of integers

    // Push elements into the queue (adds to the back)
    myQueue.push(1);
    myQueue.push(2);
    myQueue.push(3);

    // Print the size of the queue
    cout << "Size of queue: " << myQueue.size() << endl;

    // Access the first (front) element of the queue
    cout << "Front element: " << myQueue.front() << endl;

    // Access the last (back) element of the queue
    cout << "Back element: " << myQueue.back() << endl;
 ```

### demonstrating pop() behavior on queue data structure     
* pop() removes the front element from the queue.   
* It does not return the removed element.   
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<string> q;
    
    q.push("Apple");
    q.push("Banana");
    q.push("Cherry");

    cout << "Before pop, front: " << q.front() << endl;

    q.pop(); // Removes "Apple"

    cout << "After pop, front: " << q.front() << endl;

    return 0;
}


/**  RESULT >>
 * Before pop, front: Apple
 * After pop, front: Banana
 */
```



### demonstrating empty() behavior on queue data structure     
* empty() checks whether the queue is empty.   
* returns true if empty, otherwise false.   
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;

    if (q.empty()) {
        cout << "Queue is empty." << endl;
    }

    q.push(100);
    
    if (!q.empty()) {
        cout << "Queue is not empty after push." << endl;
    }

    q.pop(); // Removes the only element

    if (q.empty()) {
        cout << "Queue is empty after pop." << endl;
    }

    return 0;
}

/**  RESULT >>
 * Queue is empty.
 * Queue is not empty after push.
 * Queue is empty after pop.
 */
```

### demonstrating how to print values of queue (TASK)      
```cpp
#include <iostream>
#include <queue>  // Include queue library for using std::queue
using namespace std;

/**
 * Function to print all elements of a queue.
 * Since queue is passed by value, it is copied,
 * meaning the original queue remains unchanged.
 */
void printQueue(queue<int> queue) {
    while (!queue.empty()) {  // Loop until the queue is empty
        cout << queue.front() << " ";  // Print the front element
        queue.pop();  // Remove element from the front of the queue
    }
    cout << endl;
}

int main() {
    queue<int> myQueue;  // Declare an empty queue of integers

    // Push elements into the queue (adds to the back)
    myQueue.push(1);
    myQueue.push(2);
    myQueue.push(3);

    // Print the elements of the queue
    cout << "Queue elements: ";
    printQueue(myQueue);

    // Even after printQueue, myQueue still has its elements
    cout << "Size after printQueue call: " << myQueue.size() << endl;

    return 0;  // Return 0 to indicate successful execution
}

```


# Stack Data Structures in cpp   

Stack is type of data collection which use LIFO (last in first out)/ FILO(first in last out) technique in order to store elements 


###  real life example:   
1. Stack of Plates
   Imagine a stack of plates. If you want to add a plate to this stack, you will place it on top, and if you want to take a plate out, you will remove the one from the top. So, the last plate that was added is going to be the first one that you take out. In other words (synonym), we can say that the first plate that was added is going to be the last one that you take out..   
2. Undo and Redo Functionality of an IDE.   
   When you perform an action in an Integrated Development Environment (IDE), it gets pushed onto an undo stack. If you press "Undo," the last performed action is popped from the stack and reversed. If you then press "Redo," the action is pushed onto a redo stack and reapplied. This mechanism ensures that changes are undone and redone in a LIFO order, maintaining the sequence of user actions.
4. Backward and Forward Buttons on a Browser.   
   When you navigate through web pages, the browser maintains a history stack. Every visited page is pushed onto the stack. Pressing the backward button pops the current page from the stack, taking you to the previous one. If you press the forward button, the page is pushed back onto the stack, restoring the previous state. This ensures seamless navigation while following the LIFO principle.

in order to be able to use stlq stacks you need to include(import) library call "stack"    
```cpp 
#include<stack>
```

let's see how to create stack of intergers   
```cpp
    stack<int> myStack;  // Declare an empty stack of integers

    // Push elements into the stack (adds to the front)
    myStack.push(1); 
    myStack.push(2);
    myStack.push(3);
 ```

### Five most important funtions that accoiate with stacks   
1. empty() – Checks whether the stack is empty or not (returns true if empty, otherwise false).  
2. size() – Returns the total number of elements in the stack.  
3. top() – Returns the top element of the stack without removing it.
4. push(x) – Adds an element x to the top of the stack.
5. pop() – Removes the top element from the stack.

```cpp
#include <iostream>
#include <stack>

using namespace std;

int main() {
    stack<int> myStack;

    // 1. push(): Adds an element to the top of the stack.
    myStack.push(10);
    myStack.push(20);
    myStack.push(30);

    // 2. top(): Returns the element at the top of the stack.
    cout << "Top element: " << myStack.top() << endl; // Output: 30

    // 3. size(): Returns the number of elements in the stack.
    cout << "Stack size: " << myStack.size() << endl; // Output: 3

    // 4. pop(): Removes the top element from the stack.
    myStack.pop();
    cout << "Top after pop: " << myStack.top() << endl; // Output: 20

    // 5. empty(): Checks if the stack is empty.
    cout << "Is stack empty? " << (myStack.empty() ? "Yes" : "No") << endl; // Output: No

    return 0;
}
```
### write function for print all elements in the stack (Task)    
```cpp
// call following function within main method  
void printStackElements(stack<int> stack){
  while (!stack.empty()){
    cout << stack.top() << endl;
    stack.pop();
  }
}
/**  RESULT >>
 * 20
 * 10
 */
```

### Array Representation of Stack (Task)  

Stack can be implemented using an array by maintaining a top index to track the position of the last inserted element.   

The main limitation is that the size of the stack is fixed (determined at compile time). If the stack is full, we cannot add more elements, and if it's empty, memory remains unused.   

Array use static memory allocation and need to implement following stack methods using a array. 
1. empty()  
2. size()   
3. top()   
4. push(x)   
5. pop()

since array have static memory we need to check whether topIndex reaches "MAX-1" before "push()" method (add element) to array implemented of stack.   
```cpp
if (topIndex >= MAX - 1) {
    cout << "Stack Overflow!" << endl;
}
```

before use "pop()" method(remove element) , need to check whether a stack is empty in an array implementation.    
```cpp
if (topIndex < 0) {
    cout << "Stack is empty!" << endl;
}
```
since we are maintain stack using topIndex we can check stack sisze using topIndex.   
```cpp
int size() {
    return topIndex + 1;
}
```

while "pop()" (remove element) method we not actualy remove value but reduce top index by one to ignoring removing value as a garbarge value.  
```cpp
void pop() {
    if (topIndex < 0) {
        cout << "Stack Underflow!" << endl;
        return;
    }
    topIndex--; 
}
```

when we add element to array stuck we add to the end of the array with increasing top index by one.   
```cpp
void push(int value) {
    if (topIndex >= MAX - 1) {
        cout << "Stack Overflow!" << endl;
        return;
    }
    stack[++topIndex] = value; 
}
```

following code show full implementation of array representation of Stack
```cpp
#include <iostream>

using namespace std;

#define MAX 5 // Define the maximum size of the stack

int stack[MAX]; // Array to store stack elements
int topIndex = -1; // Variable to track the top index

// 1. push(x): Adds an element to the stack
void push(int value) {
    if (topIndex >= MAX - 1) {
        cout << "Stack Overflow! Cannot push " << value << endl;
        return;
    }
    stack[++topIndex] = value; // Increment topIndex and insert value
    cout << value << " pushed to stack." << endl;
}

// 2. pop(): Removes the top element from the stack
void pop() {
    if (topIndex < 0) {
        cout << "Stack Underflow! Cannot pop from an empty stack." << endl;
        return;
    }
    cout << stack[topIndex] << " popped from stack." << endl;
    topIndex--; // Decrease topIndex to remove the element
}

// 3. top(): Returns the top element of the stack without removing it
int top() {
    if (topIndex < 0) {
        cout << "Stack is empty!" << endl;
        return -1; // Return -1 to indicate empty stack
    }
    return stack[topIndex];
}

// 4. empty(): Checks whether the stack is empty
bool empty() {
    return (topIndex < 0);
}

// 5. size(): Returns the total number of elements in the stack
int size() {
    return topIndex + 1;
}

// Display function to show stack elements
void display() {
    if (topIndex < 0) {
        cout << "Stack is empty!" << endl;
        return;
    }
    cout << "Stack elements: ";
    for (int i = 0; i <= topIndex; i++)
        cout << stack[i] << " ";
    cout << endl;
}

int main() {
    push(10);
    push(20);
    push(30);
    display(); // Output: 10 20 30

    cout << "Top element: " << top() << endl; // Output: 30

    pop();
    display(); // Output: 10 20

    cout << "Stack size: " << size() << endl; // Output: 2
    cout << "Is stack empty? " << (empty() ? "Yes" : "No") << endl; // Output: No

    return 0;
}

```

### Linked List Representation of stack

here we are discussin about single link-list (data-address)     


```cpp
#include <iostream>

using namespace std;

// Structure to represent a stack node
struct Node {
    int data;   // Data of the stack element
    Node* next; // Pointer to the next element
};

// Global pointer to track the top of the stack
Node* topNode = nullptr;

// Function to check if the stack is empty
bool empty() {
    return topNode == nullptr;  // Returns true if stack is empty
}

// Function to return the total number of elements in the stack
int size() {
    int count = 0;
    Node* current = topNode;
    while (current != nullptr) {
        count++;  // Count each node
        current = current->next;
    }
    return count;
}

// Function to return the top element of the stack without removing it
int top() {
    if (topNode == nullptr) {
        cout << "Stack is empty!" << endl;
        return -1;  // Return -1 if the stack is empty
    }
    return topNode->data;  // Return the value of the top node
}

// Function to push (add) an element onto the stack
void push(int value) {
    Node* newNode = new Node;  // Create a new node dynamically
    newNode->data = value;     // Assign value to the node
    newNode->next = topNode;   // Link the new node to the current top
    topNode = newNode;         // Update topNode to new node
    cout << value << " pushed to stack." << endl;
}

// Function to pop (remove) the top element from the stack
void pop() {
    if (topNode == nullptr) {
        cout << "Stack Underflow! Cannot pop from an empty stack." << endl;
        return;
    }
    Node* temp = topNode;  // Temporary pointer to the top node
    cout << topNode->data << " popped from stack." << endl;
    topNode = topNode->next;  // Move topNode to the next node
    delete temp;  // Delete the old top node
}

// Function to display all elements in the stack
void display() {
    if (topNode == nullptr) {
        cout << "Stack is empty!" << endl;
        return;
    }
    Node* current = topNode;
    cout << "Stack elements: ";
    while (current != nullptr) {
        cout << current->data << " ";  // Print each node's data
        current = current->next;
    }
    cout << endl;
}

int main() {
    // Pushing elements onto the stack
    push(10);
    push(20);
    push(30);
    
    // Display current stack
    display();  // Output: Stack elements: 30 20 10 

    // Checking the top element
    cout << "Top element: " << top() << endl;  // Output: 30

    // Removing the top element
    pop();
    
    // Display stack after pop operation
    display();  // Output: Stack elements: 20 10 

    // Checking the size of the stack
    cout << "Stack size: " << size() << endl;  // Output: 2

    // Checking if stack is empty
    cout << "Is stack empty? " << (empty() ? "Yes" : "No") << endl;  // Output: No

    return 0;
}
```
 






























synonym: similar and opposite words












