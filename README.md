# insert-newnode-at-any-position-in-LinkList-in-C


#include<stdio.h>
#include<stdlib.h>
struct node{
    int data;
    struct node* next;
    
};

void insert(int data , struct node* head , int pos){
    struct node* newnode ;
    newnode=(struct node*)malloc(sizeof(struct node));
    newnode->data=data;
    
    int i;
    struct node *temp=head;
   
    if(pos==1){
        newnode->data=data;
        newnode->next=head;
        head=newnode;
        
    }
    
    
    for(i=1;i<pos-1;i++){
        temp=temp->next;
    }
    
    newnode->next=temp->next;
    temp->next=newnode;
    printf("after insert=\n");
    while(head!=NULL){
        printf("%d",head->data);
        head=head->next;
        
    }
    
    
}





int main()
{
    int data=0,pos=0;
    printf("enter new data value=");
    scanf("%d",&data);
    printf("enter position=");
    scanf("%d",&pos);
    struct node* head, *second , *third , *fourth , *fifth , *sixth;
    head= (struct node *)malloc(sizeof(struct  node));
    second= (struct node *)malloc(sizeof(struct  node));
    third= (struct node *)malloc(sizeof(struct  node));
    fourth= (struct node *)malloc(sizeof(struct  node));
    fifth= (struct node *)malloc(sizeof(struct  node));
    sixth= (struct node *)malloc(sizeof(struct  node));
    //seven= (struct node *)malloc(sizeof(struct  node));
    
    
    head->data=1;
    head->next=second;
    
    second->data=2;
    second->next=third;
    
    third->data=3;
    third->next=fourth;
    
    fourth->data=4;
    fourth->next=fifth;
    
    fifth->data=5;
    fifth->next=sixth;
    
    sixth->data=6;
    sixth->next=NULL;
    
    insert(data,head,pos);
    
    return 0;
}
