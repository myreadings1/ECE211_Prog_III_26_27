``` C code

// Stack Implementation with Linked List in C
#include <stdio.h>
#include <stdlib.h>
// Declaration of node structure 
struct node {  int value;  struct node *next;  };
struct node *Top = NULL;
///////////////////////////////////////////////////////////////
void Push ( int item)
{
// Insert item at the front of stack
// 1- Create a new node and fill it with data (item)
  struct node *newNode = (struct node *) malloc( sizeof(struct node) );
  newNode->value = item;
  newNode->next = NULL;

// 2- Connect the new node to the front of the stack
// a- if stack is empty, this is the first node  
  if ( NULL == Top )
  { Top = newNode;  }

// b- else, stack is not empty, then connect at the front    
  else{
  newNode->next = Top;
  Top = newNode;
  }
}
///////////////////////////////////////////////////////////////
void PrintStack( )
{
// a- Check if the LL is empty  
  if ( NULL == Top )
  { printf ("Stack is empty.");  }
  else {
  // b- Define temp, which points to Top and traverse all nodes 
  struct node * temp = Top;
  while ( NULL != temp  )  { 
    printf ("%d ", temp->value);
    temp = temp->next ;  
  }
  printf ("\n");
  }
}
///////////////////////////////////////////////////////////////
void Pop ( )
{
// Delete node from front of the LL
// 1- Check if the LL is empty  
    if ( NULL == Top )
    { printf ("Stack is empty.");  }
    
    else{
    // Define temp, which points to Top  
    struct node * temp = Top;
    // Move head to the second node
    Top = Top->next;
    // NULL the pointer (next) of the first node
    temp->next= NULL;
    // Print a message to the user
    printf ("The item: %d will be removed! \n", temp->value );
    free (temp);
    }
}
///////////////////////////////////////////////////////////////
int IsEmpty( )
{
  if ( NULL == Top ){ 
  printf ("Stack is empty.");
  return 0;
  }
  else{ return 1; }
}  
///////////////////////////////////////////////////////////////
int StackSize( )
{
  int count = 0;
  if ( NULL == Top ){ 
  printf ("Stack is empty.");
  }
  else{
  // b- Define temp, which points to Top and traverse all nodes
  struct node * temp = Top;
  // Traverse the LL to the last node.
  while ( NULL != temp  ) { 
  count ++; 
  temp = temp->next ;  
  }
  printf ("Number of Elements in Stack=%d \n", count);
  }
return count;  
}
///////////////////////////////////////////////////////////////
int main() {
  
 Push ( 11 );
 Push ( 12 );
 Push ( 77 );
 Push ( 97 );
 PrintStack( );
 StackSize( );
 Pop ( );
 PrintStack( );
 StackSize( );
 Pop ( );
 PrintStack( );
 StackSize( );
//// The end of code
return 0;
}
///////////////////////////////////////////////////////////////
```
