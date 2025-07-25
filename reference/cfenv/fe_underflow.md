# FE_UNDERFLOW
* cfenv[meta header]
* macro[meta id-type]
* cpp11[meta cpp]

```cpp
#define FE_UNDERFLOW integer-constant-expression
// または
#undef FE_UNDERFLOW
```
* integer-constant-expression[italic]

## 概要
浮動小数点数の演算でアンダーフローが発生したことを表す浮動小数点例外の種類。

処理系がこの浮動小数点例外に対応している場合にこのマクロが定義される。
マクロが定義されるとき、このマクロは浮動小数点例外の状態を表すビット値である。他の浮動小数点例外マクロとAND (`&`) や OR (`|`)を使用して、複数のマクロを組み合わせて使用できる。

## 例
```cpp example
#include <iostream>
#include <cfenv>

int main()
{
  float x = 1e-30f;
  float y = x * x;

  if (std::fetestexcept(FE_UNDERFLOW)) {
    std::cout << "raised underflow" << std::endl;
  }
  else {
    std::cout << "no error" << std::endl;
  }
}
```
* FE_UNDERFLOW[color ff0000]
* std::fetestexcept[link fetestexcept.md]

### 出力例
```
raised underflow
```

## バージョン
### 言語
- C++11

### 処理系
- [Clang](/implementation.md#clang): 3.0 [mark verified]
- [GCC](/implementation.md#gcc): 4.3.0 [mark verified]
- [ICC](/implementation.md#icc): ??
- [Visual C++](/implementation.md#visual_cpp): 2013 [mark verified], 2015 [mark verified]
	- コンパイルオプション`/fp:strict`または`#pragma fenv_access (on)`が必要。さもなくば、正しく動作しないおそれがある。
