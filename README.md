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
- Output
- Enter number of elements: 5
- Enter array elements:
- 2
- 3 
- 5
- 6
- 7
- Sum of array elements = 23
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
- Output
- Enter number of elements: 5
- Enter elements of first array:
- 2
- 3
- 4
- 6
- 7
- Elements of second array:
- 2 3 4 6 7 
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
- Output
- Enter number of elements: 5
- Enter array elements:
- 3
- 5
- 7
- 4
- 7
- Elements at even index positions:
- 3 7 7 
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
- Output
- Enter number of rows and columns: 3 3
- Enter matrix elements:
- 2 27 3 3 5 7 7 8 8 
- Matrix is:
- 2 27 3 
- 3 5 7 
- 7 8 8
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
- Output
- Enter number of rows and columns: 3 3
- Enter matrix elements:
- 1 3 4 6 75 76 5 4 67
- Matrix elements in row-wise order:
- 1 3 4 6 75 76 5 4 67 
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
- Output
- Enter number of rows and columns: 3 3
- Enter matrix elements:
- 2 3 5 6 3 5 3 5 4
- Matrix elements in column-wise order:
- 2 6 3 3 3 5 5 5 4 
## Q21
```cpp
#include <iostream>
using namespace std;

struct Student {
    int roll;
    string name;
    float marks;
};

int main() {
    Student s[5];

    // Input details
    for (int i = 0; i < 5; i++) {
        cout << "\nEnter details of student " << i + 1 << endl;

        cout << "Roll number: ";
        cin >> s[i].roll;

        cout << "Name: ";
        cin >> s[i].name;

        cout << "Marks: ";
        cin >> s[i].marks;
    }

    // Display students with marks > 75
    cout << "\nStudents scoring more than 75 marks:\n";
    for (int i = 0; i < 5; i++) {
        if (s[i].marks > 75) {
            cout << "Roll: " << s[i].roll
                 << ", Name: " << s[i].name
                 << ", Marks: " << s[i].marks << endl;
        }
    }

    return 0;
}
```
```
Output
Enter details of student 1
Roll number: 1
Name: rishav
Marks: 80

Enter details of student 2
Roll number: 2
Name: raunak
Marks: 65

Enter details of student 3
Roll number: 3
Name: sahil
Marks: 70

Enter details of student 4
Roll number: 4
Name: rashmika
Marks: 80

Enter details of student 5
Roll number: 5
Name: tapin
Marks: 59

Students scoring more than 75 marks:
Roll: 1, Name: rishav, Marks: 80
Roll: 4, Name: rashmika, Marks: 80
```
## Q22
```cpp
#include <iostream>
using namespace std;

struct Employee {
    int empId;
    string name;
    float basicSalary;
};

int main() {
    Employee e;
    float hra, da, grossSalary;

    cout << "Enter Employee ID: ";
    cin >> e.empId;

    cout << "Enter Name: ";
    cin >> e.name;

    cout << "Enter Basic Salary: ";
    cin >> e.basicSalary;

    // Salary calculation
    hra = 0.20 * e.basicSalary;
    da  = 0.10 * e.basicSalary;
    grossSalary = e.basicSalary + hra + da;

    // Output
    cout << "\nEmployee Details\n";
    cout << "ID: " << e.empId << endl;
    cout << "Name: " << e.name << endl;
    cout << "Gross Salary: " << grossSalary << endl;

    return 0;
}
```
```
Output
Enter Employee ID: 1
Enter Name: rishav
Enter Basic Salary: 20000

Employee Details
ID: 1
Name: rishav
Gross Salary: 26000
```
## Q23
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {10, 20, 30, 40};
    int *p = arr;

    cout << *p << endl;        // value at arr[0]
    cout << *(p + 1) << endl;  // value at arr[1]
    cout << *(p + 3) << endl;  // value at arr[3]

    return 0;
}
```
```
Output
10
20
40
explanation 
The * operator is used to access the value stored at the address the pointer is pointing to.
*p
p → address of arr[0]
*p → value at arr[0]
Value = 10
*(p + 1)
p + 1 moves the pointer to the next integer location
That is arr[1]
Value = 20
*(p + 3)
p + 3 moves the pointer to the 4th element
That is arr[3]
Value = 40
```
## Q24
```cpp
#include <iostream>      
using namespace std;

int main() {
    int arr[] = {5, 10, 15, 20};

    // The array name 'arr' acts like a pointer to the first element
    // arr == &arr[0]

    // Create a pointer 'p' and make it point to arr + 2
    // arr + 2 means move 2 elements forward from index 0
    // So p now points to arr[2], which stores 15
    int *p = arr + 2;

    // Dereference p using *p
    // This prints the value stored at the location p is pointing to
    // Since p points to arr[2], it prints 15
    cout << *p << endl;

    // Move the pointer one position backward using (p - 1)
    // If p was at arr[2], now (p - 1) points to arr[1]
    // Dereferencing gives the value at arr[1], which is 10
    cout << *(p - 1) << endl;

    return 0;
}

```
```
Output
15
10
```
## Q25
```cpp
#include <iostream>      
using namespace std;

int main() {
   int arr[5] = {1, 2, 3, 4, 5};

   // The array name 'arr' acts like a pointer to the first element
   // arr == &arr[0]

   // Loop runs from i = 0 to i = 4
   for(int i = 0; i < 5; i++)

       // (arr + i) moves i positions forward from arr[0]
       // *(arr + i) dereferences that address to get the value
       // So this prints arr[i] using pointer arithmetic
       // Example:
       // i = 0 → *(arr + 0) = 1
       // i = 1 → *(arr + 1) = 2
       // i = 2 → *(arr + 2) = 3
       // i = 3 → *(arr + 3) = 4
       // i = 4 → *(arr + 4) = 5
       cout << *(arr + i) << " ";

   return 0;  
}
```
```
Output
1 2 3 4 5
```
## Q26
```cpp
#include <iostream>     
using namespace std;

int main() {
    int arr[] = {2, 4, 6, 8};

    // The array name 'arr' acts like a pointer to the first element
    // arr == &arr[0]

    // Create a pointer p and make it point to the first element
    // So p now points to arr[0] (value 2)
    int *p = arr;

    // Increment the pointer
    // p++ moves the pointer one element forward (not one byte)
    // So now p points to arr[1] (value 4)
    p++;

    // Dereference p to get the value it is pointing to
    // Since p now points to arr[1], this prints 4
    cout << *p << endl;

    return 0;
}
```
```
Output
4
```
## Q27
```cpp
#include <iostream>     
using namespace std;

int main() {
    int arr[] = {7, 14, 21};

    // arr[1] means *(arr + 1)
    // It moves one position forward from arr[0]
    // So this accesses arr[1], which is 14
    cout << arr[1] << endl;

    // 1[arr] looks unusual, but it works the same as arr[1]
    // Because array indexing is defined as:
    // a[b] == *(a + b)
    // So 1[arr] == *(1 + arr) == *(arr + 1)
    // Therefore, this also prints 14
    cout << 1[arr] << endl;

    return 0;  
}
```
```
Output
14
14
```
## Q28
```cpp
#include <iostream>     
using namespace std;

int main() {
    int arr[] = {10, 20, 30};

    // The array name 'arr' acts like a pointer to the first element
    // arr == &arr[0]

    // Pointer p is initialized to point to the first element
    // So p points to arr[0] (value 10)
    int *p = arr;

    // *p gives the value at arr[0], which is 10
    // Then + 1 is added to that VALUE (not the pointer)
    // So this prints 10 + 1 = 11
    cout << *p + 1 << endl;

    // (p + 1) moves the pointer one element forward
    // Now it points to arr[1]
    // *(p + 1) dereferences it, giving the value at arr[1], which is 20
    cout << *(p + 1) << endl;

    return 0;  
}
```
```
Output
11
20
```
## Q29
```cpp
#include <iostream>      
using namespace std;

