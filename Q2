#include <stdio.h>
#include <stdlib.h>

// Define a structure to represent a stack node
struct StackNode {
    int data;
    struct StackNode *next;
};

// Define a structure for the stack
struct Stack {
    struct StackNode *top;  // Pointer to the top node in the stack
};
// Function to initialize the stack
void initStack(struct Stack* stack) {
    stack->top = NULL;
}
// Function to check if the stack is empty
int isEmpty(struct Stack* stack) {
    return stack->top == NULL;
}
// Function to push an element onto the stack
void push(struct Stack* stack, int element) {
    struct StackNode* newNode = (struct StackNode*)malloc(sizeof(struct StackNode));
    newNode->data = element;
    newNode->next = stack->top;
    stack->top = newNode;
}
// Function to pop an element off the stack
int pop(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Error: Stack is empty.\n");
        return -1;
    }
    int element = stack->top->data;
    struct StackNode* temp = stack->top;
    stack->top = stack->top->next;
    free(temp);
    return element;
}
// Function to peek at the top element of the stack
int peek(struct Stack* stack) {
    if (isEmpty(stack)) {
        printf("Error: Stack is empty.\n");
        return -1;
    }
    return stack->top->data;
}
int main() {
    struct Stack stack;  // Create a stack object
    initStack(&stack);   // Initialize the stack

    // Push some elements onto the stack
    push(&stack, 1);
    push(&stack, 2);
    push(&stack, 3);

    // Print the top element of the stack
    printf("Top element: %d\n", peek(&stack));
    // Pop an element off the stack
    printf("Popped element: %d\n", pop(&stack));
    // Print the top element of the stack again
    printf("Top element: %d\n", peek(&stack));
    return 0;
}
