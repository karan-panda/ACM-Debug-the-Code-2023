##  Square Border Pattern

You are asked to write a C++ program to print the following square border pattern of letters:

CORRECT OUTPUT 
```
A A A A A
A       A
A       A
A       A
A A A A A

```

### BUG CODE
```cpp
#include <iostream>
using namespace std;
int main() {
	int n = 5;
	char ch = 'A';
	for (int i = 0; i <= n; i++) {
    	for (int j = 0; j <= n; j++) { 
        	if (i == 1 || i == n && j == 1 || j == n) { 
                cout << ch-1<<" ";
        	} else {
                cout << endl;
        	}
    	}
    	ch++;
    	cout << endl;
	}
	return 0;
}
```
