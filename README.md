# cpp
discussion about pointers and some code
## Q1
```cpp
#include <iostream>
using namespace std;

int a=5;

int main() {
    int b=10;
    int *c=new int(15);
    
    cout <<"global varable address:"<<&a<<endl;
    cout <<"local variable address:"<<&b<<endl;
    cout <<"heap variable address:"<<c<<endl;
    
    delete c;
    return 0;
}
```
- Output
- global varable address:0x404040
  local variable address:0x7ffc4ecc4344
  heap variable address:0x100262b0
## Q2
```cpp
#include <iostream>
using namespace std;

int square(int x)
{
    return x * x;
}

int main()
{
    int n = 5;

    // Normal call
    cout << "Normal call: " << square(n) << endl;

    // Function pointer
    int (*fp)(int) = square;
    cout << "Function pointer call: " << fp(n) << endl;

    return 0;
}
```
- Output
- Normal call: 25
  Function pointer call: 25


## Q3
```cpp
#include <iostream>
using namespace std;

int main()
{
    int x = 10;      // normal variable
    int *p = &x;     // pointer storing address of x

    cout << "Value of variable x: " << x << endl;
    cout << "Address of variable x: " << &x << endl;
    cout << "Value stored in pointer p: " << p << endl;

    return 0;
}
```
- Output
- Value of variable x: 10
  Address of variable x: 0x7ffc9488e674
  Value stored in pointer p: 0x7ffc9488e674
## Q4
```cpp
#include <iostream>
using namespace std;

int main()
{
    int a = 10;      // first variable
    int *p = &a;     // pointer stores address of a
    int b;           // third variable

    // Copy value using dereferencing
    b = *p;

    cout << "Value of a: " << a << endl;
    cout << "Value copied to b: " << b << endl;

    return 0;
}
```
- Output
- Value of a: 10
  Value copied to b: 10
## Q5
```cpp
# include <iostream>
using namespace std;
int main() {
int x = 5;
int *p = &x;
*p = 10;
cout << x;
}
```
- Output
- 10
## Q6
```cpp
# include <iostream>
using namespace std;
int main() {
    int a = 1, b = 2;
    int *p = &a;
    p = &b;
    *p = 5;
    cout << a << " " << b;
}
```
- Output
- 1  5
## Q7
```cpp
# include <iostream>
using namespace std;
int main() {
    int x = 10;
    int *p = &x;
    int **pp = &p;
    **pp = 20;
    cout << x;
}
```
- Output
- 20
## Q8
```cpp
# include <iostream>
using namespace std;
int main() {
    int a[5] = {2,4,6,8,10};
    int *p = a;
    cout << *p++ << " ";
    cout << *p;
}
```
- Output
- 2   4
## Q9
```cpp
#include <iostream>
using namespace std;

// Function to swap two numbers using pointers
void swap(int *a, int *b) {
    int temp = *a;  // store value of a
    *a = *b;        // assign value of b to a
    *b = temp;      // assign stored value to b
}

int main() {
    int x = 10, y = 20;

    cout << "Before swapping: x = " << x << ", y = " << y << endl;

    // Call swap function with addresses of x and y
    swap(&x, &y);

    cout << "After swapping: x = " << x << ", y = " << y << endl;

    return 0;
}
```
- Output
- Before swapping: x = 10, y = 20
  After swapping: x = 20, y = 10
