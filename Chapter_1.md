## 1. auto

1.1 
```
#include <iostream>
#include <type_traits>
#include <vector>
#include <typeinfo>
 
using std::cout;
using std::endl;
using std::vector;
 
// 1. placeholder type specifiers
 
template<class T, class U>
auto add(T t, U u) { return t + u; }
 
int main()
{
 
  auto res = add(2,3.0);
 
  cout << res << " has type " << typeid(res).name() << endl;
  return 0;
}
```
Output:
```
5 has type d
```
`typeid().name`: 用于获取该变量类型。

1.2
```
#include <iostream>
#include <type_traits>
#include <vector>
#include <typeinfo>
#include <cstring>

using std::cout;
using std::endl;
using std::vector;

int main()
{

  int data[10];
  auto& i = data;

  cout << i << endl;
  cout << typeid(data).name() << endl;
  cout << typeid(int(&)[10]).name() << endl;
  return 0;
}
```
`i`: 为地址

1.3
```
#include <iostream>
#include <string>

using std::cout;
using std::endl;

int main()
{

std::string s{'a', 'b', 'c'};
cout << s << endl;

}

```
Output:
```
abc
```
```
Value initialization, e.g.	
std::string s{};
   
Direct initialization, e.g.	
std::string s("hello");
   
Copy initialization, e.g.	
std::string s = "hello";
   
List initialization, e.g.	
std::string s{'a', 'b', 'c'};
```
