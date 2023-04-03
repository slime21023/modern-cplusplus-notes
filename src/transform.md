# transform
* `template <class InputIterator, class OutputIterator, class UnaryOperation> OutputIterator transform (InputIterator first1, InputIterator last1, OutputIterator result, UnaryOperation op);`
* `template <class InputIterator1, class InputIterator2, class OutputIterator, class BinaryOperation> OutputIterator transform (InputIterator1 first1, InputIterator1 last1, InputIterator2 first2, OutputIterator result, BinaryOperation binary_op);`

**Transform range**
* Applies an operation sequentially to the elements of one or two ranges and stores the result in the range that begins at **result**.

**Example**

```c++
#include <iostream>
#include <algorithm>
#include <vector>
#include <functional>

int op_increase (int i) { return ++i; }

int main () {
  std::vector<int> foo;
  std::vector<int> bar;

  // set some values:
  for (int i=1; i<6; i++)
    foo.push_back (i*10);                         // foo: 10 20 30 40 50

  bar.resize(foo.size());                         // allocate space

  std::transform (foo.begin(), foo.end(), bar.begin(), op_increase);
                                                  // bar: 11 21 31 41 51

  // std::plus adds together its two arguments:
  std::transform (foo.begin(), foo.end(), bar.begin(), foo.begin(), std::plus<int>());
                                                  // foo: 21 41 61 81 101

  std::cout << "foo contains:";
  for (std::vector<int>::iterator it=foo.begin(); it!=foo.end(); ++it)
    std::cout << ' ' << *it;
  std::cout << '\n';

  return 0;
}
```