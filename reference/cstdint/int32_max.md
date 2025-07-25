# INT32_MAX
* cstdint[meta header]
* macro[meta id-type]
* cpp11[meta cpp]

```cpp
#define INT32_MAX implementation-defined
```

## 概要
[`int32_t`](int32_t.md) の最大値を表す定数。

ビット数32をNとして、このマクロの値は2<sup>N-1</sup> - 1である2147483647となる。

その値の型は、[`int32_t`](int32_t.md)を整数昇格したものとなる。

なお、このマクロは [`int32_t`](int32_t.md) が定義されていない場合には定義されない。

## 例
```cpp example
#include <iostream>
#include <cstdint>

int main()
{
  std::cout << INT32_MAX << std::endl;
}
```
* INT32_MAX[color ff0000]

### 出力
```
2147483647
```


## バージョン
### 言語
- C++11

### 処理系
- [Clang](/implementation.md#clang): 3.2 [mark verified]
- [GCC](/implementation.md#gcc): 4.4 [mark verified]
- [ICC](/implementation.md#icc): ??
- [Visual C++](/implementation.md#visual_cpp): 2010 [mark verified], 2012 [mark verified], 2013 [mark verified], 2015 [mark verified]
