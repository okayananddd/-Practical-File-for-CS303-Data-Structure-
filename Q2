#include <stdio.h>
#include <stdlib.h>

// Define the Node structure
struct Node {
   int data;
   struct Node *next;
};

// Global head pointer for the linked list
struct Node* head = NULL;

// Function to insert a new node at the beginning of the list
void insert(int new_data) {
   struct Node* new_node = (struct Node*) malloc(sizeof(struct Node));
   new_node->data = new_data;
   new_node->next = head;
   head = new_node;
}

// Function to display the linked list
void display() {
   struct Node* ptr = head;
   while (ptr != NULL) {
      printf("%d ", ptr->data);
      ptr = ptr->next;
   }
}

int main() {
   // Insert some data into the linked list
   insert(3);
   insert(1);
   insert(7);
   insert(2);
   insert(9);

   // Display the linked list
   printf("The linked list is: ");
   display();

   return 0;
}
