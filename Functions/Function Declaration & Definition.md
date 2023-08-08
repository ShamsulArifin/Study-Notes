this will work without errors

``` c++
#include <iostream>

int max(int a, int b)
{
  if (a > b)
    return a;
  else
    return b;
}

int main()
{
  int x{5};
  int y{12};

  int result = max(x, y);
  std::cout << "The maximum of the two numbers is: " << result << std::endl;

  return 0;
}
```

separating declaration and definition into two parts

``` c++
#include <iostream>

int max(int a, int b); //* function declaration, prototype
                       //* signature doesn't include return type
int min(int a, int b);

int main()
{
  int x{5};
  int y{12};

  int result = max(x, y);
  std::cout << "The maximum of the two numbers is: " << result << std::endl;

  return 0;
}

  

//? function definition shows up after main
int max(int a, int b)
{
  if (a > b)
    return a;
  else
    return b;
}
```

Full code

``` c++
#include <iostream>

int max(int a, int b); //* function declaration, prototype
                       //* signature doesn't include return type
int min(int a, int b);
int incMult(int a, int b);

int main()
{
  int x{5};
  int y{12};

  int result = max(x, y);
  std::cout << "The maximum of the two numbers is: "
            << result << std::endl;

  result = min(x, y);
  std::cout << "The minimum of the two numbers is: "
            << result << std::endl;

  result = incMult(x, y);
  std::cout << "incMult is: "
            << result << std::endl;

  return 0;
}

  

//? function definition shows up after main
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

  

int incMult(int a, int b)
{
  return ((++a) * (++b));
}
```