int main() {
    int arr[] = {3, 6, 9, 12};

    // The array name 'arr' acts like a pointer to the first element
    // arr == &arr[0]

    // Pointer p is initialized to point to the first element
    // So p points to arr[0] (value 3)
    int *p = arr;

    // Loop continues as long as p is less than or equal to
    // the address of arr[3] (the last element)
    while(p <= &arr[3]) {

        // *p dereferences the pointer and prints the value
        // First iteration: prints 3
        // Then 6, 9, and finally 12
        cout << *p << " ";

        // Move the pointer one element forward
        // p++ moves to the next array element
        p++;
    }

    return 0; 
}
```
```
Output
3 6 9 12
```
## Q30
```cpp
#include <iostream>      
using namespace std;

int main() {
    int arr[] = {1, 2, 3};

    // Pointer p points to the first element of the array
    // p = arr is same as p = &arr[0]
    int *p = arr;

    // Loop runs 3 times (i = 0, 1, 2)
    for(int i = 0; i < 3; i++)

        // *(p++) does two things:
        // 1) Returns the value at current pointer position (*p)
        // 2) Then increments the pointer to the next element (p++)
        //
        // So it prints arr[0], then arr[1], then arr[2]
        cout << *(p++) << " ";

    return 0; 
}
```
```
Output
1 2 3
```
## Q31
```cpp
#include <iostream>   
using namespace std;

int main() {
    int arr[] = {10, 20, 30};

    // Pointer p points to the first element of the array
    // p = arr is same as p = &arr[0]
    int *p = arr;

    // Printing p will display the address of arr[0]
    // Example output (address will vary each run):
    // 0x7ffd9c1e1a10
    cout << p << endl;

    // p + 1 moves the pointer one element forward
    // This points to arr[1]
    // It prints the address of arr[1]
    // Since int size is usually 4 bytes, the address will increase by 4
    cout << p + 1 << endl;

    return 0;  
}
```
```
Output
0x7ffc44ab332c
0x7ffc44ab3330
```
## Q32
```cpp
#include <iostream>     
using namespace std;

int main() {
    char arr[] = {'A', 'B', 'C', '\0'};

    // Pointer p points to the first element of the array
    char *p = arr;

    // Now cout treats p as a C-string and prints characters until '\0'
    // Output: ABC
    cout << p << endl;

    // p + 1 points to the second element (arr[1])
    // This prints from 'B' onwards until '\0'
    // Output: BC
    cout << p + 1 << endl;

    return 0;  // End of program
}
```
```
Output
ABC
BC
```
## Q33
```cpp
#include <iostream>     
using namespace std;

struct Data {
    int x;
    int y;
};

int main() {
    Data arr[] = {{1,2}, {3,4}, {5,6}};

    // Pointer p points to the first element of the array
    // p = arr is same as p = &arr[0]
    Data *p = arr;

    // p->x means (p->x) = arr[0].x = 1
    cout << p->x << endl;

    // (p + 1) moves the pointer to the next element in the array
    // So (p + 1) points to arr[1]
    // (p + 1)->y = arr[1].y = 4
    cout << (p + 1)->y << endl;

    return 0;  // End of program
}
```
```
Output
1
4
```
## Q34
```cpp
#include <iostream>     
using namespace std;

struct Item {
    int price;
};

int main() {
    Item arr[] = {100, 200, 300};

    // Pointer p points to the first element of the array
    // p = arr is same as p = &arr[0]
    Item *p = arr;

    // p[2] means the 3rd element of the array (index 2)
    // p[2].price = arr[2].price = 300
    cout << p[2].price << endl;

    // (p + 1) moves pointer to the next element (index 1)
    // *(p + 1) dereferences it to get the element
    // Then .price accesses its price value
    // (*(p + 1)).price = arr[1].price = 200
    cout << (*(p + 1)).price << endl;

    return 0;  // End of program
}
```
```
Output
300
200
```
## Q35
```cpp
#include <iostream>
using namespace std;

// Define a node structure for the linked list
struct Node {
    int data;     // Data stored in the node
    Node* next;   // Pointer to the next node
};

class SinglyLinkedList {
private:
    Node* head;   // Pointer to the first node of the list

public:
    // Constructor to initialize head to nullptr (empty list)
    SinglyLinkedList() {
        head = nullptr;
    }

    // Insert node at the beginning of the list
    void insertAtBeginning(int value) {
        Node* newNode = new Node(); // Allocate memory for new node
        newNode->data = value;      // Store the value
        newNode->next = head;       // Point new node to current head
        head = newNode;             // Update head to new node
    }

    // Insert node at the end of the list
    void insertAtEnd(int value) {
        Node* newNode = new Node(); // Allocate memory for new node
        newNode->data = value;      // Store the value
        newNode->next = nullptr;    // Last node should point to nullptr

        // If list is empty, new node becomes head
        if (head == nullptr) {
            head = newNode;
            return;
        }

        // Traverse to the last node
        Node* temp = head;
        while (temp->next != nullptr) {
            temp = temp->next;
        }

        // Link the last node to the new node
        temp->next = newNode;
    }

    // Delete a node by value
    void deleteNode(int value) {
        // If list is empty
        if (head == nullptr) {
            cout << "List is empty." << endl;
            return;
        }

        // If the node to delete is the head node
        if (head->data == value) {
            Node* temp = head;      // Save the node to delete
            head = head->next;      // Move head to the next node
            delete temp;            // Free memory of deleted node
            return;
        }

        // Traverse the list to find the node to delete
        Node* current = head;
        Node* previous = nullptr;

        while (current != nullptr && current->data != value) {
            previous = current;
            current = current->next;
        }

        // If value not found in the list
        if (current == nullptr) {
            cout << "Value not found in the list." << endl;
            return;
        }

        // Remove the node from the list
        previous->next = current->next;

        // Free memory of the deleted node
        delete current;
    }

    // Display the entire list
    void display() {
        // If list is empty
        if (head == nullptr) {
            cout << "List is empty." << endl;
            return;
        }

        // Traverse and print each node's data
        Node* temp = head;
        while (temp != nullptr) {
            cout << temp->data << " ";
            temp = temp->next;
        }
        cout << endl;
    }
};

int main() {
    SinglyLinkedList list;

    // Insert elements
    list.insertAtBeginning(10);   // List: 10
    list.insertAtBeginning(20);   // List: 20 -> 10
    list.insertAtEnd(30);         // List: 20 -> 10 -> 30
    list.insertAtEnd(40);         // List: 20 -> 10 -> 30 -> 40

    // Display list
    cout << "List after insertion: ";
    list.display();

    // Delete a node
    list.deleteNode(20);          // List becomes: 10 -> 30 -> 40

    // Display list
    cout << "List after deleting 20: ";
    list.display();

    // Try deleting a value not in list
    list.deleteNode(100);

    return 0;
}
```
```
Output
List after insertion: 20 10 30 40 
List after deleting 20: 10 30 40 
Value not found in the list.
```
## Q36
```cpp
#include <iostream>
using namespace std;

int main() {
    int size;

    // Ask user for the size of the array
    cout << "Enter the size of the array: ";
    cin >> size;

    // Dynamically allocate memory for the array using new
    int *arr = new int[size];

    // Input values into the array
    cout << "Enter " << size << " values:" << endl;
    for (int i = 0; i < size; i++) {
        cin >> arr[i];
    }

    // Print the array
    cout << "Array elements are: ";
    for (int i = 0; i < size; i++) {
        cout << arr[i] << " ";
    }
    cout << endl;

    // Free the dynamically allocated memory using delete[]
    delete[] arr;

    return 0;
}
```
```
Output
Enter the size of the array: 3
Enter 3 values:
23 35 24
Array elements are: 23 35 24
```
## Q37
```cpp
#include <iostream>
using namespace std;

