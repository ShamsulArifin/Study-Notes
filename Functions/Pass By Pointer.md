pass value to the function using [[pointer]]  and inside the function use the value or the pointer by [[dereference]]ing it.

``` c++
#include <iostream>

void sayAge(int *age); //* declaration

int main()
{
  int age{23}; //* local to main function

  std::cout << "age (before call): "
            << age << " &age: " << &age << std::endl;

  sayAge(&age); //? argument

  std::cout << "age (after call): "
            << age << " &age: " << &age << std::endl;

  return 0;

}

void sayAge(int *age) //* parameter
{
  ++(*age);
  std::cout << "My age is: " << *age
            << " &age: " << &age << std::endl;
}
```