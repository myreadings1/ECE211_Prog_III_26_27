``` C Code

// Linked list implementation in C
#include <stdio.h>
#include <stdlib.h>
#define SIZE 6 
// Declaration of node structure 
struct node {  int value;  struct node *next;  };

int main() {
// Put all values in one array (call it A)
 int A[ 6 ]= { 77,107,91,9,202,111};

  // Initialize nodes
  struct node *head = NULL;
  struct node *temp = NULL;
  struct node *newNode = NULL;

// Transfer all values A to a linked list 
 for (int i=0; i < 6; i++)
 {
    newNode = (struct node *) malloc( sizeof(struct node) );
    newNode->value = A[i];
    newNode->next = NULL;
    
    // If LL is empty, this means newNode is the first node in the linked list
    if ( NULL == head) 
    {  head = newNode;  }

    // Insert new node at the end of LL
    else {
    // Make temp starts from the first node
    temp = head; 

    // Traverse the LL to the last node. After this loop, temp reaches the last node in the LL
    while ( NULL != temp->next  )
    { temp = temp->next ;  }

    // temp reaches the last node in the LL
    temp->next = newNode;
    }

 }

// Print all nodes in the LL
// a- Make temp starts from the first node and traverse all nodes till the last one 
 temp = head;
 printf ("\n");
 while ( NULL != temp  )
  { 
    printf ("%d ", temp->value);
    temp = temp->next ;  
  }
/////////////////////////////////////////////////////////////////////////////////////  
// Insert 119 at the front of LL
// 1- Create a new node and fill it with data
    newNode = (struct node *) malloc( sizeof(struct node) );
    newNode->value = 119;
    newNode->next = NULL;

// 2- Connect the new node to the end of LL
// a- Check if the LL is empty  
    if ( NULL == head ){
    head = newNode;  }

// b- If LL is not empty, then connect at the front    
    else{
    newNode->next = head;
    head = newNode;
    }

// Print all nodes in the LL
// a- Make temp starts from the first node and traverse all nodes till the last one 
 temp = head;
 printf ("\n");
 while ( NULL != temp  )
  { 
    printf ("%d ", temp->value);
    temp = temp->next ;  
  }
/////////////////////////////////////////////////////////////////////////////////

// Insert 2017 at the end of LL
// 1- Create a new node and fill it with data
    newNode = (struct node *) malloc( sizeof(struct node) );
    newNode->value = 2017;
    newNode->next = NULL;

// 2- Traverse the LL to the last node 
// a- Check if the LL is empty, then newNode will be the first node  
    if ( NULL == head ){
    head = newNode;  }

// b- If LL is not empty, then traverse the LL to the last node    
    else{
    // Make temp starts from the first node and traverse all nodes till the last one
    temp = head;
    while ( NULL != temp->next  )
    { temp = temp->next ;  }

    // Connect the newNode at the end of LL
    temp->next = newNode;
    
    }

 // Print all nodes in the LL
// a- Make temp starts from the first node and traverse all nodes till the last one 
 temp = head;
 printf ("\n");
 while ( NULL != temp  )
  { 
    printf ("%d ", temp->value);
    temp = temp->next ;  
  }
///////////////////////////////////////////////////////////////////////////

// Insert 777 after 91 in the LL
// 1- Create a new node and fill it with data
    newNode = (struct node *) malloc( sizeof(struct node) );
    newNode->value = 777;
    newNode->next = NULL;

// 2- Traverse the LL to till node 91, then connect the new node after 91
// a- Check if the LL is empty  
    if ( NULL == head ){
    printf ("The Linked List is empty. We could not add 777 !");  }

// b- If LL is not empty, traverse LL till node 91    
    else{
    // Make temp starts from the first node and traverse all nodes till the last one
    temp = head;
    while ( 1 )
    { 
      if (  ( 91 == temp->value ) || ( NULL == temp->next ) )
      { break ;}
    
      temp = temp->next ;  
    }
// c- Make sure temp reached node 91 or not  
    if ( 91 == temp->value )
    {
      newNode->next = temp->next;
      temp->next = newNode;
    }
    // If temp did not reach 91, print We could not add 777
    else{
    printf ("There is no node with value 91. We could not add 777 !!");  }
    
    }

 // Print all nodes in the LL
// a- Make temp starts from the first node and traverse all nodes till the last one 
 temp = head;
 printf ("\n");
 while ( NULL != temp  )
  { 
    printf ("%d ", temp->value);
    temp = temp->next ;  
  }
/////////////////////////////////////////////////////////////////////////
// Delete node from front of the LL
// 1- Check if the LL is empty  
    if ( NULL == head ){
    printf ("The Linked List is empty. We could remove node !");  }
    
    else{
    // Make temp starts from the first node and traverse all nodes till the last one 
    temp = head;
    // Move head to the second node
    head = head->next;
    // NULL the pointer (next) of the first node
    temp->next= NULL;
    // Print a message to the user
    printf ("The item: %d will be removed! \n", temp->value );
    free (temp);
    }

 // Print all nodes in the LL
// a- Make temp starts from the first node and traverse all nodes till the last one 
 temp = head;
 printf ("\n");
 while ( NULL != temp  )
  { 
    printf ("%d ", temp->value);
    temp = temp->next ;  
  }

//// The end of code
return 0;
}

```
