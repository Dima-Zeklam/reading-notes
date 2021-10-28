# Trees
* Data structures are used to store and organize data.

* Trees are a collection of nodes, and they are linked with edges (pointers), representing the hierarchical connections between the nodes. 
* Trees are non-linear data structures.

#### Components of a Tree

1. A **node:** contains data of any type, but all the nodes must be of the same data type.
2. **Root:** The root of a tree is a node that has no incoming link (no parent node) or a starting point of your tree.

3. **Children:** The child of a tree is a node with one incoming link from a node above it (i.e. a parent node). If two children nodes share the same parent, they are called siblings.

4. **Parent:** The parent node has an outgoing link connecting it to one or more child nodes.

5. **Leaf:** A leaf has a parent node but has no outgoing link to a child node. or it's an endpoint of your tree.

6. **Subtree:** A subtree is a smaller tree held within a larger tree. The root of that tree can be any node from the bigger tree.


7. **Height:** The height of a node is the number of edges in the longest path from a node to a leaf node, or you can said how many steps there are between your node and the tree’s endpoint. The height of a tree is the height of its root node.
8. **K** - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
9. **Left** - A reference to one child node, in a binary tree
10. **Right** - A reference to the other child node, in a binary tree
11. **Degree:** The degree of a node refers to the number of sub-trees.

### Traversals
Traversing a tree allows us to search for a node, print out the contents of a tree.
#### Categories of traversals when it comes to trees:
1. Depth First, **Depth:** node is the number of edges between that node and the root. Think of this as how many steps there are between your node and the tree’s starting point.

**Here are three methods for depth first traversal:**

* Pre-order: root >> left >> right

```
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
```
* In-order: left >> root >> right
```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```
* Post-order: left >> right >> root
```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value
```

2. Breadth First
breadth first traversal uses a queue (instead of the call stack via recursion) to traverse the width/breadth of the tree.
Example:
```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```
### Binary Tree Vs K-ary Trees

#### Binary Tree
![Binary Tree](https://res.cloudinary.com/practicaldev/image/fetch/s--od-naD9n--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_880/https://miro.medium.com/max/975/1%2APWJiwTxRdQy8A_Y0hAv5Eg.png)

**Binary Tree** is a tree data structure in which each node has at most two children,Since each element in a binary tree can have only 2 children,the left and right child.  

#### Big O
* Searching: searching in binary tree has worst case complexity of O(n).

* Insertion: insertion in binary tree has worst case complexity of O(n).
* Deletion: deletion in binary tree has worst case complexity of O(n).


### K-ary Trees
The K-ary tree is a rooted tree, where each node can hold at most k number of children.

![K-ary Trees](https://i.stack.imgur.com/qUwlh.png)

Example:
```
ALGORITHM breadthFirst(root)
// INPUT  <-- root node
// OUTPUT <-- front node of queue to console

  Queue breadth <-- new Queue()
  breadth.enqueue(root)

  while breadth.peek()
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    if front.left is not NULL
      breadth.enqueue(front.left)

    if front.right is not NULL
      breadth.enqueue(front.right)
```
#### Big O
* The Big O time complexity for inserting a new node is O(n). 

* Searching for a specific node will also be O(n). 
* In the worst case we will have to look at n items, hence the O(n) complexity.

