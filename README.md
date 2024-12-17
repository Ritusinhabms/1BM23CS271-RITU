![image](https://github.com/user-attachments/assets/347e37a3-0e57-49c1-8abf-32eee0cafc22)(REVERSE)

#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node *next;
};
struct node *head=NULL;
void reverse()
{
    struct node *prevnode,*currentnode,*nextnode;
    prevnode=0;
    currentnode=nextnode=head;
   while(nextnode!=NULL)
   {
       nextnode=nextnode->next;
       currentnode->next=prevnode;
       prevnode=currentnode;
       currentnode=nextnode;

   }
   head=prevnode;
}

void displaylist()
{
    struct node *temp;
    temp=head;
    while(temp!=NULL)
    {
        printf("%d ->",temp->data);
        temp=temp->next;
    }
    printf("NULL\n");
}
void push(int x)
{
    struct node *newnode;
    newnode=(struct node*)malloc(sizeof(struct node));
    newnode->data=x;
    newnode->next=head;
    head=newnode;
}
int main()
{
    push(20);
    push(30);
    push(40);
    printf("original list:");
    displaylist();
    reverse();
    printf("reversed list:");
    displaylist();
}

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void concat(struct Node** head, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* temp = *head;

    new_node->data = data;
    new_node->next = NULL;

    if (*head == NULL) {
        *head = new_node;
    } else {
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = new_node;
    }
}

void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

void concatenate(struct Node** list1, struct Node** list2) {
    if (*list1 == NULL) {
        *list1 = *list2;
        return;
    }

    struct Node* last = *list1;
    while (last->next != NULL) {
        last = last->next;
    }

    last->next = *list2;
}



(CONCATENATION)

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void concat(struct Node** head, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* temp = *head;

    new_node->data = data;
    new_node->next = NULL;

    if (*head == NULL) {
        *head = new_node;
    } else {
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = new_node;
    }
}

void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

void concatenate(struct Node** list1, struct Node** list2) {
    if (*list1 == NULL) {
        *list1 = *list2;
        return;
    }

    struct Node* last = *list1;
    while (last->next != NULL) {
        last = last->next;
    }

    last->next = *list2;
}

int main() {
    struct Node* list1 = NULL;
    struct Node* list2 = NULL;

    concat(&list1, 10);
    concat(&list1, 20);
    concat(&list1, 30);

    concat(&list2, 40);
    concat(&list2, 50);
    concat(&list2, 60);

    printf("Original list1:\n");
    display(list1);

    printf("Original list2:\n");
    display(list2);

    concatenate(&list1, &list2);

    printf("Concatenated list1 and list2:\n");
    display(list1);

    return 0;
}

(SORT)

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void insert(struct Node** head, int data) {
    struct Node* new_node = (struct Node*)malloc(sizeof(struct Node));
    struct Node* temp = *head;
    new_node->data = data;
    new_node->next = NULL;
    
    if (*head == NULL) {
        *head = new_node;
    } else {
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = new_node;
    }
}

void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

void sort(struct Node* head) {
    struct Node* i;
    struct Node* j;
    int temp;
    for (i = head; i != NULL; i = i->next) {
        for (j = i->next; j != NULL; j = j->next) {
            if (i->data > j->data) {
                temp = i->data;
                i->data = j->data;
                j->data = temp;
            }
        }
    }
}

int main() {
    struct Node* list = NULL;
    
    insert(&list, 30);
    insert(&list, 10);
    insert(&list, 50);
    insert(&list, 20);
    insert(&list, 40);
    
    printf("Original list:\n");
    display(list);
    
    sort(list);
    
    printf("Sorted list:\n");
    display(list);
    
    return 0;
}


