# cpp
discussion about pointers and some code
## Q1
//Q1
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
