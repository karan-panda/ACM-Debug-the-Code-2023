## Check the code for syntax and logical errors and make corrections to achieve the desired output. 
The search function is intended to search for a user-entered value in a given array. If the value is found, it should return the location of the item in the array. For example, if the array is arr {1, 2, 3, 4, 5}, and the entered value is 2, the output should be "Item found at location 2." If the entered value is 6, the output should be "Item not found."
The search function takes four parameters: a[], which represents the array, start, which represents the start index of the array, last, which represents the last index of the array, and item, which represents the item to be searched for.
The initial code for the search function compiles successfully but produces incorrect results for some test cases due to logical errors. Your task is to correct the code so that it passes all the test cases and use recursive method only.

```cpp
int Search(int a[], int start, int last, int item)
{
	int mid;
	if (last >= start)
	{
    	mid = (start + last) / 2;
    	if (a[mid] == item)
    	{
        	return mid + 1;
    	}
    	else if (a[mid] < item)
    	{
        	return Search(a, start, mid + 1, item);
    	}
    	else
    	{
        	return Search(a, mid - 1, last, item);
    	}
	}
	return -1;
}
```
