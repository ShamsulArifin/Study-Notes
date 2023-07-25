```c++

  int intData{33};
  double doubleData{55};

  //* references
  int &refIntData{intData};
  double &refDoubleData{doubleData};

  //* print data to terminal
  std::cout << "intData: " << intData << std::endl;
  std::cout << "&intData: " << &intData << std::endl;
  std::cout << "doubleData: " << doubleData << std::endl;
  std::cout << "&doubleData: " << &doubleData << std::endl;
```