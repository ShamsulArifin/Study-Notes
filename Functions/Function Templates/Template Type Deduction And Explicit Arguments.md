``` c++
#include <iostream>
#include <string>

template <typename T>
T maximum(T a, T b)
{
  return (a > b) ? a : b;
}

int main()
{
  int a{10}, b{23};
  double c{23.4}, d{43.5};
  std::string e{"Hello"}, f{"world"};


  //? Explicit template arguments

  auto max = maximum<double>(a, d);
  std::cout << "Max: " << max << std::endl;

  return 0;
}
```
