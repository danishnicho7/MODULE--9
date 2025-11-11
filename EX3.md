# Ex.No:3  
# Ex.Name: B-Tree – setValue Module  

## Date:09/10/25

## Aim:  
To write a C++ program to implement the **setValue Module of a B-Tree**, which inserts values and displays them in sorted order.  

## Algorithm:  
1. Start the program.  
2. Define a B-Tree node structure containing keys and child pointers.  
3. Insert keys into the B-Tree one by one:  
   - If the node has space, insert the key in sorted order.  
   - If the node overflows, split the node and propagate the middle key upward.  
4. Continue until all keys are inserted.  
5. Perform **inorder traversal** of the B-Tree to display all keys in ascending order.  
6. Stop the program.  

## Program:
```cpp
int setValue(int val, int *pval, BTreeNode *node, BTreeNode **child)
{
    int pos;
    if (!node)
    {
        *pval = val;
        *child = NULL;
        return 1;
    }

    if (val < node->val[1]) 
    {
        pos = 0;
    } 
    else 
    {
        for (pos = node->count;(val < node->val[pos] && pos > 1); pos--);
        if (val == node->val[pos]) 
        {
            cout<<"Duplicates are not permitted\n";
            return 0;
        }
    }
    if (setValue(val, pval, node->link[pos], child))
    {
        if (node->count < MAX) 
        {
            insertKey(*pval, pos, node, *child);
        }
        else
        {
            splitNode(*pval, pval, pos, node, *child, child);
            return 1;
        }
    }
    return 0;
}
```

## Output:
<img width="867" height="452" alt="image" src="https://github.com/user-attachments/assets/c5e54dc3-80be-41c8-b078-28fbd0f59162" />

## Result:
```
Input:
10
8 9 7 11 15 16 17 18 20 23

Output:
7 8 9 11 15 16 17 18 20 23
```
