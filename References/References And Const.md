Non const [[reference]]

```c++
  //* Non const reference

  std::cout << std::endl;

  std::cout << "Non const reference: " << std::endl;

  int age{27};

  int &refAge{age};

  /*

    std::cout << "age: " << age << std::endl;
    std::cout << "refAge: " << refAge << std::endl;

    //* can modify original variable through reference
    std::cout << std::endl;
    std::cout << "Modify original variable through reference: " << std::endl;
    refAge++; //* modify through reference
    std::cout << "Age: " << age << std::endl;
    std::cout << "refAge: " << refAge << std::endl;

  */

  //* simulating reference behaviour with pointer
  //! compiler error
  // const int *const pAge {&age};
  // *pAge = 45;
```