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