int main() {
    int a, b;

    // Input two numbers
    cout << "Enter two numbers: ";
    cin >> a >> b;

    // Declare pointers to both variables
    int *p1 = &a;
    int *p2 = &b;

    // Swap using a temporary variable
    int temp = *p1;  // temp = value of a
    *p1 = *p2;       // a = value of b
    *p2 = temp;      // b = temp (original value of a)

    // Print swapped values
    cout << "After swapping:" << endl;
    cout << "a = " << a << endl;
    cout << "b = " << b << endl;

    return 0;
}
```
```
Output
Enter two numbers: 24 35
After swapping:
a = 35
b = 24
```
## Q38
```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    int n;

    // Input number of strings
    cout << "Enter number of strings: ";
    cin >> n;

    // Create an array of pointers to char
    char** arr = new char*[n];

    // Input strings
    cout << "Enter " << n << " strings:" << endl;
    for (int i = 0; i < n; i++) {
        char temp[100];          // temporary buffer to read the string
        cin >> temp;

        // Allocate memory for each string based on its length
        arr[i] = new char[strlen(temp) + 1];

        // Copy string to allocated memory
        strcpy(arr[i], temp);
    }

    // Print all strings
    cout << "\nThe strings are:" << endl;
    for (int i = 0; i < n; i++) {
        cout << arr[i] << endl;
    }

    // Free memory for each string
    for (int i = 0; i < n; i++) {
        delete[] arr[i];
    }

    // Free memory for array of pointers
    delete[] arr;

    return 0;
}
```
```
Output
Enter number of strings: 3
Enter 3 strings:
rishav
panshul
nishant

The strings are:
rishav
panshul
nishant
```
## Q39
```cpp
#include <iostream>
using namespace std;

class CircularBuffer {
private:
    int *buffer;     // dynamically allocated array
    int capacity;    // maximum number of elements
    int front;       // index of front element
    int rear;        // index of last element
    int size;        // current number of elements

public:
    // Constructor
    CircularBuffer(int cap) {
        capacity = cap;
        buffer = new int[capacity];  // allocate memory
        front = 0;
        rear = -1;
        size = 0;
    }

    // Destructor
    ~CircularBuffer() {
        delete[] buffer;  // deallocate memory
    }

    // Check if buffer is full
    bool isFull() {
        return size == capacity;
    }

    // Check if buffer is empty
    bool isEmpty() {
        return size == 0;
    }

    // Add element to buffer
    void enqueue(int value) {
        if (isFull()) {
            cout << "Overflow! Buffer is full." << endl;
            return;
        }

        rear = (rear + 1) % capacity; // move rear circularly
        buffer[rear] = value;
        size++;
        cout << value << " added to buffer." << endl;
    }

    // Remove element from buffer
    void dequeue() {
        if (isEmpty()) {
            cout << "Underflow! Buffer is empty." << endl;
            return;
        }

        cout << buffer[front] << " removed from buffer." << endl;
        front = (front + 1) % capacity; // move front circularly
        size--;
    }

    // Display buffer elements
    void display() {
        if (isEmpty()) {
            cout << "Buffer is empty." << endl;
            return;
        }

        cout << "Buffer elements: ";
        for (int i = 0; i < size; i++) {
            int index = (front + i) % capacity;
            cout << buffer[index] << " ";
        }
        cout << endl;
    }
};

int main() {
    int capacity;
    cout << "Enter buffer capacity: ";
    cin >> capacity;

    CircularBuffer cb(capacity);

    int choice, value;

    do {
        cout << "\nMenu:\n";
        cout << "1. Add element\n";
        cout << "2. Remove element\n";
        cout << "3. Display buffer\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter value to add: ";
                cin >> value;
                cb.enqueue(value);
                break;

            case 2:
                cb.dequeue();
                break;

            case 3:
                cb.display();
                break;

            case 4:
                cout << "Exiting..." << endl;
                break;

            default:
                cout << "Invalid choice. Try again." << endl;
        }
    } while (choice != 4);

    return 0;
}
```
```
Output
Enter buffer capacity: 3

Menu:
1. Add element
2. Remove element
3. Display buffer
4. Exit
Enter your choice: 1
Enter value to add: 10
10 added to buffer.

Enter your choice: 1
Enter value to add: 20
20 added to buffer.

Enter your choice: 1
Enter value to add: 30
30 added to buffer.

Enter your choice: 1
Enter value to add: 40
Overflow! Buffer is full.

Enter your choice: 3
Buffer elements: 10 20 30

Enter your choice: 2
10 removed from buffer.

Enter your choice: 3
Buffer elements: 20 30
```
## Q40
```cpp
#include <iostream>
using namespace std;

int main() {
    const int num = 50;      // constant variable (cannot be changed)

    // Pointer to a constant int
    const int *ptr = &num;

    // Reading value using the pointer (allowed)
    cout << "Value of num using pointer: " << *ptr << endl;

    // Trying to modify the value through pointer (NOT allowed)
    // *ptr = 100;   // This will cause a compile-time error

    // Direct modification of num is also not allowed
    // num = 100;    // This will also cause a compile-time error

    return 0;
}
```
```
Output
Value of num using pointer: 50
```
## Q41
```
Problem: Returning Reference to a Local Variable

A local variable exists only inside the function.
Once the function ends, the local variable is destroyed.
If you return a reference to it, the reference will point to memory that no longer exists → undefined behavior.
```
```
#wrong code
int& wrongFunction() {
    int x = 10;   // local variable
    return x;     // returning reference to local variable (dangerous!)
}
```
```
Correct Approach: Use Static or Global Variable

Static and global variables live throughout the program execution.
So returning a reference to them is safe.
```
### Using static variable
```cpp
#include <iostream>
using namespace std;

int& safeFunction() {
    static int x = 10;   // static variable persists after function ends
    return x;            // safe to return reference
}

int main() {
    int &ref = safeFunction();
    cout << "Value: " << ref << endl;  // prints 10

    ref = 50;                         // modify the static variable
    cout << "Modified Value: " << safeFunction() << endl;  // prints 50

    return 0;
}
```
```
Output
Value: 10
Modified Value: 50
```
### Using global variable
```cpp
#include <iostream>
using namespace std;

int globalVar = 10;   // global variable

int& safeGlobalFunction() {
    return globalVar; // safe to return reference
}

int main() {
    int &ref = safeGlobalFunction();
    cout << "Value: " << ref << endl;  // prints 10

    ref = 100;                        // modifies global variable
    cout << "Modified Value: " << safeGlobalFunction() << endl; // prints 100

    return 0;
}
```
```
Output
Value: 10
Modified Value: 100
```
## Q42
```cpp
#include <iostream>
using namespace std;

class Student {
private:
    string name;
    int rollNumber;
    float marks;

public:
    // Function to input student details
    void input() {
        cout << "Enter Name: ";
        cin >> name;
        cout << "Enter Roll Number: ";
        cin >> rollNumber;
        cout << "Enter Marks: ";
        cin >> marks;
    }

    // Function to display student details
    void display() {
        cout << "\nStudent Details:" << endl;
        cout << "Name: " << name << endl;
        cout << "Roll Number: " << rollNumber << endl;
        cout << "Marks: " << marks << endl;
    }
};

