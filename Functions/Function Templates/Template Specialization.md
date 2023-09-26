``` c++
#include <iostream>
#include <cstring>

//? Function template
template <typename T>
T maximum(T a, T b)
{
  return (a > b) ? a : b; // Return the larger of two values.
}

  

//? Template Specialization
template <>
const char *maximum<const char *>(const char *a, const char *b)
{
  return strcmp(a, b) > 0 ? a : b; /// Compare strings and returns pointer to the one with greater value.
}

  

int main()
{
  int a{10}, b{23};
  double c{34.7}, d{32.4};
  std::string e{"hello"}, f{"world"};

  

  auto max_int = maximum(a, b);    //? int type deduced
  auto max_double = maximum(c, d); //? double type deduced
  auto max_str = maximum(e, f);    //? string type deduced

  std::cout << "max_int: " << max_int << std::endl;
  std::cout << "max_double: " << max_double << std::endl;
  std::cout << "max_str: " << max_str << std::endl;

  

  const char *g{"wild"};
  const char *h{"animal"};

  

  //! This won't do as expected if used by first template
  const char *result = maximum(g, h);
  std::cout << "max(const char*): " << maximum(g, h) << std::endl;

  return 0;
}
```