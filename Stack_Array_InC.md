``` C Code

// Stack implementation with Array in C
#include <stdio.h>
#include <stdlib.h>

#define SIZE 10
// Creating a structure to hold stack elements
struct stack {
  int items[SIZE];
  int Top;
};

// Add elements into stack
void push(struct stack *s, int newitem) 
{
  if ( SIZE-1 == s->Top) {   printf("STACK FULL");  } 
  else {
    s->Top++;
    s->items[s->Top] = newitem;
  }
}

// Remove element from stack
void pop (struct stack *s) 
{
  if ( -1 == s->Top ) {   printf("\n STACK EMPTY \n");  } 
  else {
    printf("Item popped= %d", s->items[ s->Top ] );
    s->Top--;
  }
  printf("\n");
}

// Print elements of stack
void printStack(struct stack *s) 
{
  printf("Stack: ");
  for (int i = 0; i <= s->Top ; i++) 
  {   printf("%d ", s->items[i]);  }
  printf("\n");
}

// Driver code
int main() {
struct stack s1;
// Stack initialization
 s1.Top = -1;
  
 push( &s1, 11);
 push( &s1, 21);
 push( &s1, 32);
 push( &s1, 48);
 
 printStack( &s1 );

 pop ( &s1 );

 printf("\nAfter popping out\n");
 printStack( &s1 );
}
```