int main() {
    Student s1, s2, s3;

    cout << "Enter details for Student 1" << endl;
    s1.input();

    cout << "\nEnter details for Student 2" << endl;
    s2.input();

    cout << "\nEnter details for Student 3" << endl;
    s3.input();

    cout << "\nDisplaying Student Information:" << endl;
    s1.display();
    s2.display();
    s3.display();

    return 0;
}
```
```
Input:
Enter details for Student 1
Enter Name: rishav
Enter Roll Number: 3
Enter Marks: 25

Enter details for Student 2
Enter Name: nishant
Enter Roll Number: 2
Enter Marks: 24

Enter details for Student 3
Enter Name: raj
Enter Roll Number: 1
Enter Marks: 26
```
```
Output:
Displaying Student Information:

Student Details:
Name: rishav
Roll Number: 3
Marks: 25

Student Details:
Name: nishant
Roll Number: 2
Marks: 24

Student Details:
Name: raj
Roll Number: 1
Marks: 26
```
## Q43
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    int accountNumber;
    double balance;

public:
    // Constructor
    BankAccount(int accNo, double bal) {
        accountNumber = accNo;
        balance = bal;
        cout << "Account Created! Account No: " 
             << accountNumber << ", Balance: " 
             << balance << endl;
    }

    // Destructor
    ~BankAccount() {
        cout << "Account No: " << accountNumber 
             << " is being destroyed." << endl;
    }

    // Display function
    void display() {
        cout << "Account No: " << accountNumber 
             << ", Balance: " << balance << endl;
    }
};

// Function to create objects using user input
void createAccounts() {
    int accNo1, accNo2;
    double bal1, bal2;

    cout << "\nEnter details for Account 1\n";
    cout << "Account Number: ";
    cin >> accNo1;
    cout << "Balance: ";
    cin >> bal1;

    cout << "\nEnter details for Account 2\n";
    cout << "Account Number: ";
    cin >> accNo2;
    cout << "Balance: ";
    cin >> bal2;

    BankAccount acc1(accNo1, bal1);
    BankAccount acc2(accNo2, bal2);

    cout << "\nInside createAccounts() function." << endl;
    acc1.display();
    acc2.display();

} // Destructor automatically called here

int main() {
    cout << "Entering main()" << endl;

    createAccounts();

    cout << "Back in main()" << endl;

    return 0;
}
```
```
Output:
Entering main()

Enter details for Account 1
Account Number: 11454
Balance: 500000

Enter details for Account 2
Account Number: 29082
Balance: 400000
Account Created! Account No: 11454, Balance: 500000
Account Created! Account No: 29082, Balance: 400000

Inside createAccounts() function.
Account No: 11454, Balance: 500000
Account No: 29082, Balance: 400000
Account No: 29082 is being destroyed.
Account No: 11454 is being destroyed.
Back in main()
```
## Q44
```cpp
#include <iostream>
using namespace std;

class Employee {
private:
    string name;
    double salary;

public:
    // Constructor
    Employee(string empName, double empSalary) {
        name = empName;
        setSalary(empSalary);  // Validation
    }

    // Setter with validation
    void setSalary(double empSalary) {
        if (empSalary >= 0) {
            salary = empSalary;
        } else {
            cout << "Error: Salary cannot be negative. Setting salary to 0.\n";
            salary = 0;
        }
    }

    // Getter
    double getSalary() const {
        return salary;
    }

    void display() const {
        cout << "Employee Name: " << name << endl;
        cout << "Salary: " << salary << endl;
    }
};

int main() {
    string name1, name2;
    double salary1, salary2;

    // Input for Employee 1
    cout << "Enter name of Employee 1: ";
    cin >> name1;
    cout << "Enter salary of Employee 1: ";
    cin >> salary1;

    // Input for Employee 2
    cout << "\nEnter name of Employee 2: ";
    cin >> name2;
    cout << "Enter salary of Employee 2: ";
    cin >> salary2;

    // Creating objects using user input
    Employee emp1(name1, salary1);
    Employee emp2(name2, salary2);

    cout << "\nEmployee 1 Details:\n";
    emp1.display();

    cout << "\nEmployee 2 Details:\n";
    emp2.display();

    // Update salary example
    double newSalary;
    cout << "\nEnter new salary for Employee 2: ";
    cin >> newSalary;

    emp2.setSalary(newSalary);

    cout << "\nAfter updating salary:\n";
    emp2.display();

    return 0;
}
```
```
Input:
Enter name of Employee 1: rishav
Enter salary of Employee 1: 400000

Enter name of Employee 2: nikhil
Enter salary of Employee 2: -500000
Output:
ERROR!
Error: Salary cannot be negative. Setting salary to 0.

Employee 1 Details:
Employee Name: rishav
Salary: 400000

Employee 2 Details:
Employee Name: nikhil
Salary: 0

Enter new salary for Employee 2: 500000

After updating salary:
Employee Name: nikhil
Salary: 500000
```
## Q45
```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    // Add two integers
    int add(int a, int b) {
        return a + b;
    }

    // Add two double values
    double add(double a, double b) {
        return a + b;
    }

    // Add three integers
    int add(int a, int b, int c) {
        return a + b + c;
    }
};

int main() {
    Calculator calc;

    int choice;

    cout << "Choose an option:\n";
    cout << "1. Add two integers\n";
    cout << "2. Add two doubles\n";
    cout << "3. Add three integers\n";
    cout << "Enter your choice: ";
    cin >> choice;

    if (choice == 1) {
        int a, b;
        cout << "Enter two integers: ";
        cin >> a >> b;
        cout << "Sum: " << calc.add(a, b) << endl;
    }
    else if (choice == 2) {
        double a, b;
        cout << "Enter two double values: ";
        cin >> a >> b;
        cout << "Sum: " << calc.add(a, b) << endl;
    }
    else if (choice == 3) {
        int a, b, c;
        cout << "Enter three integers: ";
        cin >> a >> b >> c;
        cout << "Sum: " << calc.add(a, b, c) << endl;
    }
    else {
        cout << "Invalid choice!" << endl;
    }

    return 0;
}
```
```
Output
Choose an option:
1. Add two integers
2. Add two doubles
3. Add three integers
Enter your choice: 1
Enter two integers: 35 67
Sum: 102
```
## Q46
```cpp
#include <iostream>
using namespace std;

struct Subject {
    string name;
    int marks;
};

class Student {
private:
    int roll;
    string name;
    Subject* subjects;
    int n;

public:
    // Constructor
    Student(int numSubjects) {
        n = numSubjects;
        subjects = new Subject[n];
    }

    // Destructor
    ~Student() {
        delete[] subjects;
    }

    void input() {
        cout << "\nEnter Roll Number: ";
        cin >> roll;

        cout << "Enter Name: ";
        cin >> name;

        for (int i = 0; i < n; i++) {
            cout << "\nSubject " << i + 1 << " Name: ";
            cin >> subjects[i].name;
            cout << "Marks: ";
            cin >> subjects[i].marks;
        }
    }

    void display() {
        cout << "\nRoll No: " << roll;
        cout << "\nName: " << name;
        cout << "\nSubjects:\n";

        for (int i = 0; i < n; i++) {
            cout << subjects[i].name << " - "
                 << subjects[i].marks << endl;
        }

        cout << "Total: " << total();
        cout << "\nGrade: " << grade() << endl;
    }

    int total() {
        int sum = 0;
        for (int i = 0; i < n; i++)
            sum += subjects[i].marks;
        return sum;
    }

    char grade() {
        float avg = (float) total() / n;

        if (avg >= 90) return 'A';
        else if (avg >= 75) return 'B';
        else if (avg >= 50) return 'C';
        else return 'F';
    }
};

int main() {
    int numStudents, numSubjects;

    cout << "Enter number of students: ";
    cin >> numStudents;

    cout << "Enter number of subjects per student: ";
    cin >> numSubjects;

    // Create array of pointers
    Student** students = new Student*[numStudents];

    // Create each student object
    for (int i = 0; i < numStudents; i++) {
        students[i] = new Student(numSubjects);
    }

    // Input data
    for (int i = 0; i < numStudents; i++) {
        cout << "\nEnter details for Student " << i + 1;
        students[i]->input();
    }

    // Find topper
    int topper = 0;
    int highest = students[0]->total();

    for (int i = 1; i < numStudents; i++) {
        if (students[i]->total() > highest) {
            highest = students[i]->total();
            topper = i;
        }
    }

    // Display all students
    cout << "\n--- All Students ---\n";
    for (int i = 0; i < numStudents; i++) {
        students[i]->display();
    }

    // Display topper
    cout << "\n--- Topper ---\n";
    students[topper]->display();

    // Free memory properly
    for (int i = 0; i < numStudents; i++) {
        delete students[i];
    }
    delete[] students;

    return 0;
}
```
```
Input:
Enter number of students: 2
Enter number of subjects per student: 2

Enter details for Student 1
Enter Roll Number: 1
Enter Name: rishav

Subject 1 Name: eng
Marks: 38

Subject 2 Name: maths
Marks: 35

Enter details for Student 2
Enter Roll Number: 2
Enter Name: ronny

Subject 1 Name: maths
Marks: 39

Subject 2 Name: sci
Marks: 35
Output:
--- All Students ---

Roll No: 1
Name: rishav
Subjects:
eng - 38
maths - 35
Total: 73
Grade: F

Roll No: 2
Name: ronny
Subjects:
maths - 39
sci - 35
Total: 74
Grade: F

--- Topper ---

Roll No: 2
Name: ronny
Subjects:
maths - 39
sci - 35
Total: 74
Grade: F
```
## Q47
```cpp
#include <iostream>
#include <string>
using namespace std;

// Structure for Patient
struct Patient {
    int id;
    string name;
    int severity; // Higher value = higher priority
};

// Node structure for linked list
struct Node {
    Patient data;
    Node* next;
};

class PatientQueue {
private:
    Node* front; // Pointer to front of queue

public:
    // Constructor
    PatientQueue() {
        front = nullptr;
    }

    // Destructor to free all memory
    ~PatientQueue() {
        while (front != nullptr) {
            Node* temp = front;
            front = front->next;
            delete temp;
        }
    }

    // Enqueue based on severity (higher severity first)
    void enqueue(Patient p) {
        Node* newNode = new Node;
        newNode->data = p;
        newNode->next = nullptr;

        // If queue is empty or new node has higher severity
        if (front == nullptr || p.severity > front->data.severity) {
            newNode->next = front;
            front = newNode;
        } else {
            // Traverse to find correct position
            Node* temp = front;
            while (temp->next != nullptr && temp->next->data.severity >= p.severity) {
                temp = temp->next;
            }
            newNode->next = temp->next;
            temp->next = newNode;
        }
        cout << "Patient " << p.name << " enqueued successfully.\n";
    }

    // Dequeue (remove front patient)
    void dequeue() {
        if (front == nullptr) {
            cout << "Queue is empty. Cannot dequeue.\n";
            return;
        }
        Node* temp = front;
        cout << "Dequeued Patient: " << front->data.name << " (Severity: " 
             << front->data.severity << ")\n";
        front = front->next;
        delete temp;
    }

    // Display all patients
    void display() {
        if (front == nullptr) {
            cout << "Queue is empty.\n";
            return;
        }
        cout << "\nPatient Queue (High -> Low Severity):\n";
        Node* temp = front;
        while (temp != nullptr) {
            cout << "ID: " << temp->data.id 
                 << ", Name: " << temp->data.name 
                 << ", Severity: " << temp->data.severity << endl;
            temp = temp->next;
        }
    }
};

int main() {
    PatientQueue pq;
    int choice;

    do {
        cout << "\n--- Patient Queue Menu ---\n";
        cout << "1. Enqueue Patient\n";
        cout << "2. Dequeue Patient\n";
        cout << "3. Display Queue\n";
        cout << "4. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: {
                Patient p;
                cout << "Enter Patient ID: ";
                cin >> p.id;
                cout << "Enter Patient Name: ";
                cin >> p.name;
                cout << "Enter Severity (higher number = more severe): ";
                cin >> p.severity;
                pq.enqueue(p);
                break;
            }
            case 2:
                pq.dequeue();
                break;
            case 3:
                pq.display();
                break;
            case 4:
                cout << "Exiting...\n";
                break;
            default:
                cout << "Invalid choice! Try again.\n";
        }

    } while (choice != 4);

    return 0;
}
```
```
Output
--- Patient Queue Menu ---
1. Enqueue Patient
2. Dequeue Patient
3. Display Queue
4. Exit
Enter your choice: 1
Enter Patient ID: 234
Enter Patient Name: panshul
Enter Severity (higher number = more severe): 99
Patient panshul enqueued successfully.

--- Patient Queue Menu ---
1. Enqueue Patient
2. Dequeue Patient
3. Display Queue
4. Exit
Enter your choice: 2
Dequeued Patient: panshul (Severity: 99)

--- Patient Queue Menu ---
1. Enqueue Patient
2. Dequeue Patient
3. Display Queue
4. Exit
Enter your choice: 3
Queue is empty.

--- Patient Queue Menu ---
1. Enqueue Patient
2. Dequeue Patient
3. Display Queue
4. Exit
Enter your choice: 4
Exiting...
```
## Q48
```cpp
#include <iostream>
#include <string>
using namespace std;

// Structure for a book node
struct BookNode {
    int id;
    string title;
    string author;
    bool issued;       // true if issued, false otherwise
    BookNode* next;
};

// Library class
class Library {
private:
    BookNode* head;

public:
    // Constructor
    Library() {
        head = nullptr;
    }

    // Destructor to free all memory
    ~Library() {
        BookNode* temp;
        while (head != nullptr) {
            temp = head;
            head = head->next;
            delete temp;
        }
    }

    // Add a new book to the library
    void addBook(int id, const string& title, const string& author) {
        BookNode* newBook = new BookNode;
        newBook->id = id;
        newBook->title = title;
        newBook->author = author;
        newBook->issued = false;
        newBook->next = nullptr;

        if (head == nullptr) {
            head = newBook;
        } else {
            BookNode* temp = head;
            while (temp->next != nullptr) {
                temp = temp->next;
            }
            temp->next = newBook;
        }
        cout << "Book added successfully.\n";
    }

    // Issue a book by ID
    void issueBook(int id) {
        BookNode* temp = head;
        while (temp != nullptr) {
            if (temp->id == id) {
                if (!temp->issued) {
                    temp->issued = true;
                    cout << "Book '" << temp->title << "' issued successfully.\n";
                } else {
                    cout << "Book '" << temp->title << "' is already issued.\n";
                }
                return;
            }
            temp = temp->next;
        }
        cout << "Book with ID " << id << " not found.\n";
    }

    // Return a book by ID
    void returnBook(int id) {
        BookNode* temp = head;
        while (temp != nullptr) {
            if (temp->id == id) {
                if (temp->issued) {
                    temp->issued = false;
                    cout << "Book '" << temp->title << "' returned successfully.\n";
                } else {
                    cout << "Book '" << temp->title << "' was not issued.\n";
                }
                return;
            }
            temp = temp->next;
        }
        cout << "Book with ID " << id << " not found.\n";
    }

    // Search for a book by title
    void searchBook(const string& title) {
        BookNode* temp = head;
        while (temp != nullptr) {
            if (temp->title == title) {
                cout << "Book Found! ID: " << temp->id
                     << ", Author: " << temp->author
                     << ", Issued: " << (temp->issued ? "Yes" : "No") << endl;
                return;
            }
            temp = temp->next;
        }
        cout << "Book '" << title << "' not found in the library.\n";
    }

    // Display all books
    void displayAll() {
        if (head == nullptr) {
            cout << "Library is empty.\n";
            return;
        }
        cout << "\n--- All Books in Library ---\n";
        BookNode* temp = head;
        while (temp != nullptr) {
            cout << "ID: " << temp->id
                 << ", Title: " << temp->title
                 << ", Author: " << temp->author
                 << ", Issued: " << (temp->issued ? "Yes" : "No") << endl;
            temp = temp->next;
        }
    }
};

int main() {
    Library lib;
    int choice;

    do {
        cout << "\n--- Library Menu ---\n";
        cout << "1. Add Book\n";
        cout << "2. Issue Book\n";
        cout << "3. Return Book\n";
        cout << "4. Search Book by Title\n";
        cout << "5. Display All Books\n";
        cout << "6. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1: {
                int id;
                string title, author;
                cout << "Enter Book ID: ";
                cin >> id;
                cin.ignore(); // clear newline
                cout << "Enter Book Title: ";
                getline(cin, title);
                cout << "Enter Author Name: ";
                getline(cin, author);
                lib.addBook(id, title, author);
                break;
            }
            case 2: {
                int id;
                cout << "Enter Book ID to issue: ";
                cin >> id;
                lib.issueBook(id);
                break;
            }
            case 3: {
                int id;
                cout << "Enter Book ID to return: ";
                cin >> id;
                lib.returnBook(id);
                break;
            }
            case 4: {
                string title;
                cin.ignore(); // clear newline
                cout << "Enter Book Title to search: ";
                getline(cin, title);
                lib.searchBook(title);
                break;
            }
            case 5:
                lib.displayAll();
                break;
            case 6:
                cout << "Exiting Library System.\n";
                break;
            default:
                cout << "Invalid choice! Try again.\n";
        }
    } while (choice != 6);

    return 0;
}
```
```
Output
--- Library Menu ---
1. Add Book
2. Issue Book
3. Return Book
4. Search Book by Title
5. Display All Books
6. Exit
Enter your choice: 1
Enter Book ID: 305
Enter Book Title: harry potter
Enter Author Name: jk rowling
Book added successfully.

--- Library Menu ---
1. Add Book
2. Issue Book
3. Return Book
4. Search Book by Title
5. Display All Books
6. Exit
Enter your choice: 2
Enter Book ID to issue: 305
Book 'harry potter' issued successfully.

--- Library Menu ---
1. Add Book
2. Issue Book
3. Return Book
4. Search Book by Title
5. Display All Books
6. Exit
Enter your choice: 3
Enter Book ID to return: 
305
Book 'harry potter' returned successfully.

--- Library Menu ---
1. Add Book
2. Issue Book
3. Return Book
4. Search Book by Title
5. Display All Books
6. Exit
Enter your choice: 4
Enter Book Title to search: harry potter
Book Found! ID: 305, Author: jk rowling, Issued: No

--- Library Menu ---
1. Add Book
2. Issue Book
3. Return Book
4. Search Book by Title
5. Display All Books
6. Exit
Enter your choice: 5

--- All Books in Library ---
ID: 305, Title: harry potter, Author: jk rowling, Issued: No

--- Library Menu ---
1. Add Book
2. Issue Book
3. Return Book
4. Search Book by Title
5. Display All Books
6. Exit
Enter your choice: 6
Exiting Library System.
```
## Q49
```cpp
#include <iostream>
#include <string>
using namespace std;

// Structure for Transaction
struct Transaction {
    string type;   // "Deposit" or "Withdraw"
    double amount;
    string date;
    Transaction* next;
};

// Class for Bank Account
class BankAccount {
private:
    int accountNo;
    string holderName;
    double balance;
    Transaction* historyHead;

    // Add a transaction to the history
    void addTransaction(const string& type, double amount, const string& date) {
        Transaction* newTrans = new Transaction;
        newTrans->type = type;
        newTrans->amount = amount;
        newTrans->date = date;
        newTrans->next = nullptr;

        if (historyHead == nullptr) {
            historyHead = newTrans;
        } else {
            Transaction* temp = historyHead;
            while (temp->next != nullptr) {
                temp = temp->next;
            }
            temp->next = newTrans;
        }
    }

public:
    // Constructor
    BankAccount(int accNo, const string& name, double bal) {
        accountNo = accNo;
        holderName = name;
        balance = bal;
        historyHead = nullptr;
        if (bal > 0)
            addTransaction("Deposit", bal, "Initial");
    }

    // Destructor
    ~BankAccount() {
        Transaction* temp;
        while (historyHead != nullptr) {
            temp = historyHead;
            historyHead = historyHead->next;
            delete temp;
        }
    }

    // Deposit money
    void deposit(double amt, const string& date) {
        if (amt <= 0) {
            cout << "Invalid deposit amount.\n";
            return;
        }
        balance += amt;
        addTransaction("Deposit", amt, date);
        cout << "Deposited " << amt << " successfully.\n";
    }

    // Withdraw money
    void withdraw(double amt, const string& date) {
        if (amt <= 0) {
            cout << "Invalid withdrawal amount.\n";
            return;
        }
        if (amt > balance) {
            cout << "Insufficient balance!\n";
            return;
        }
        balance -= amt;
        addTransaction("Withdraw", amt, date);
        cout << "Withdrawn " << amt << " successfully.\n";
    }

    // Show transaction history
    void showHistory() {
        if (historyHead == nullptr) {
            cout << "No transactions yet.\n";
            return;
        }
        cout << "\nTransaction History for Account " << accountNo << ":\n";
        Transaction* temp = historyHead;
        while (temp != nullptr) {
            cout << temp->date << " - " << temp->type << " - " << temp->amount << endl;
            temp = temp->next;
        }
    }

    // Show current balance
    void showBalance() {
        cout << "Account No: " << accountNo
             << ", Holder: " << holderName
             << ", Balance: " << balance << endl;
    }

    // Getter for account number
    int getAccountNo() const {
        return accountNo;
    }
};

int main() {
    int numAccounts;
    cout << "Enter number of accounts to create: ";
    cin >> numAccounts;

    BankAccount** accounts = new BankAccount*[numAccounts];

    // Create accounts
    for (int i = 0; i < numAccounts; i++) {
        int accNo;
        string name;
        double initialBalance;

        cout << "\nEnter details for Account " << i + 1 << ":\n";
        cout << "Account Number: ";
        cin >> accNo;
        cin.ignore(); // clear newline
        cout << "Holder Name: ";
        getline(cin, name);
        cout << "Initial Balance: ";
        cin >> initialBalance;

        accounts[i] = new BankAccount(accNo, name, initialBalance);
    }

    int choice;
    do {
        cout << "\n--- Bank Menu ---\n";
        cout << "1. Deposit\n";
        cout << "2. Withdraw\n";
        cout << "3. Show Balance\n";
        cout << "4. Show Transaction History\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        if (choice >= 1 && choice <= 4) {
            int accNo;
            cout << "Enter Account Number: ";
            cin >> accNo;

            // Find account
            BankAccount* account = nullptr;
            for (int i = 0; i < numAccounts; i++) {
                if (accounts[i]->getAccountNo() == accNo) {
                    account = accounts[i];
                    break;
                }
            }

            if (account == nullptr) {
                cout << "Account not found!\n";
                continue;
            }

            if (choice == 1) {
                double amt;
                string date;
                cout << "Enter amount to deposit: ";
                cin >> amt;
                cin.ignore();
                cout << "Enter date (YYYY-MM-DD): ";
                getline(cin, date);
                account->deposit(amt, date);
            } else if (choice == 2) {
                double amt;
                string date;
                cout << "Enter amount to withdraw: ";
                cin >> amt;
                cin.ignore();
                cout << "Enter date (YYYY-MM-DD): ";
                getline(cin, date);
                account->withdraw(amt, date);
            } else if (choice == 3) {
                account->showBalance();
            } else if (choice == 4) {
                account->showHistory();
            }
        } else if (choice != 5) {
            cout << "Invalid choice! Try again.\n";
        }

    } while (choice != 5);

    // Free memory
    for (int i = 0; i < numAccounts; i++) {
        delete accounts[i];
    }
    delete[] accounts;

    cout << "Exiting Bank System.\n";
    return 0;
}
```
```
Output
Enter number of accounts to create: 3

Enter details for Account 1:
Account Number: 209
Holder Name: rishav
Initial Balance: 5000

Enter details for Account 2:
Account Number: 205
Holder Name: panshul
Initial Balance: 5000000

Enter details for Account 3:
Account Number: 3
Holder Name: ronny
Initial Balance: 6000

--- Bank Menu ---
1. Deposit
2. Withdraw
3. Show Balance
4. Show Transaction History
5. Exit
Enter your choice: 1
Enter Account Number: 209
Enter amount to deposit: 4000
Enter date (YYYY-MM-DD): 2026-01-30
Deposited 4000 successfully.

--- Bank Menu ---
1. Deposit
2. Withdraw
3. Show Balance
4. Show Transaction History
5. Exit
Enter your choice: 3
Enter Account Number: 209
Account No: 209, Holder: rishav, Balance: 9000

--- Bank Menu ---
1. Deposit
2. Withdraw
3. Show Balance
4. Show Transaction History
5. Exit
Enter your choice: 4
Enter Account Number: 209

Transaction History for Account 209:
Initial - Deposit - 5000
2026-01-30 - Deposit - 4000

--- Bank Menu ---
1. Deposit
2. Withdraw
3. Show Balance
4. Show Transaction History
5. Exit
Enter your choice: 5
Exiting Bank System.
```
## Q50
```cpp
#include <iostream>
#include <string>
using namespace std;

// Structure for Course
struct Course {
    string courseCode;
    string courseName;
    int credits;
};

// Class for Student
class Student {
private:
    int roll;
    string name;
    Course* registeredCourses; // dynamic array of courses
    int courseCount;           // number of registered courses

public:
    // Constructor
    Student(int r, const string& n) {
        roll = r;
        name = n;
        registeredCourses = nullptr;
        courseCount = 0;
    }

    // Destructor
    ~Student() {
        delete[] registeredCourses;
    }

    // Register a new course
    void registerCourses() {
        int n;
        cout << "How many courses to register for " << name << "? ";
        cin >> n;

        // Create new dynamic array for registered courses
        Course* newCourses = new Course[courseCount + n];

        // Copy old courses if any
        for (int i = 0; i < courseCount; i++)
            newCourses[i] = registeredCourses[i];

        // Input new courses
        for (int i = 0; i < n; i++) {
            cout << "Enter Course Code: ";
            cin >> newCourses[courseCount + i].courseCode;
            cin.ignore();
            cout << "Enter Course Name: ";
            getline(cin, newCourses[courseCount + i].courseName);
            cout << "Enter Credits: ";
            cin >> newCourses[courseCount + i].credits;
        }

        delete[] registeredCourses;       // free old array
        registeredCourses = newCourses;   // assign new array
        courseCount += n;

        cout << "Courses registered successfully for " << name << ".\n";
    }

    // Drop a course by code
    void dropCourse(const string& code) {
        int index = -1;
        for (int i = 0; i < courseCount; i++) {
            if (registeredCourses[i].courseCode == code) {
                index = i;
                break;
            }
        }

        if (index == -1) {
            cout << "Course not found.\n";
            return;
        }

        // Shift courses left to remove
        for (int i = index; i < courseCount - 1; i++) {
            registeredCourses[i] = registeredCourses[i + 1];
        }
        courseCount--;

        cout << "Course " << code << " dropped successfully from " << name << ".\n";
    }

    // Show all registered courses
    void showCourses() {
        if (courseCount == 0) {
            cout << name << " has no registered courses.\n";
            return;
        }
        cout << "\nCourses registered for " << name << ":\n";
        for (int i = 0; i < courseCount; i++) {
            cout << registeredCourses[i].courseCode << " - "
                 << registeredCourses[i].courseName
                 << " (" << registeredCourses[i].credits << " credits)\n";
        }
    }

    // Total credits
    int totalCredits() {
        int total = 0;
        for (int i = 0; i < courseCount; i++)
            total += registeredCourses[i].credits;
        return total;
    }

    // Getter for roll number
    int getRoll() const { return roll; }

    // Getter for student name
    string getName() const { return name; }

    // Check if student is registered in a course
    bool isRegisteredIn(const string& courseCode) const {
        for (int i = 0; i < courseCount; i++) {
            if (registeredCourses[i].courseCode == courseCode)
                return true;
        }
        return false;
    }
};

int main() {
    int numStudents;
    cout << "Enter number of students: ";
    cin >> numStudents;

    Student** students = new Student*[numStudents];

    // Input student details
    for (int i = 0; i < numStudents; i++) {
        int roll;
        string name;
        cout << "\nEnter details for Student " << i + 1 << ":\n";
        cout << "Roll Number: ";
        cin >> roll;
        cin.ignore();
        cout << "Name: ";
        getline(cin, name);
        students[i] = new Student(roll, name);

        // Register courses for each student
        students[i]->registerCourses();
    }

    int choice;
    do {
        cout << "\n--- Menu ---\n";
        cout << "1. Show Courses of a Student\n";
        cout << "2. Drop a Course for a Student\n";
        cout << "3. Show Total Credits of a Student\n";
        cout << "4. Show Students Registered in a Course\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        if (choice == 1) {
            int roll;
            cout << "Enter Roll Number: ";
            cin >> roll;
            for (int i = 0; i < numStudents; i++) {
                if (students[i]->getRoll() == roll) {
                    students[i]->showCourses();
                    break;
                }
            }
        } else if (choice == 2) {
            int roll;
            string code;
            cout << "Enter Roll Number: ";
            cin >> roll;
            cin.ignore();
            cout << "Enter Course Code to drop: ";
            getline(cin, code);
            for (int i = 0; i < numStudents; i++) {
                if (students[i]->getRoll() == roll) {
                    students[i]->dropCourse(code);
                    break;
                }
            }
        } else if (choice == 3) {
            int roll;
            cout << "Enter Roll Number: ";
            cin >> roll;
            for (int i = 0; i < numStudents; i++) {
                if (students[i]->getRoll() == roll) {
                    cout << students[i]->getName() << " has total "
                         << students[i]->totalCredits() << " credits.\n";
                    break;
                }
            }
        } else if (choice == 4) {
            string code;
            cin.ignore();
            cout << "Enter Course Code: ";
            getline(cin, code);
            cout << "\nStudents registered in " << code << ":\n";
            for (int i = 0; i < numStudents; i++) {
                if (students[i]->isRegisteredIn(code))
                    cout << students[i]->getName() << " (Roll: "
                         << students[i]->getRoll() << ")\n";
            }
        } else if (choice != 5) {
            cout << "Invalid choice! Try again.\n";
        }

    } while (choice != 5);

    // Free memory
    for (int i = 0; i < numStudents; i++)
        delete students[i];
    delete[] students;

    return 0;
}
```
```
Output
Enter number of students: 2

Enter details for Student 1:
Roll Number: 1
Name: rishav
How many courses to register for rishav? 2
Enter Course Code: 105
Enter Course Name: maths
Enter Credits: 4
Enter Course Code: 106
Enter Course Name: cpp
Enter Credits: 4
Courses registered successfully for rishav.

Enter details for Student 2:
Roll Number: 3
Name: ronny
How many courses to register for ronny? 2
Enter Course Code: 106
Enter Course Name: cpp
Enter Credits: 4
Enter Course Code: 107
Enter Course Name: mfc
Enter Credits: 4
Courses registered successfully for ronny.

--- Menu ---
1. Show Courses of a Student
2. Drop a Course for a Student
3. Show Total Credits of a Student
4. Show Students Registered in a Course
5. Exit
Enter your choice: 1
Enter Roll Number: 1

Courses registered for rishav:
105 - maths (4 credits)
106 - cpp (4 credits)

--- Menu ---
1. Show Courses of a Student
2. Drop a Course for a Student
3. Show Total Credits of a Student
4. Show Students Registered in a Course
5. Exit
Enter your choice: 3
Enter Roll Number: 3
ronny has total 8 credits.

--- Menu ---
1. Show Courses of a Student
2. Drop a Course for a Student
3. Show Total Credits of a Student
4. Show Students Registered in a Course
5. Exit
Enter your choice: 4
Enter Course Code: 105

Students registered in 105:
rishav (Roll: 1)

--- Menu ---
1. Show Courses of a Student
2. Drop a Course for a Student
3. Show Total Credits of a Student
4. Show Students Registered in a Course
5. Exit
Enter your choice: 5
```
## Q51
```cpp
#include <iostream>
#include <string>
#include <sstream>
using namespace std;

// Structure for directory/file node
struct DirNode {
    string name;
    bool isFile;
    DirNode* child;   // first child
    DirNode* sibling; // next sibling

    DirNode(const string& n, bool file) : name(n), isFile(file), child(nullptr), sibling(nullptr) {}
};

// Class for Directory Tree
class DirectoryTree {
private:
    DirNode* root;

    // Helper function to split path
    void splitPath(const string& path, string parts[], int& count) {
        stringstream ss(path);
        string token;
        count = 0;
        while (getline(ss, token, '/')) {
            if (!token.empty())
                parts[count++] = token;
        }
    }

    // Helper function to find node (returns parent if create = false)
    DirNode* findNode(const string path, bool create = false, bool asFile = false) {
        if (path == "/") return root;

        string parts[100];
        int n;
        splitPath(path, parts, n);

        DirNode* curr = root;
        for (int i = 0; i < n; i++) {
            DirNode* prev = nullptr;
            DirNode* temp = curr->child;
            while (temp != nullptr && temp->name != parts[i]) {
                prev = temp;
                temp = temp->sibling;
            }

            if (!temp) {
                if (create) {
                    // Create new folder/file
                    temp = new DirNode(parts[i], asFile && i == n-1);
                    if (!curr->child) {
                        curr->child = temp;
                    } else {
                        prev->sibling = temp;
                    }
                } else {
                    return nullptr; // not found
                }
            }

            curr = temp;
        }
        return curr;
    }

    // Helper function to list contents
    void listHelper(DirNode* node, int level = 0) {
        if (!node) return;
        for (DirNode* temp = node->child; temp != nullptr; temp = temp->sibling) {
            for (int i = 0; i < level; i++) cout << "  ";
            cout << (temp->isFile ? "File: " : "Dir: ") << temp->name << endl;
            listHelper(temp, level + 1);
        }
    }

    // Helper function to delete a node
    bool deleteHelper(DirNode* parent, const string& name) {
        if (!parent || !parent->child) return false;
        DirNode* temp = parent->child;
        DirNode* prev = nullptr;

        while (temp && temp->name != name) {
            prev = temp;
            temp = temp->sibling;
        }

        if (!temp) return false; // not found

        // Remove node from list
        if (!prev) parent->child = temp->sibling;
        else prev->sibling = temp->sibling;

        // Free memory recursively
        freeNode(temp);
        return true;
    }

    // Free memory of node and its children
    void freeNode(DirNode* node) {
        if (!node) return;
        freeNode(node->child);
        freeNode(node->sibling);
        delete node;
    }

public:
    // Constructor
    DirectoryTree() {
        root = new DirNode("/", false);
    }

    // Destructor
    ~DirectoryTree() {
        freeNode(root);
    }

    // Create a folder
    void createFolder(const string& path) {
        if (findNode(path, true, false))
            cout << "Folder created at " << path << endl;
    }

    // Create a file
    void createFile(const string& path) {
        if (findNode(path, true, true))
            cout << "File created at " << path << endl;
    }

    // List contents of a path
    void list(const string& path) {
        DirNode* node = findNode(path);
        if (!node) {
            cout << "Path not found!\n";
            return;
        }
        listHelper(node);
    }

    // Delete folder/file
    void deleteNode(const string& path) {
        if (path == "/") {
            cout << "Cannot delete root!\n";
            return;
        }

        string parts[100];
        int n;
        splitPath(path, parts, n);

        // Find parent node
        string parentPath = "/";
        for (int i = 0; i < n - 1; i++) {
            parentPath += parts[i];
            if (i != n - 2) parentPath += "/";
        }

        DirNode* parent = findNode(parentPath);
        if (!parent) {
            cout << "Parent path not found!\n";
            return;
        }

        if (deleteHelper(parent, parts[n - 1]))
            cout << "Deleted node: " << parts[n - 1] << endl;
        else
            cout << "Node not found!\n";
    }
};

int main() {
    DirectoryTree dt;
    int choice;
    do {
        cout << "\n--- Directory Menu ---\n";
        cout << "1. Create Folder\n";
        cout << "2. Create File\n";
        cout << "3. List Directory\n";
        cout << "4. Delete Node\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;
        cin.ignore();

        if (choice == 1) {
            string path;
            cout << "Enter folder path: ";
            getline(cin, path);
            dt.createFolder(path);
        } else if (choice == 2) {
            string path;
            cout << "Enter file path: ";
            getline(cin, path);
            dt.createFile(path);
        } else if (choice == 3) {
            string path;
            cout << "Enter path to list: ";
            getline(cin, path);
            dt.list(path);
        } else if (choice == 4) {
            string path;
            cout << "Enter path to delete: ";
            getline(cin, path);
            dt.deleteNode(path);
        } else if (choice != 5) {
            cout << "Invalid choice!\n";
        }

    } while (choice != 5);

    return 0;
}
```
```
Output
--- Directory Menu ---
1. Create Folder
2. Create File
3. List Directory
4. Delete Node
5. Exit
Enter your choice: 1
Enter folder path: downloads/mfc
Folder created at downloads/mfc

--- Directory Menu ---
1. Create Folder
2. Create File
3. List Directory
4. Delete Node
5. Exit
Enter your choice: 2
Enter file path: mfc/download
File created at mfc/download

--- Directory Menu ---
1. Create Folder
2. Create File
3. List Directory
4. Delete Node
5. Exit
Enter your choice: 3
Enter path to list: cpp/download
Path not found!

--- Directory Menu ---
1. Create Folder
2. Create File
3. List Directory
4. Delete Node
5. Exit
Enter your choice: 4
Enter path to delete: download/mfc
Parent path not found!

--- Directory Menu ---
1. Create Folder
2. Create File
3. List Directory
4. Delete Node
5. Exit
Enter your choice: 5
```







