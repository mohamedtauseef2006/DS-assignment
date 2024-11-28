#include <stdio.h>
#include <stdlib.h>

#define MAX 5

struct Queue {
    int items[MAX];
    int front, rear;
};

// Initialize the queue
void initializeQueue(struct Queue* q) {
    q->front = -1;
    q->rear = -1;
}

// Check if the queue is full
int isFull(struct Queue* q) {
    if ((q->front == 0 && q->rear == MAX - 1) || (q->rear == (q->front - 1) % (MAX - 1))) {
        return 1;
    }
    return 0;
}

// Check if the queue is empty
int isEmpty(struct Queue* q) {
    if (q->front == -1) {
        return 1;
    }
    return 0;
}

// Add an element to the queue
void enQueue(struct Queue* q, int value) {
    if (isFull(q)) {
        printf("Queue is full\n");
        return;
    }

    if (q->front == -1) {
        q->front = 0;
    }

    q->rear = (q->rear + 1) % MAX;
    q->items[q->rear] = value;
    printf("Inserted %d\n", value);
}

// Remove an element from the queue
int deQueue(struct Queue* q) {
    int element;
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }

    element = q->items[q->front];
    if (q->front == q->rear) {
        q->front = -1;
        q->rear = -1;
    } else {
        q->front = (q->front + 1) % MAX;
    }
    printf("Deleted %d\n", element);
    return element;
}

// Get the front element of the queue
int Front(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    return q->items[q->front];
}

// Get the rear element of the queue
int Rear(struct Queue* q) {
    if (isEmpty(q)) {
        printf("Queue is empty\n");
        return -1;
    }
    return q->items[q->rear];
}

int main() {
    struct Queue q;
    initializeQueue(&q);

    enQueue(&q, 1);
    enQueue(&q, 2);
    enQueue(&q, 3);
    enQueue(&q, 4);
    enQueue(&q, 5);

    printf("Front element: %d\n", Front(&q));
    printf("Rear element: %d\n", Rear(&q));

    deQueue(&q);
    enQueue(&q, 6);

    printf("Front element: %d\n", Front(&q));
    printf("Rear element: %d\n", Rear(&q));

    return 0;
}
