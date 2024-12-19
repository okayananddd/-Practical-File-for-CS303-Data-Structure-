#include <stdio.h>
#include <stdlib.h>
typedef struct Node {
    int data;
    struct Node* next;
} Node;
Node* head = NULL;
void insertNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;

    if (head == NULL) {
        head = newNode;
        newNode->next = head;
    } else {
        Node* temp = head;
        while (temp->next != head) {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->next = head;
    }
}
void deleteNode(int data) {
    if (head == NULL) {
        return;
    }

    Node* temp = head;
    Node* prev = NULL;
   // If head node holds the data to be deleted
    if (temp->data == data) {
        if (temp->next == head) { // Only one node in the list
            free(temp);
            head = NULL;
        } else {
            while (temp->next != head) {
                temp = temp->next;
            }
            temp->next = head->next;
            free(head);
            head = temp->next;
        }
        return;
    }
    // Search for the node to be deleted
    prev = head;
    temp = head->next;
    while (temp != head) {
        if (temp->data == data) {
            prev->next = temp->next;
            free(temp);
            return;
        }
        prev = temp;
        temp = temp->next;
    }
}
void printList() {
    if (head == NULL) {
        return;
    }
    Node* temp = head;
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while (temp != head);
    printf("\n");
}
void freeList() {
    if (head != NULL) {
        Node* temp = head;
        do {
            Node* nextNode = temp->next;
            free(temp);
            temp = nextNode;
        } while (temp != head);
        head = NULL;
    }
}
int main() {
    insertNode(1);
    insertNode(2);
    insertNode(3);
    insertNode(4);
    printList(); // Output: 1 2 3 4
    deleteNode(3);
    printList(); // Output: 1 2 4
    freeList(); // Free all allocated memory
    return 0;
}
