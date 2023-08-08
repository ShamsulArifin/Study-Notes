``` c++
#include <iostream>

void sayAge(int age) //? parameter
{
  ++age; //* local to sayAge function

  std::cout << "My Age is: " << age
            << " &age: " << &age << std::endl;
}

int main()
{
  int age{23}; //* local to main function

  std::cout << "age (before call): "
            << age << " &age: " << &age << std::endl;

  sayAge(age); //? argument
  
  std::cout << "age (after call): "
            << age << " &age: " << &age << std::endl;

  return 0;
}
```