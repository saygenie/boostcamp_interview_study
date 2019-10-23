# 자료구조
## B Tree, B+ Tree
### BTree
#### 규칙
> 노드의 자료수가 N이라면 자식의 수는 N+1이어야 한다. 
각 노드의 자료는 정렬된 상태여야 한다.
노드의 자료 Dk의 왼쪽 서브트리는 Dk보다 작은 값들이고 오른쪽 서브트리는 Dk보다 큰 값들이어야 한다.
Root 노드는 적어도 2개이상의 자식을 가져야 한다.
Root 노드를 제외한 모든 노드는 적어도 M/2개의 자료를 가지고 있어야 한다.
외부 노드로 가는 경로의 길이는 모두 같다. - 외부노드는 모두 같은 레벨에 있다
입력자료는 중복될 수 없다. 

#### 삽입

출처: https://wangin9.tistory.com/entry/B-tree-B-tree [잉구블로그]

![](https://i.imgur.com/rp80IRK.png)

### B+ Tree
> B+ 트리의 데이터는 리프 노드에 저장해 둔다.
> 리프 노드의 형제들은 자신의 옆 노드에 대한 포인터를 가지고 있다.

![](https://i.imgur.com/UimPK2E.png)
![](https://i.imgur.com/wlOg6Xf.png)

### 1. B-Tree


B-tree는 Binary Search Tree를 확장한 Tree로 각 Node는 여러개의 Key를 가질 수 있고, 여러개의 Child를 가질 수 있다. 또한 모든 Leaf Node는 동일한 Depth를 갖고 있다. Key는 B-tree 알고리즘에 따라 정렬되어 각 Node에 배치된다. [그림 1]은 3 Order B-Tree를 나타내고 있다. 각 Node는 최대 2개의 Key를 가질 수 있고, 최대 3개의 Child를 가질 수 있다.

각 Node에는 여러개의 Key를 갖고 있고 각 Key에 대응하는 Data도 함께 갖고 있다. 하나의 Node에 여러개의 Key를 갖기 때문에 Block 단위로 Data를 Read/Write하는 Disk 환경에서는 Binary Search Tree보다 B-Tree를 이용하는 것이 유리하다.

### 2. B+ Tree


B+ Tree는 B-Tree를 개량한 Tree이다. B-tree처럼 모든 Leaf Node는 동일한 Depth를 갖는다. B-Tree와의 가장 큰 차이점은 Inner Node에는 Key만 저장이 되고 Leaf Node에 Key와 Data를 함께 저장한다는 점이다. Leaf Node에만 Data가 저장되기 때문에 Leaf Node간의 Pointer를 연결하여 B-Tree에 비하여 쉬운 순회가 가능하다. [그림 2]는 4 Order B+ Tree를 나타내고 있다. Inner Node는 최대 2개의 Key를 갖을 수 있고 Leaf Node는 최대 3개의 Key/Value를 갖을 수 있다.

B+ Tree의 Inner Node는 Data가 없기 때문에 B-Tree의 Inner Node에 비하여 용량작다. 하나의 Disk Block에 더 많은 Inner Node를 배치 할 수 있게 되어, Key 탐색시 B-Tree에 비하여 상대적으로 적은 Disk Block만 읽어도 된다. 이러한 이점 때문에 B+ Tree는 Key 탐색시 B-Tree보다 좀더 나은 성능을 보여준다.
