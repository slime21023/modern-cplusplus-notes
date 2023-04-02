# map

- An associative container that contains key-value pairs with unique keys (**sorted**).
- Need to include `<map>` header file.
- A user-provided **Compare** can be supplied to change the ordering (**sorting**).
- Search, removal, and insertion times are logarithmic.
- Usually implemented as RB Trees.
- Functions
  - size()
  - =
  - [], at()
  - clear()
  - count(), find()
  - empty()
  - insert(pair), insert(iterator1, iterator2), insert(init_list)
  - erase(key), erase(iterator), erase(iterator1, iterator2)
  - begin(), end()
  - upper_bound(key), lower_bound(key)

### Example
```c++
#include <iostream>
#include <map>

using namespace std;

int main()
{
    map<int, string> m = {{10, "cat"}, {20, "dog"}, {5, "bat"}};
    cout << "size = " << m.size() << endl;
    
    for(auto& p: m)
    {
        cout << "{" << p.first << ", " << p.second << "} ";
    }
    cout << endl;
    
    m.insert({100, "rabbit"});
    m.insert({10, "fish"});
    
    int num_erased = m.erase(10);
    cout << "num_erased = " << num_erased << endl;
    
    auto ub = m.upper_bound(15);
    auto lb = m.lower_bound(15);
    cout << "ub = " << ub->first << endl;
    cout << "lb = " << lb->first << endl;
    
    m.insert({{-10, "apple"}, {-30, "orange"}, {-20, "mango"}});
    
    map<int, string> m2 = {{10, "aa"}, {20, "bb"}, {15, "cc"}, {5, "dd"}};
    m.insert(m2.begin(), m2.end());
    
    for(auto& p: m)
    {
        cout << "{" << p.first << ", " << p.second << "} ";
    }
    cout << endl;
    return 0;
}
```