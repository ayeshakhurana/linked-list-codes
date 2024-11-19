#include<stdio.h>
#include<stdlib.h>
typedef struct scdnode{
    int info;
    struct scdnode *next;
    struct scdnode *prev;
}scd;
scd *insert_beg(scd *head){
    scd *temp;
    temp=(scd*)malloc(sizeof(scd));
    if(temp==NULL){
        return head;
    }else if(head==NULL){
        printf("enter element to be inserted at beginning: ");
        scanf("%d",&temp->info);
        temp->next=temp->prev=head;
        head=temp;
    }else{
        scd *p1=head;
        scd *last;
        last=head->prev;
        temp->next=p1;
        temp->prev=last;
        p1->prev=last->next=temp;
        head=temp;
        return head;
    }
}
scd *insert_last(scd *head){
    scd *temp;
    temp=(scd*)malloc(sizeof(scd));
    if(temp==NULL){
        return head;
    }else if(head==NULL){
        printf("enter element to be inserted at beginning: ");
        scanf("%d",&temp->info);
        temp->next=temp->prev=temp;
        head=temp;
    }else{
        scd *p1=head;
        scd *last;
        last=head->prev;
        temp->prev=last;
        temp->next=p1;
        last->next=temp;
        head->prev=temp;
        return head;
    }
}
scd *insert_at_pos(scd *head){
    int k;
    printf("enter position at which element is to be inserted:");
    scanf("%d",&k);
    scd *temp;
    temp=(scd*)malloc(sizeof(scd));
    if(temp==NULL){
        printf("memory not allocated: ");
        return head;
    }else if(head==NULL){
        printf("enter element to be inserted at beginning: ");
        scanf("%d",&temp->info);
        temp->next=temp->prev=temp;
        head=temp;
    }else if(k==1){
        printf("enter element to be inserted at beginning: ");
        scanf("%d",&temp->info);
        scd *p1=head;
        scd *last;
        last=head->prev;
        temp->next=p1;
        temp->prev=last;
        p1->prev=last->next=temp;
        head=temp;
        return head;
    }else{
        scd *p1=head;
        for(int i=1;i<k;i++){
            p1=p1->next;
        }
        scd *p2;
        p2=p1->next;
        temp->prev=p1;
        temp->next=p2;
        p1->next=temp;
        p2->prev=temp;
        return head;
    }
}
scd *delete_beg(scd *head){
    if(head==NULL){
        return head;
    }else{
        scd *p1=head, *p3=head,*p2;
        scd *last;
        last=head->prev;
        p2=p1->next;
        while(p1->next!=head){
            p1=p1->next;
        }
        p1->next=p2;
        p2->prev=last;
        free(p3);
        head=p2;
        return head;
    }
}
scd *delete_last(scd *head){
    if(head==NULL){
        return head;
    }else{
        scd *p2=head, *p1=head;
        while(p1->next!=head){
            p2=p1;
            p1=p1->next;
        }
        p2->next=head;
        free(p1);
        return head;
    }
}
void display(scd *head){
    if(head==NULL){
        printf("list is empty \n");
        return ;
    }else{
        scd *p1=head;
        while(p1->next !=head){
            printf("%d",p1->info);
            p1=p1->next;
        }
        printf("%d",p1->info);
        return ;
    }
}
int main(){
    scd *head=NULL;
    int ch;
    do{
        printf("enter your choice: \n 1. insert at beginning \n 2. insert at last \n 3. delete from beginning \n 4. deletr from last \n 5. display\n 6. insert at k \n");
        scanf("%d",&ch);
        switch(ch){
            case 1:
                    head=insert_beg(head);
                    printf("list after insertions is: \n");
                    display(head);
                    break;
            case 2:
                    head=insert_last(head);
                    printf("list after insertion is : \n");
                    display(head);
                    break;
            case 3:
                    head=delete_beg(head);
                    printf("list after deletion is: \n");
                    display(head);
                    break;
            case 4:
                    head=delete_last(head);
                    printf("list after deletion is: \n");
                    display(head);
                    break;
            case 5:
                    printf("list is: \n");
                    display(head);
                    break;
            case 6:
                    head=insert_at_pos(head);
                    printf("list is: \n");
                    display(head);
                    break;
        }
    }while(ch!=7);
    return 0;
}
