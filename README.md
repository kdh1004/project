# project
report

1. #include <stdio.h>
#include <stdlib.h>
typedef struct list {
	int d;
	struct list* p;
}LIST;
LIST* root = NULL;
LIST* last = NULL;
void AddList(int a) {
	LIST* r = (LIST*)malloc(sizeof(LIST));
	r->d = a; 
	r->p = NULL;
	if (root == NULL)root = r;
	else last->p = r;
	last = r;
}
int main(void) {
	AddList(35);
	AddList(40);
	AddList(45);
	while (root) {
		printf("%d\n", root->d);
		root = root->p;
	}
}



-------------------------

2. #include <stdlib.h>               /* malloc */
typedef struct Tree {
    struct Tr *l, *r;
    int d;
} T;
void print(T* p){
   printf("%d\n", p->d);
   if(p->l) print(p->l);
   if(p->r) print(p->r);    
}
T* mem(){
 T* p=(T*)malloc(sizeof(T));
 p->l=p->r=NULL;
 return(p);
}
int main(void){
    T *r, *r1, *r2, *l1;
    l1= (T*)mem(); l1->d=3; 
    r2= (T*)mem(); r2->d=8; 
    r1= (T*)mem(); r1->d=7; r1->r=r2;
    r= (T*)mem(); r->d=5; r->l=l1;  r->r=r1;
    print(r);
}

-----------------------

3.
