``` c++
#include <iostream>

template <typename T>
T maximum(T a, T b)
{
  return (a > b) ? a : b;
}

int main()
{
  int x{5}, y{7};

  // std::string x{"Hello"}, y{"Python"};

  int *p_x{&x}, *p_y{&y};

  auto result = maximum(x, y);

  std::cout << "max: " << result << std::endl;

  return 0;
}
```

**Summary**

- [[Function Templates]] are just blueprints, they are not real [[Function Declaration & Definition|function declaration and definition]].
- Real function declarations and definitions, aka template instances are created when you call the function with arguments
- If the template parameters are of the same type `(T, T)`, then the arguments you call the function with much also match, otherwise you get a [[Compiler|compiler]] error.
- Template instances won't always do what you want. A good example is when you call our maximum function with [[pointer|pointers]].
- There are tools like [cppinsights.io](https://cppinsights.io) that can show you template instantiations. You can even use debugger to infer that information from the activation record of  a template function.
- The arguments passed to a function template must support the operations that are done in the body of the function.