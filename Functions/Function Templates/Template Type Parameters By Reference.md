``` c++
#include <iostream>

template <typename T>
const T &maximum(const T &a, const T &b); //? Declaration

// template <typename T>
// T maximum(T a, T b); //? Declaration

int main()
{
  double a{23.5}, b{42.5};
  
  std::cout << "Out - &a: " << &a << std::endl;
  auto result = maximum(a, b);
  std::cout << "Out - &a: " << &a << std::endl;

  return 0;

}

//? Definition
template <typename T>
const T &maximum(const T &a, const T &b)
{
  // ++a; //! will cause  compiler error
  
  std::cout << "In - &a: " << &a << std::endl;
  return (a > b) ? a : b;
}

  

//! Doing this will confuse  the compiler

// template <typename T>
// T maximum(T a, T b)
// {
//   std::cout << "In - &a: " << &a << std::endl;
//   return (a > b) ? a : b;
// }
```