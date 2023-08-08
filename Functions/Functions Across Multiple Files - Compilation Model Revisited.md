Function can be declared in the main file like this

``` c++
#include <iostream>

//* Declaration
int max(int a, int b);

int main()
{
  int maximum = max(34, 54);
  std::cout << "Maximum: " << maximum << std::endl;
  return 0;
}

//* Definition
int max(int a, int b)
{
  if (a > b)
    return a;
  else
    return b;
}
```

or we can split the function across multiple files by moving the declaration in a header file and the definition into a separate corresponding cpp file.

**compare.h**

``` c++
//* Declaration
int max(int a, int b);
int min(int a, int b);
```

**compare.cpp**

``` c++
//* Definition
int max(int a, int b)
{
  if (a > b)
    return a;
  else
    return b;
}

int min(int a, int b)
{
  if (a < b)
    return a;
  else
    return b;
}
```

After that we have to declare the function header file so that we can use the function

``` c++
#include <iostream>
#include "compare.h"

int main()
{
  int maximum = max(34, 54);
  int minimum = min(65, 34);

  std::cout << "Maximum: "
            << maximum << std::endl;
  std::cout << "Minimum: "
            << minimum << std::endl;

  return 0;
}
```

using functions this way makes the main file much more cleaner and increases it's readability

![[Compilation Model.canvas|Compilation Model]]