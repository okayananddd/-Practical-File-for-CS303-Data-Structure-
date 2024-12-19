#include <stdio.h>
#include <stdlib.h>
// Define the Node structure for a circular doubly linked list
struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
};
// Define the CircularDoublyLinkedList structure
struct CircularDoublyLinkedList {
    struct Node* head;
};
// Function to initialize a new circular doubly linked list
void initList(struct CircularDoublyLinkedList* list) {
    list->head = NULL;
}
// Function to insert a new node into the circular doubly linked list
void insertNode(struct CircularDoublyLinkedList* list, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    newNode->prev = NULL;

    if (list->head == NULL) {
        list->head = newNode;
        newNode->next = newNode;
        newNode->prev = newNode;
        return;
    }
    struct Node* temp = list->head;
    while (temp->next != list->head) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
    newNode->next = list->head;
    list->head->prev = newNode;
}
// Function to delete a node with a specific value from the circular doubly linked list
void deleteNode(struct CircularDoublyLinkedList* list, int data) {
    if (list->head == NULL) {
        return;
    }
    struct Node* temp = list->head;
   // If the node to be deleted is the head node
    if (temp->data == data) {
        if (temp->next == list->head) {  // Only one node in the list
            list->head = NULL;
            free(temp);
            return;
        }
       temp->prev->next = list->head->next;
        list->head->next->prev = temp->prev;
        list->head = temp->next;
        free(temp);
        return;
    }
    // Traverse the list and find the node to delete
    temp = temp->next;
    while (temp != list->head) {
        if (temp->data == data) {
            temp->prev->next = temp->next;
            temp->next->prev = temp->prev;
            free(temp);
            return;
        }
        temp = temp->next;
    }
}
// Function to print the circular doubly linked list
void printList(struct CircularDoublyLinkedList* list) {
    if (list->head == NULL) {
        return;
    }

    struct Node* temp = list->head;
    printf("%d ", temp->data);
    temp = temp->next;

    while (temp != list->head) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
int main() {
    struct CircularDoublyLinkedList list;
    initList(&list);

    // Insert nodes into the circular doubly linked list
    insertNode(&list, 1);
    insertNode(&list, 2);
    insertNode(&list, 3);
    insertNode(&list, 4);

    // Print the list
    printf("List: ");
    printList(&list);

    // Delete node with value 3
    deleteNode(&list, 3);

    // Print the list after deletion
    printf("List after deletion: ");
    printList(&list);

    return 0;
}
