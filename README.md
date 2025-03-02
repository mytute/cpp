#  Queue Data Structures cpp   


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














