# Linked List in cpp  

sample code of linked list    
```cpp
#include <iostream>
using namespace std;

// define custom node structure
struct Node {
  int Value;
  Node* Next;
};

// search funtion
Node* search(Node* head, int searchValue){
  Node* PTR = head;

  while(PTR != NULL){
    if(PTR->Value == searchValue){
      return PTR;
    }
    PTR = PTR->Next;
  }
  return NULL;
}

int main(){

    // ***** define linked-list *****
    Node* head = new Node();
    Node* second = new Node();
    Node* third = new Node();

    head-> Value = 10;
    head-> Next = second;

    second-> Value = 20;
    second-> Next = third;

    third-> Value = 30;
    third-> Next = NULL;
    // *****************************

    // *** search in linked-list ***
    int searchValue = 10;
    Node* result = search(head, searchValue);

    if(result != NULL){
      cout << "Value " << searchValue << " found at address " << result << endl;
    }else{
      cout << "Value " << searchValue << " not found in the list" << endl;
    }
    //return 0;
}
```

