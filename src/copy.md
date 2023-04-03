# copy
* `copy`
* `copy_if`

### `copy`
`template <class InputIterator, class OutputIterator> OutputIterator copy (InputIterator first, InputIterator last, OutputIterator result);`

**Copy range of elements**
* Copies the elements in the range `[first,last)` into the range beginning at **result**.

**example**

```c++
#include <iostream>
#include <algorithm>
#include <vector>

int main () {
  int myints[]={10,20,30,40,50,60,70};
  std::vector<int> myvector (7);

  std::copy ( myints, myints+7, myvector.begin() );

  std::cout << "myvector contains:";
  for (std::vector<int>::iterator it = myvector.begin(); it!=myvector.end(); ++it)
    std::cout << ' ' << *it;

  std::cout << '\n';

  return 0;
}
```

### `copy_if`
`template <class InputIterator, class OutputIterator, class UnaryPredicate>  OutputIterator copy_if (InputIterator first, InputIterator last, OutputIterator result, UnaryPredicate pred);`

**Copy certain elements of range**
* Copies the elements in the range `[first,last)` for which **pred** returns true to the range beginning at **result**.

```c++
#include <iostream>
#include <algorithm>
#include <vector>

int main () {
  std::vector<int> foo = {25,15,5,-5,-15};
  std::vector<int> bar (foo.size());

  // copy only positive numbers:
  auto it = std::copy_if (foo.begin(), foo.end(), bar.begin(), [](int i){return !(i<0);} );
  bar.resize(std::distance(bar.begin(),it));  // shrink container to new size

  std::cout << "bar contains:";
  for (int& x: bar) 
    std::cout << ' ' << x;
  std::cout << '\n';

  return 0;
}
```