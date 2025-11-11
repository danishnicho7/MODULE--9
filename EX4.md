# Ex.No:4  
# Ex.Name: Right Rotate Module of a Splay Tree  

## Date:09/10/2025

## Aim:  
To write a C++ program to perform a **Right Rotation in a Splay Tree** and display the tree before and after the rotation using preorder traversal.  

## Algorithm:  
1. Start the program.  
2. Define a node structure with `data`, `left`, and `right` pointers.  
3. Insert elements into the tree following **Binary Search Tree (BST)** insertion rules.  
4. Implement a **right rotate function** that:  
   - Makes the left child of a node the new root.  
   - Adjusts pointers so that the original root becomes the right child of the new root.  
5. Perform a **splay operation** on the given key using right rotation.  
6. Display the tree traversal before and after the rotation.  
7. Stop the program.
   
## Program:
```cpp
node *rightRotate(struct node *x)
{
    node *y = x->left;
    x->left = y->right;
    y->right = x;
    return y;
}
```

## Output:
<img width="864" height="672" alt="image" src="https://github.com/user-attachments/assets/3525d27f-4acd-4a15-ba4e-60e3f2ee21b5" />

## Result:
```
Input:
5
10 20 30 5 6
30

Output:
Preorder traversal of the BST is
10 5 6 20 30

Preorder traversal of the modified Splay tree is
30 20 10 5 6
```
