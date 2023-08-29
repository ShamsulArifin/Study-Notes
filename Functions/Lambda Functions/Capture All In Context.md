``` c++
#include <iostream>

int main()
{
  //* capture all by value
  int c{42};

  auto func = [=]()
  {
    std::cout << "Inner value: " << c << std::endl;
  };

  for (size_t i{}; i < 5; ++i)
  {
    std::cout << "Outer value: " << c << std::endl;
    func();
    ++c;
  }

  //* capture all by reference
  int c{42};
  int d{65};

  auto func = [&]()
  {
    std::cout << "Inner value(c): " << c << std::endl;
    std::cout << "Inner value(d): " << d << std::endl;
  };

  for (size_t i{}; i < 5; ++i)
  {
    std::cout << "Outer value(c): " << c << std::endl;
    std::cout << "Outer value(d): " << d << std::endl;
    func();
    ++c;
  }

  return 0;
}
```
