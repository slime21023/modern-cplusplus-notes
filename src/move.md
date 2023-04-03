# move
* `template <class T>typename remove_reference<T>::type&& move (T&& arg) noexcept;`

**Move as rvalue**
* Returns an **rvalue reference** to arg.

**Example**

```c++
#include <utility>
#include <iostream>
#include <vector>
#include <string>

int main () {
  std::string foo = "foo-string";
  std::string bar = "bar-string";
  std::vector<std::string> myvector;

  myvector.push_back (foo);                    // copies
  myvector.push_back (std::move(bar));         // moves

  std::cout << "myvector contains:";
  for (std::string& x:myvector) std::cout << ' ' << x;
  std::cout << '\n';

  return 0;
}
```
