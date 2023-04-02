# multimap

- An associative container that contains sorted list of key-value pairs allowing multiple entries with same keys.
- Need to include `<map>` header file.
- A user-provided **Compare** can be supplied to change the ordering (**sorting**).
- Search, removal, and insertion times are logarithmic.
- Usually implemented as RB Trees.

- Functions:
  - size()
  - =
  - clear()
  - count(), find()
  - empty()
  - insert(pair), insert(iterator1, iterator2), insert(init_list)
  - erase(key), erase(iterator), erase(iterator1, iterator2)
  - upper_bound(key), lower_bound(key)
  - equal_range(key)


### Example
```c++
#include <iostream>
#include <map>

using namespace std;

int main()
{
    multimap<int, string> m = {{10, "cat"}, {20, "dog"}, {5, "bat"}};
    cout << "size = " << m.size() << endl;
    
    
    m.insert({100, "rabbit"});
    m.insert({10, "fish"});
    m.insert({{10, "cat"}, {12, "bat"}});
    m.insert(make_pair<int, string>(12, "bat_2"));
    
    for(auto& p: m)
    {
        cout << "{" << p.first << ", " << p.second << "} ";
    }
    cout << endl;
    
    map<int, string> m2 = {{10, "aa"}, {20, "bb"}, {15, "cc"}, {5, "dd"}};
    m.insert(m2.begin(), m2.end());
    
    auto ub = m.upper_bound(15);
    auto lb = m.lower_bound(15);
    cout << "ub = " << ub->first << endl;
    cout << "lb = " << lb->first << endl;
    
    auto range = m.equal_range(10);
    for(auto it = range.first; it != range.second; ++it)
    {
        cout << it->second << "    ";
    }
    cout << endl;
    
    return 0;
}
```
