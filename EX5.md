# Ex.No:5  
# Ex.Name: Right rotate module of the red black tree

## Date:09/10/25

## Aim:  
To Write the Right rotate module of the red black tree in CPP.

## Algorithm:  
1. Start the program.    
2. In the `main()` function:  
   - Create an object of `Temperature`.  
   - Call the methods to read input, perform conversion, and display results.  
3. Stop the program.  

## Program:
```cpp
void rightrotate(node* temp)
{
    node* left = temp->l;
    temp->l = left->r;
    
    if (temp->l)
        temp->l->p = temp;
        
    left->p = temp->p;
    
    if (!temp->p)
        root = left;
    else if (temp == temp->p->l)
        temp->p->l = left;
    else
        temp->p->r = left;
        
    left->r = temp;
    temp->p = left;
}
```

 ## Output:
<img width="1059" height="840" alt="image" src="https://github.com/user-attachments/assets/42f73450-3da8-4f07-b6bc-7500c64b0d9e" />

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
