---
title: Tutorial Implementasi Single Lingked List menggunakan C++
tags: Programming
---

https://www.codementor.io/@codementorteam/a-comprehensive-guide-to-implementation-of-singly-linked-list-using-c_plus_plus-ondlm5azr

## Implementasi Linked List

```cpp
struct node
{
    int data;
    node *next;
};
```

## Membuat Linked List
```cpp
class list
{
    Private:
    node *head, *tail;
    public:
    list()
    {
      head=NULL;
      tail=NULL;
    }
};
```
membuat node baru
```cpp
void createnode(int value)
{
      node *temp=new node;
      temp->data=value;
      temp->next=NULL;
      if(head==NULL)
      {
        head=temp;
        tail=temp;
        temp=NULL;
      }
      else
      { 
        tail->next=temp;
        tail=temp;
      }
}
```
## Menampilkan Linked List
Menampilkan node
```cpp
void display()
{
    node *temp=new node;
    temp=head;
    while(temp!=NULL)
    {
      cout<<temp->data<<"\t";
      temp=temp->next;
    }
} 
```
### Menyisipkan Node
### Menghapus Node
