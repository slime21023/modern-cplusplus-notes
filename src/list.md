# list
list 為 sequence container
* double linked list，允許非連續性的記憶體配置
* 不支援random access
* optimized for rapid insert and delete operations
* functions:
  * size()
  * =
  * front(), back()
  * empty()
  * begin(), end(), rbegin(), rend()
  * insert(), erase(), remove()
  * clear()
  * push_back(), push_front(), pop_back(), pop_front()


### Declare and initialize the list
```c++
// creates an empty list of integers
std::list<int> myList; 
```

Using the initializer list constructor:
```c++
std::list<int> originalList = {1, 2, 3, 4, 5};
// creates a copy of the original list
std::list<int> copiedList(originalList); 
```
Using the assignment operator:
```c++
std::list<int> originalList = {1, 2, 3, 4, 5};
std::list<int> copiedList;

// creates a copy of the original list
copiedList = originalList; 
```

### Add elements to the list
```c++
// adds the value 5 to the end of the list
myList.push_back(5); 
// adds the value 10 to the beginning of the list
myList.push_front(10); 
// adds the value 15 to the beginning of the list
myList.insert(myList.begin(), 15); 
```

### Remove elements from the list
```c++
// removes the last element from the list
myList.pop_back(); 
// removes the first element from the list
myList.pop_front(); 
// removes the first element from the list
myList.erase(myList.begin()); 
```

### Access elements in the list
```c++
// gets the first element of the list
int firstElement = myList.front(); 
// gets the last element of the list
int lastElement = myList.back(); 
```

### Get the size of the list
```c++
// returns the number of elements in the list
int size = myList.size(); 
```

### Iterate over the elements of the list
```c++
for (auto it = myList.begin(); it != myList.end(); it++) {
    std::cout << *it << std::endl;
}

for (auto element : myList) {
    std::cout << element << std::endl;
}
```

### Example
```c++
#include <iostream>
#include <list>



int main() {
   
    std::list<int> myList; // creates an empty list of integers
    myList.push_back(5); // adds the value 5 to the end of the list
    myList.push_front(10); // adds the value 10 to the beginning of the list
    myList.insert(myList.begin(), 15); // adds the value 15 to the beginning of the list
    
    for (auto it = myList.begin(); it != myList.end(); it++) {
        std::cout << *it << std::endl;
    }
    
    for (auto element : myList) {
        std::cout << element << std::endl;
    }

    
    return 0;
}

```