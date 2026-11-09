``` C code
#include <stdio.h>
#define SIZE 5
// Array and index tracking variables
int items[SIZE];
int front = -1;
int rear = -1;
/////////////////////////////////////////////////////
// Function to add an element to the queue
void enqueue(int value) {
    // Check for Overflow condition
    if (rear == SIZE - 1) { printf("Queue is Full\n");
    } else {
        // If it is the first element, reset front to 0
        if (front == -1) {
            front = 0;
        }
        rear++;
        items[rear] = value;
        printf("Enqueued: %d\n", value);
    }
}
/////////////////////////////////////////////////////
// Function to remove an element from the queue
void dequeue() {
    // Check for Underflow condition
    if (front == -1 || front > rear) {
        printf("Queue is Empty.\n");
    } else {
        printf("Dequeued: %d\n", items[front]);
        front++;
        
        // Reset the queue to initial state if it becomes empty
        if (front > rear) {
            front = rear = -1;
        }
    }
}
/////////////////////////////////////////////////////
// Function to display the element of the queue
void display() {
    if (rear == -1) { printf("Queue is Empty\n");
    } else {
        int i;
        for (i = front; i <= rear; i++) {
            printf("%d ", items[i]);
        }
        printf("\n");
    }
}
/////////////////////////////////////////////////////
int main() {
    // Attempting dequeue on empty queue
    dequeue();

    // Inserting elements
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(50);

    // Attempting enqueue on full queue
    enqueue(60);

    printf("\nQueue elements: ");
    display();

    // Removing elements
    dequeue();
    dequeue();

    printf("\nQueue elements after two deletions: ");
    display();

    return 0;
}

```
