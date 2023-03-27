# array

array為sequence container
* `std::array`用來封裝固定大小的陣列
* 需要arraysize (compile time會用到)
* Assign by value
* Access element:
  * at()
  * []
  * front()
  * back()
  * data() 

### Declare and initialize the array
```c++
std::array<int, 5> myArray = {1, 2, 3, 4, 5};
// or
myArray.fill(0); // fills all elements with the value 0
```

### Get array size
```c++
int size = myArray.size(); // returns the number of elements in the array
```

### Iterate over the elements of the array
```c++
for (int i = 0; i < myArray.size(); i++) {
    std::cout << myArray[i] << std::endl;
}

for (auto element : myArray) {
    std::cout << element << std::endl;
}
```

### Example
```c++
#include <iostream>
#include <array>


int main() {
    std::array<int, 5> myArray = {1, 2, 3, 4, 5};
    
    for (int i = 0; i < myArray.size(); i++) {
        std::cout << myArray[i] << std::endl;
    }

    for (auto element : myArray) {
        std::cout << element << std::endl;
    }
    
    return 0;
}
```