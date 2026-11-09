``` C code

#include <stdio.h>
#include <stdlib.h>
// Define the node structure
struct Node {   int data;   struct Node* next;};
// Global pointers to keep track of the front and rear of the queue
struct Node* front = NULL;
struct Node* rear = NULL;
////////////////////////////////////////////////////
// Function to add an element to the queue (Insertion at Rear)
void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (newNode == NULL) { printf("Queue Overflow (Out of memory)\n");
        return;   
     }
    newNode->data = value;
    newNode->next = NULL;
    // If the queue is empty, both front and rear point to the new node
    if (front == NULL && rear == NULL) {
        front = rear = newNode;  
        } 
    else{
    // Link the old rear node to the new node, then update the rear pointer
        rear->next = newNode;
        rear = newNode;
    }
    printf("Enqueued: %d\n", value);
}
////////////////////////////////////////////////////
// Function to remove an element from the queue (Deletion from Front)
void dequeue() {
    // Check for Underflow
    if (front == NULL) {  printf("Queue Underflow (Queue is empty)\n");
        return;   }
    struct Node* temp = front;
    printf("Dequeued: %d\n", front->data);
    // Move front to the next node
    front = front->next;
    // If front becomes NULL, set rear to NULL as well (Queue is now empty)
    if (front == NULL) {
        rear = NULL;
    }
    // Free the memory of the old front node
    free(temp);
}
////////////////////////////////////////////////////
// Function to print all elements in the queue
void display() {
    if (front == NULL) {
        printf("Queue is empty\n");
        return;
    }
    
    struct Node* temp = front;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n\n");
}
////////////////////////////////////////////////////
int main() {
    // Insert elements into the queue
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(55);

    printf("Queue after Enqueue operations: ");
    display();

    // Remove elements from the queue
    dequeue();
    dequeue();

    printf("Queue after Dequeue operations: ");
    display();
    return 0;
}




```
