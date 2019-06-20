# Data Structure
- [Linear](#linear)
  - [Array](#array)
  - [LinkedList](#linkedlist)
  - [Stack](#stack)
  - [Queue](#queue)
- [Non Linear](#non-linear)
  - [Tree](#tree)
    - [Binary Tree](#binary-tree)
    - [Binary Search Tree](#binary-search-tree)
    - [Binary Heap](#binary-heap)
    - [Red Black Tree](#red-black-tree)
  - [Graph](#graph)
    - [Minimum Spanning Tree](#minimum-spanning-tree)
    - [Kruskal Algorithm](#kruskal-algorithm)
    - [Prim Algorithm](#prim-algorithm)
    - [Floyd Warshall Algorithm](#floyd-warshall-algorithm)

## Linear
자료를 구성하는 데이터를 순차적으로 나열시킨 형태

### Array
- 특정 자료형들이 메모리 공간상에서 **연속적**으로 이루어져 있는 형태
- 데이터를 메모리상에 연속적으로 나열해 두었기 때문에 **데이터의 접근에 있어서 O(1)의 시간복잡도**를 따른다.
- 데이터의 삽입/삭제 시 O(n^2)의 시간복잡도를 따르게 되므로 삽입/삭제 등의 연산이 빈번할 경우 배열을 사용하는 것은 비효율적이다.

### LinkedList
- 여러개의 노드들이 연결된 형태
- 메모리 공간상에서 각 노드들이 연속적으로 이루어지지 않고 **흩어져** 있으며, 각각의 노드가 자신의 다음 노드의 위치를 알고 있는 형태이다.
- 데이터의 접근에 있어서 O(N)의 시간복잡도를 따른다.
-  데이터의 삽입/삭제 시 O(1)의 시간복잡도를 따르게 되므로 **삽입/삭제 등의 연산이 빈번할 경우 연결리스트를 사용하는 것이 효율적**이다.


### Stack
- LIFO(Last In First Out), 나중에 들어간 원소가 먼저 나온다.

###  Queue
- FIFO(First In First Out), 먼저 들어간 원소가 먼저 나온다.

#### Check Point
- [Stack 두 개로 Queue 구현하기](https://github.com/BinSin/Interview_Question/tree/master/ImportantCoding/Interview/src/DataStructure/Point1)
- [Stack 으로 괄호 유효성 체크하기](https://github.com/BinSin/Interview_Question/tree/master/ImportantCoding/Interview/src/DataStructure/Point2)

## Non Linear
하나의 자료 뒤에 여러개의 자료가 존재할 수 있는 형태

### Tree
- 트리는 계층적 구조이다.
- Node : 트리를 구성하고 있는 각각의 요소
- Edge(간선) : 트리를 구성하기 위해 노드와 노드를 연결하는 선
- Root Node : 트리 구조의 최상위 노드
- Terminal Node(Leaf Node, 단말 노드) : 자식 노드가 없는 노드
- Internal Node(비단말 노드) : 단말 노드를 제외한 모든 노드

#### Binary Tree
- 루트 노드를 중심으로 두 개의 서브 트리로 나뉘어진 트리
- Level : 각 층별을 나태내며 0 부터 시작한다.
- Height : 최고 레벨
- Full Binary Tree(포화 이진 트리) : 모든 레벨이 꽉 찬 이진 트리
- Complete Binary Tree(완전 이진 트리) : 루트 노드를 시작으로 왼쪽에서 부터 오른쪽으로 빠지지 않고 채워져 있는 이진 트리

#### Binary Search Tree
- 효율적인 탐색을 위해 정해진 규칙으로 데이터를 저장한 이진 트리이다.
- 규칙
  1. 이진 탐색 트리의 노드에 저장된 키는 유일해야 한다.
  2. 루트 노드의 키가 왼쪽 서브 트리를 구성하는 어떠한 노드의 키보다 크다.
  3. 루트 노드의 키가 오른쪽 서브 트리를 구성하는 어떠한 노드의 키보다 작다.
  4. 왼쪽과 오른쪽 서브트리는 모두 이진 탐색 트리이다.
- 이진 탐색 트리의 **탐색 연산은 O(log n)**의 시간 복잡도를 갖는다.
- 만약 한쪽으로만 쏠리는 **편향 트리일 경우 O(n)**의 시간 복잡도를 갖게 된다.

#### Binary Heap
- Tree의 형식으로 **배열에 기반한 완전 이진 트리**이다.
- 종류
  1. Max Heap : 부모 노드의 값이 최대값이 되는 BST
  2. Min Heap : 부모 노드의 값이 최소값이 되는 BST

#### Red Black Tree
- BST를 기반으로 하는 트리 형식으로 편향 트리가 되는 것을 방지하기 위해 노드에 색깔을 주어 편향을 막은 트리
- Depth가 최소가 되도록 해주기 때문에 탐색, 삽입, 삭제 시 O(log n)의 시간 복잡도를 갖게 된다.
- 규칙
  1. 각 노드는 red, black 중 하나의 색깔을 갖는다.
  2. 루트 노드의 색깔은 black 이다.
  3. 모든 리프 노드들의 색깔은 black 이다.
  4. red 노드의 자식들의 색깔은 모두 black 이다.
  5. 루트 노드에서 임의의 리프 노드에 이르는 경로에서 만나는 블랙 노드의 수는 모두 같다.

### Graph


#### Minimum Spanning Tree


#### Kruskal Algorithm


#### Prim Algorithm


#### Floyd Warshall Algorithm
