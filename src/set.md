# set

- An **associative container** that contains a sorted set of unique objects of
  type Key.

- A user-provided **Compare** can be supplied to change the **ordering
  (sorting)**.

- Search, removal, and insertion are logarithmic
- Usually implemented as RB Trees.
- Functions:
  - size()
  - =
  - clear()
  - count(), find()
  - empty()
  - insert(key), insert(iterator1, iterator2), insert(init_list)
  - erase(it), erase(it1, it2), erase(key)
  - upper_bound(key), lower_bound(key)

more detail: https://en.cppreference.com/w/cpp/container/set/insert

### Example
```c++
#include <iostream>
#include <set>

using namespace std;

int main() {
  set<int> s = {10, 20, 5, 10, 15, 20, 4};
  cout << "size = " << s.size() << endl;
  s.insert(100);
  s.insert(10);
  cout << "size = " << s.size() << endl;

  for(auto& el: s)
  {
    cout << el << " ";
  }
  cout << endl;

  auto it = s.erase(s.find(10));
  cout << *it << endl;

  auto ub = s.upper_bound(15);
  auto lb = s.lower_bound(15);
  cout << "ub = " << *ub << endl;
  cout << "lb = " << *lb << endl;
  
  return 0;
}

```
