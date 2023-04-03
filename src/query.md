# existence query

### `all_of`

`template <class InputIterator, class UnaryPredicate>  bool all_of (InputIterator first, InputIterator last, UnaryPredicate pred);`

**Test condition on all elements in range**
* Returns **true** if **pred** returns **true** for all the elements in the range `[first,last)` or if the range is empty, and false otherwise.

```c++
#include <iostream>
#include <algorithm>
#include <array>

int main () {
  std::array<int,8> foo = {3,5,7,11,13,17,19,23};

  if ( std::all_of(foo.begin(), foo.end(), [](int i){return i%2;}) )
    std::cout << "All the elements are odd numbers.\n";

  return 0;
}
```

### `any_of`
`template <class InputIterator, class UnaryPredicate>  bool any_of (InputIterator first, InputIterator last, UnaryPredicate pred);`

**Test if any element in range fulfills condition**
* Returns **true** if **pred** returns **true** for any of the elements in the range `[first,last)`, and false otherwise.
* If `[first,last)` is an empty range, the function returns false.

```c++
#include <iostream>
#include <algorithm>
#include <array>
int main () {
  std::array<int,7> foo = {0,1,-1,3,-3,5,-5};

  if ( std::any_of(foo.begin(), foo.end(), [](int i){return i<0;}) )
    std::cout << "There are negative elements in the range.\n";

  return 0;
}
```

### `none_of`
`template <class InputIterator, class UnaryPredicate>  bool none_of (InputIterator first, InputIterator last, UnaryPredicate pred);`

**Test if no elements fulfill conditio**
* Returns **true** if **pred** returns **false** for all the elements in the range `[first,last)` or if the range is empty, and false otherwise.

```c++
#include <iostream>
#include <algorithm>
#include <array>
int main () {
  std::array<int,8> foo = {1,2,4,8,16,32,64,128};

  if ( std::none_of(foo.begin(), foo.end(), [](int i){return i<0;}) )
    std::cout << "There are no negative elements in the range.\n";

  return 0;
}
```


### Other operations
- [find](https://cplusplus.com/reference/algorithm/find/)
- [find_if](https://cplusplus.com/reference/algorithm/find_if/)
- [find_if_not](https://cplusplus.com/reference/algorithm/find_if_not/)