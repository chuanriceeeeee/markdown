## Doubly LinkList

### initialize
```
typedef struct DuLNode
{
    ElemType data;
    struct LNode* prior;
    struct LNode* next;
}DuLNode,*DuLinkList;
```
### judge empty
```
head->prior->next==head->next->prior==head
```
### insert
```
//p is after the position s need to insert
s->prior=p->prior;
p->prior->next=s;
s->next=p;
```
