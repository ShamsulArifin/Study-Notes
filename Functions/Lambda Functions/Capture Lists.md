``` c++
#include <iostream>

int main()
{
  //* capture lists
  double a{10};
  double b{20};

  // auto func = [a, b]()
  // {
  //   std::cout << "a + b: " << a + b << std::endl;
  // };

  // func();

  //* capture by value
  // int c{42};

  // auto func = [c]()
  // {
  //   std::cout << "Inner value: " << c
  //             << "&inner: " << &c << std::endl;
  // };

  // for (size_t i{}; i < 5; ++i)
  // {
  //   std::cout << "Outer value: " << c
  //             << "&outer: " << &c << std::endl;
  //   func();
  //   ++c;
  // }

  

  //* capture by reference
  int c{42};

  auto func = [&c]()
  {
    std::cout << "Inner value: " << c
              << " &inner: " << &c << std::endl;
  };

  

  for (size_t i{}; i < 5; ++i)
  {
    std::cout << "Outer value: " << c
              << " &outer: " << &c << std::endl;
    func();
    ++c;
  }

  return 0;
}
```