## Q10
```cpp
#include <iostream>
using namespace std;

int main() {
    // Create dynamic integer
    int* ptr = new int;

    // Assign value through pointer
    *ptr = 10;

    // Display value
    cout << "Value of dynamic integer: " << *ptr << endl;

    // Modify value through pointer
    *ptr = 25;
    cout << "Modified value: " << *ptr << endl;

    // Delete dynamic memory
    delete ptr;

    // Set pointer to NULL (good practice)
    ptr = nullptr;

    return 0;
}
```
- Output
- Value of dynamic integer: 10
- Modified value: 25
## Q11
```cpp
#include <iostream>
using namespace std;
int main() {       
        int a[] = {1,2,3,4,5};
        int *p = a;
        cout << *p++ << " ";
        cout << (*p)++ << " ";
        cout << ++*p << " ";
        cout << *p << "\n";
        for(int i=0;i<5;i++) cout << a[i] << " ";
}
```
- output
- 1 2 4 4
- 1 4 3 4 5 
## Q12
```cpp
#include <iostream>
using namespace std;
int main() {       
       int x=10;
       int *p=&x;
       cout << (*p)++ << " " << x << "\n";
       cout << ++(*p) << " " << x << "\n";
       cout << *p++ << " " << x << "\n";
}
```
- Output
- 10 11
- 12 12
- 12 12
## Q13
```cpp
#include <iostream>
using namespace std;
int main() {       
       int a[] = {10,20,30,40,50};
       int *p = a + 1;
       cout << *(p+2) << " " << *(p-1) << "\n";
}
```
- Output
- 40 10
## Q14
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    
    cout << "Enter number of elements: ";
    cin >> n;

    int arr[n];

    cout << "Enter " << n << " elements:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    cout << "Array elements are:\n";
    for (int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```
- output
- Enter number of elements: 5
- Enter 5 elements:
- 1
- 2
- 3
- 4
- 5
- Array elements are:
- 1 2 3 4 5 
## Q15
```cpp
#include <iostream>
using namespace std;

int main() {
    int n, sum = 0;

    cout << "Enter number of elements: ";
    cin >> n;

    int arr[n];

    cout << "Enter array elements:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
        sum += arr[i];
    }

    cout << "Sum of array elements = " << sum << endl;

    return 0;
}
```
-Output
-Enter number of elements: 5
-Enter array elements:
-2
-3
-5
-6
-7
-Sum of array elements = 23
## Q16
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;

    cout << "Enter number of elements: ";
    cin >> n;

    int arr1[n], arr2[n];

    cout << "Enter elements of first array:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr1[i];
    }

    // Copying array
    for (int i = 0; i < n; i++) {
        arr2[i] = arr1[i];
    }

    cout << "Elements of second array:\n";
    for (int i = 0; i < n; i++) {
        cout << arr2[i] << " ";
    }

    return 0;
}
```
-Output
-Enter number of elements: 5
-Enter elements of first array:
-2
-3
-4
-6
-7
-Elements of second array:
-2 3 4 6 7 
## Q17
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;

    cout << "Enter number of elements: ";
    cin >> n;

    int arr[n];

    cout << "Enter array elements:\n";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    cout << "Elements at even index positions:\n";
    for (int i = 0; i < n; i++) {
        if (i % 2 == 0) {
            cout << arr[i] << " ";
        }
    }

    return 0;
}
```
-Output
-Enter number of elements: 5
-Enter array elements:
-3
-5
-7
-4
-7
-Elements at even index positions:
-3 7 7 
## Q18
```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;

    cout << "Enter number of rows and columns: ";
    cin >> rows >> cols;

    int mat[rows][cols];

    cout << "Enter matrix elements:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> mat[i][j];
        }
    }

    cout << "Matrix is:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << mat[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```
-Output
-Enter number of rows and columns: 3 3
-Enter matrix elements:
-2 27 3 3 5 7 7 8 8 
-Matrix is:
-2 27 3 
-3 5 7 
-7 8 8
## Q19
```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;

    cout << "Enter number of rows and columns: ";
    cin >> rows >> cols;

    int mat[rows][cols];

    cout << "Enter matrix elements:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> mat[i][j];
        }
    }

    cout << "Matrix elements in row-wise order:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << mat[i][j] << " ";
        }
    }

    return 0;
}
```
-Output
-Enter number of rows and columns: 3 3
-Enter matrix elements:
-1 3 4 6 75 76 5 4 67
-Matrix elements in row-wise order:
-1 3 4 6 75 76 5 4 67 
## Q20
```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;

    cout << "Enter number of rows and columns: ";
    cin >> rows >> cols;

    int mat[rows][cols];

    cout << "Enter matrix elements:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> mat[i][j];
        }
    }

    cout << "Matrix elements in column-wise order:\n";
    for (int j = 0; j < cols; j++) {
        for (int i = 0; i < rows; i++) {
            cout << mat[i][j] << " ";
        }
    }

    return 0;
}
```
-Output
-Enter number of rows and columns: 3 3
-Enter matrix elements:
-2 3 5 6 3 5 3 5 4
-Matrix elements in column-wise order:
-2 6 3 3 3 5 5 5 4 


