# DS_Module15
# Ex3(A) Tree Representation and Traversal
## DATE:
## AIM:
To write a C function to perform post order traversal of a binary tree.

## Algorithm
1. Start
2. Define a function display_postorder() that takes a pointer to the root node of the tree.
3. Check if the current node (root_node) is not null.
4. Recursively call display_postorder() for the left child of the current node.
5. Recursively call display_postorder() for the right child of the current node.
6. After visiting both children, print the value of the current node.
7. End

## Program:
```
Program to perform post order traversal of a binary tree.
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024

```
```c

/*struct node
{
  int value;
  struct node*left_child, *right_child;
};*/

void display_postorder(struct node*root_node)
{
  if(root_node)
  {
    display_postorder(root_node->left_child);
    display_postorder(root_node->right_child);
    printf("%d\n",root_node->value);
  }
}

```

## Output:
![image](https://github.com/user-attachments/assets/24de390f-a069-4e29-baa4-bfb4e0f4d760)



## Result:
Thus, the function to perform post order traversal of a binary tree is implemented successfully
# Ex3(B) Binary Search Tree
## DATE:
## AIM:
To write a C function to insert the elements in the binary search tree

## Algorithm
1. Start
2. Check if the current node is NULL; if true, create a new node with the given key.
3. Allocate memory for the new node, set its key, and initialize its left and right children toNULL.
4. If the current node is not NULL, compare the key with the current node's key.
5. If key <= node->key, recursively insert the key into the left subtree and update the left child pointer.
6. If key > node->key, recursively insert the key into the right subtree and update the right child pointer.
7. Return the current node after the insertion.
8. End 

## Program:
```
Program to insert the elements in the binary search tree
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```
*structnode
{
  int key;
  struct node*left, *right;
};*/

struct node* insert(struct node* node, int key)
{
  if(node==NULL)
  {
    struct node*node=(struct node*)malloc(sizeof(struct node));
    node->key=key;
    node->left=NULL;
    node->right=NULL;
    return node;
  }
  else
  {
    struct node* cur;
    if(key<=node->key)
    {
      cur=insert(node->left,key);
      node->left=cur;
    }  
    else
    {
      cur=insert(node->right,key);
      node->right=cur;
    }
    returnnode;
  }
}
```
## Output:
![image](https://github.com/user-attachments/assets/13664423-3e5e-49c2-88ed-2e9c2ccc5773)



## Result:
Thus, the C function to insert the elements in the binary search tree is implemented successfully.
# Ex3(C) Expression Tree
## DATE:
## AIM:
To write a C function to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.

## Algorithm
1. Start
2. Print node data in preorder then traverse left then right
3. Traverse left in inorder then print node data then traverse right
4. Traverse left in postorder then traverse right then print node data
5. Recursive approach is used for all three traversal methods
6. Functions handle each tree node using tree->d, tree->l, tree->r
7. End

## Program:
```
Program to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```c
/*
struct n
{
  char d;
  struct n*l;
  struct n*r;
};*/

void preOrder(struct n*tree)
{
  if(tree)
  {
    printf("%c",tree->d);
    preOrder(tree->l);
    preOrder(tree->r);
  }
}
void inOrder(struct n*tree)
{
  if(tree)
  {
    inOrder(tree->l);
    printf("%c",tree->d);
    inOrder(tree->r);
  }
}
void postOrder(struct n*tree)
{
  if(tree)
  {
    postOrder(tree->l);
    postOrder(tree->r);
    printf("%c",tree->d);
  }
}
```

## Output:
![image](https://github.com/user-attachments/assets/3a05fc77-0770-47e2-8a8d-77401e7d31eb)



## Result:
Thus, the C program to display the Expression Tree in the format of In-order ,Pre-order and Post-order traversal.
# Ex3(D) Heap Tree
## DATE:
## AIM:
To write a C function to delete an element in a Heap Tree.

## Algorithm
1. Start 
2. Find the index of the element num in the array. 
3. Swap the element to be deleted with the last element in the array. 
4. Decrease the array size (size) by 1. 
5. Start heapifying from the last non-leaf node (index size/2 - 1). 
6. Call heapify() to restore the heap property for each node. 
7. End 
## Program:
```
Program to delete an element in a Heap Tree
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024 
```
```
void deleteRoot(int array[], int num) 
{ 
  int i; 
  for(i=0;i<size;i++) 
  { 
    if(num==array[i]) 
    { 
      break; 
    } 
  } 
  swap(&array[i],&array[size-1]); 
  size-=1; 
  for(i=size/2-1;i>=0;i--) 
  { 
    heapify(array,size,i); 
  } 
}
```
## Output:
![image](https://github.com/user-attachments/assets/9d5ef6da-1e3d-4259-8ff3-ee63be1fa51b)




## Result:
Thus, the function to delete an element in a Heap Tree is implemented successfully.
# Ex3(E) Largest Element in BST
## DATE:
## AIM:
To Write a c program to find the largest value in a Binary Search Tree.

## Algorithm
1. Initialize a pointer to the root of the BST.
2. Move to the right child in a loop while it exists.
3. Stop when the right child is NULL.
4. Return the current node’s value as the largest.


## Program:
```
Program to find and display the priority of the operator in the given Postfix expression
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```

#include <stdio.h>
#include <stdlib.h>

struct node
{
  int info;
  struct node *left, *right;
};

struct node *createnode(int key)
{
  struct node*newnode = (struct node*)malloc(sizeof(struct node));
  newnode->info = key;
  newnode->left = NULL;
  newnode->right = NULL;
  return(newnode);
}

void inorder(struct node *root)
{
if(root != NULL)
{
inorder(root->left); printf(" %d ",root->info); inorder(root->right);
}
}
void largest(struct node *root)
{
  while (root != NULL && root->right != NULL)
  {
    root = root->right;
  }
  printf("\nLargest value is %d", root->info);
}

int main()
{
  /* Creating first Tree. */
  struct node *newnode = createnode(25);
  newnode->left = createnode(17);
  newnode->right = createnode(35);
  newnode->left->left = createnode(13);
  newnode->left->right = createnode(19);
  newnode->right->left = createnode(27);
  newnode->right->right =createnode(55);

  printf("Inorder traversal of tree 1 :"); inorder(newnode); largest(newnode);
  return 0;
}

```
## Output:

![image](https://github.com/user-attachments/assets/83f9f7aa-3bca-4f28-b3ec-768b4e89838c)




## Result:
Thus, the C program to find the largest value in a Binary Search Tree is implemented successfully.
