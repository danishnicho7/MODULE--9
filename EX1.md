# Ex.No:1  
# Ex.Name: Search Module of the B+ Tree  

## Date:09/10/2025

## Aim:  
To write a C++ program to implement the **Search Module of a B+ Tree** and verify whether a given key is present in the tree.  

## Algorithm:  
1. Start the program.  
2. Construct a B+ Tree from the given set of keys.  
3. Insert keys level by level according to the rules of the B+ Tree.  
4. Display the B+ Tree level-wise after construction.  
5. Read the search key.  
6. Traverse the tree:  
   - Compare the search key with the keys in the current node.  
   - If found, return success.  
   - If not found, move to the appropriate child node.  
   - Continue until the leaf node is reached.  
7. If the key exists, display **“Found”** else display **“Not Found”**.  
8. Stop the program.  

## Program:
```cpp
void BPTree::search(int x)
{
    if (root == NULL)
    {
    cout << "Tree is empty\n";
    }
    else
    {
        Node *cursor = root;
        while (cursor->IS_LEAF == false) 
        {
            for (int i = 0; i < cursor->size; i++)
            {
                if (x < cursor->key[i])
                {
                    cursor = cursor->ptr[i];
                    break;
                }
                if (i == cursor->size - 1) 
                {
                    cursor = cursor->ptr[i + 1];
                    break;
                }
            }
        }
        for (int i = 0; i < cursor->size; i++)
        {
            if (cursor->key[i] == x)
            {
                cout << "Found\n";
                return;
            }
         }
        cout << "Not found\n";
    }
}
```

## Output:
<img width="870" height="791" alt="image" src="https://github.com/user-attachments/assets/c5ecbade-64d3-48fe-ad5c-31721aae3c76" />

## Result:
```
Input:
5
1 2 3 45 20
20

Output:
3
1 2
3 20 45
Found
```
