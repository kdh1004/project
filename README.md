# project
report

1. 
![image](https://user-images.githubusercontent.com/50905795/68380123-954e2180-0192-11ea-983d-dbca26367f3b.png)

리스트란 추상적 자료형, 자료구조의 하나이다. 순서를 가지고 일렬로 나열한 값들의 모임으로 정의된다. 
갈림길이 없이 일렬로 나열되어있어 처음과 끝이 명확하다는 점에서 그래프와 구별된다.
리스트의 각 원소에 순서대로 번호를 붙일 수도 있으며 이 번호를 사용해서 임의의 원소를 찾을 수 있는 연산을 추가할 수 있다. 그런 점에서 배열을 리스트의 일종으로 보기도 한다.
연결 리스트 - 노드를 단위로 하며 노드는 조료와 다음 노드를 가리키는 참조값으로 구성되어 있다. 노드가 아무것도 가리키지 않으면 리스트의 끝이다.
원형 연결 리스트 - 각 노드는 다음 노드를 가리키고, 마지막 노드가 처음 노드를 가리키는 연결 리스트이다.
이중 연결 리스트 - 각 노드는 이전 노드와 다음 노드를 가리키는 참조값으로 구성된다. 처음 노드의 이전 노드와 마지막 노드의 다음 노드는 없다.

#include <stdio.h>
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

2. 
![image](https://user-images.githubusercontent.com/50905795/68379924-3092c700-0192-11ea-88a8-6c90d0ef1499.png)

트리 구조란 여러 노드가 한 노드를 가리킬 수 없는 구조이다. 부모 노드 밑에 자식 노드가, 또 자식 노드 밑에 자식 노드가 연결되는 재귀적 형태의 자료구조이다.
이진 트리 - 부모 노드 밑에 자식 노드가 2개까지만 올 수 있는 형태이다. 두 자식 노드는 왼쪽과 오른쪽으로 구분지어 두 개의 포인터를 가진 구조로 구현할 수 있다.
b-tree - 이진 트리를 확장한 것으로 자식 노드가 2개 이상을 가질 수 있는 노드이다. 이것이 확장되어 2-3-4 트리나 b+트리라는 트리도 있다.
포레스트 - 하나 이상의 트리로 이루어진 집합을 포레스트라고 부른다.

#include <stdlib.h>               /* malloc */
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
![image](https://user-images.githubusercontent.com/50905795/68379975-4acca500-0192-11ea-83d3-2c1a2e3b1f07.png)
그래프란 정점과 정점들을 연결하는 변으로 구성된다. 일반적으로 정점은 원으로 표현하고 변은 화살표나 선분으로 표시한다.
유방향 그래프 — 간선의 방향이 존재하는 그래프이다. 그 방향으로만 이동할 수 있다.
무방향 그래프 — 모든 간선이 방향을 가지지 않는 그래프이다. 어느 방향이든 이동할 수 있다.
비가중치 그래프 — 모든 간선에 가중치가 없는 그래프이다. 여기서 가중치란, 변에 대한 특정한 수치를 뜻한다.
그래프는 두 가지 방식으로 구현할 수 있는데, 인접 행렬은 2차원 배열을 사용하는 방식이며 인접 리스트는 리스트를 사용하는 방식이다.

#include<stdio.h>
int a[1000][1000];
int n, m;
int main(void) 
  scanf_s("%d %d", &n, &m);
  for (int i = 0; i < m; i++) 
  {
    int x, y;
    scanf_s("%d %d", &x, &y);   
    a[x][y] = 1;
    a[y][x] = 1;   
  }
  for (int i = 0; i <= n; i++) 
  {
    for (int j = 0; j <= n; j++) 
    {
        printf("%d ", a[i][j]);
	}
	    printf("\n");
	}  
    system("pause");
}

-----------------------

