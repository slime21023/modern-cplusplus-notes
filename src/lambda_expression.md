# lambda_expression

lambda expression 是用來產生**匿名(Anonymous)**函數物件的表示式

`[] (params) -> return {body}`

- `=`: Defualt capture by value
- `&`: Default capture by reference

### Syntax
- `[]`: **lambda-introducer (capture clause)**
  - `[]`: 不傳遞外部變數
  - `[=]`: 所有的外部變數以傳值(by value)的方式傳遞
  - `[&]`: 所有的外部變數以參考(by reference)的方式傳遞
  - `[x, &y]`: 變數x傳值，變數y傳參考
  - `[=, &y]`: 除了變數y傳參考，其餘變數用傳值的方式傳遞

- `(params)`: **lambda declarator (parameter list)**
  - 不可指定參數的預設值
  - 不可使用可變長度的參數列表
  - 參數列表不可以包含沒有命名的參數

- `throw()`：**例外狀況規格（exception specification）**

- `-> int`：**傳回值型別（return type）**
  
### Example
```c++
#include <iostream>
using namespace std;
int main() {
  auto greeting = []() { cout << "Hello, Lambda" << endl; };
  greeting();
}
```