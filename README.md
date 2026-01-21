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
