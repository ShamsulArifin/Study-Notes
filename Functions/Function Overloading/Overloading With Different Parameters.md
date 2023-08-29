``` c++
#include <iostream>

// int max(int a, int b)
// {
//   std::cout << "int overload called" << std::endl;
//   return (a > b) ? a : b;
// }

double max(double a, double b)
{
  std::cout << "double overload called" << std::endl;
  return (a > b) ? a : b;
}

  

double max(int a, double b)
{
  std::cout << "(int,double) overload called" << std::endl;
  return (a > b) ? a : b;
}

  

double max(double a, int b)
{
  std::cout << "(double, int) overload called" << std::endl;
  return (a > b) ? a : b;
}

  

double max(double a, int b, int c)
{
  std::cout << "(double, int, int) overload called" << std::endl;
  return a;
}

  

std::string_view max(std::string_view a, std::string_view b)
{
  std::cout << "string_view overload called" << std::endl;
  return (a > b) ? a : b;
}

  

int main()
{
  int x{4}, y{9};
  double a{35.8}, b{8.98};

  auto result = max(a, b);
  result = max(x, b);
  result = max(a, y);
  result = max(b, x, y);

  // result = max(a, b);
  max("Hello", "World");

  return 0;
}
```