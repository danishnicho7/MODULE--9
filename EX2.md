# Ex.No:2  
# Ex.Name: Red-Black Tree Construction Module  

## Date:09/10/25

## Aim:  
To write a C++ program to construct a **Red-Black Tree (RBT)** and display its inorder traversal along with node colors.  

## Algorithm:  
1. Start the program.  
2. Define a Red-Black Tree node structure with:  
   - Data (key value)  
   - Color (0 = Black, 1 = Red)  
   - Left and Right child pointers, Parent pointer.  
3. Insert nodes one by one into the tree following the **Binary Search Tree (BST)** property.  
4. After each insertion, perform **fix-up operations** to maintain Red-Black Tree properties:  
   - Root must always be black.  
   - No two red nodes can appear consecutively.  
   - Every path from root to leaf must contain the same number of black nodes.  
5. Perform rotations (Left Rotate, Right Rotate) and recoloring when violations occur.  
6. Once all elements are inserted, perform **Inorder Traversal** to display:  
   - Node data  
   - Node color (0 = Black, 1 = Red).  
7. Stop the program.  

## Program:
```cpp
node* bst(node* trav, node* temp)
{
    if (trav == NULL)
        return temp;
    if (temp->d < trav->d)
    {
        trav->l = bst(trav->l, temp);
        trav->l->p = trav;
    }
    else if (temp->d > trav->d)
    {
        trav->r = bst(trav->r, temp);
        trav->r->p = trav;
    }
    return trav;
}
```

##  Output:
<img width="1348" height="861" alt="image" src="https://github.com/user-attachments/assets/5a3e904a-bf14-4833-8756-599584bb272d" />

## Result:
```
Input:
5
50 10 20 5 65

Output:
Inorder Traversal of Created Tree
Data=5 Color=1
Data=10 Color=0
Data=20 Color=0
Data=50 Color=0
Data=65 Color=1
```
