# unordered_set

- An associative container that contains a set of **unique** objects of type **Key**.
- Need to include `<unordered_set>` header file.
- Search, removal, and insertion times are constant.
- Implemented as Hash Table.
- Functions:
  - size()
  - =
  - clear()
  - count(), find()
  - empty()
  - insert(key), insert(iterator1, iterator2), insert(init_list)
  - erase(key), erase(iterator1, iterator2), erase(iterator)
  - bucket_count(), load_factor()

### Example
```c++

#include <iostream>
#include <unordered_set>

using namespace std;

int main()
{
    unordered_set<int> us = { 5, 4, 10, 5, 5, 20, 15 };
    for(int x: us)
    {
        cout << x << " ";
    }
    cout << endl;
    
    cout << "size = " << us.size() << endl;
    cout << "count(5) = " << us.count(5) << endl;
    cout << "num erased(5) " << us.erase(5) << endl;
    cout << boolalpha << "found 16 = " << (us.find(16) != us.end()) << endl;
    
    cout << "num buckets = " << us.bucket_count() << endl;
    cout << "load factor = " << us.load_factor() << endl;
    
    return 0;
}
```