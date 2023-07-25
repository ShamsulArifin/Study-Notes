
Reference | Pointers
------------ | ------------
Don't use [[dereferencing]] for reading and writing | Must go through dereferencing operator to read/write through pointed value
Can't be changed to reference something else | Can be changed to point somewhere else
Must be initialized at declaration | Can be declared un-initialized (will contain [[Garbage Addresses]])

```c++
  //* declare pointer and reference

  double doubleValue{12.34};
  //!reference must always be initialized at declaration
  double &refDoubleValue{doubleValue}; //* Reference to doubleValue
  double *pDoubleValue{&doubleValue};  //* Pointer to doubleValue
  
  //*Reading data
  std::cout << "doubleValue: " << doubleValue << std::endl;
  std::cout << "refDoubleValue: " << refDoubleValue << std::endl;
  std::cout << "pDoubleValue: " << pDoubleValue << std::endl;
  std::cout << "*pDoubleValue: " << *pDoubleValue << std::endl;

  //*writing through pointer
  *pDoubleValue = 15.44;
  
  std::cout << std::endl;
  std::cout << "doubleValue: " << doubleValue << std::endl;
  std::cout << "refDoubleValue: " << refDoubleValue << std::endl;
  std::cout << "pDoubleValue: " << pDoubleValue << std::endl;
  std::cout << "*pDoubleValue: " << *pDoubleValue << std::endl;

  //*writing through reference
  refDoubleValue = 18.44;

  std::cout << std::endl;
  std::cout << "doubleValue: " << doubleValue << std::endl;
  std::cout << "refDoubleValue: " << refDoubleValue << std::endl;
  std::cout << "pDoubleValue: " << pDoubleValue << std::endl;
  std::cout << "*pDoubleValue: " << *pDoubleValue << std::endl;
  
  double someOtherDouble{78.45};
  
  //? you cant make reference refer something else once it initialized
  refDoubleValue = someOtherDouble;//! this will not make the reference refer something   else
  //! this would only assign the value to the address the reference is referring to
  
  std::cout << "Making the reference refer something else...." << std::endl;
  std::cout << std::endl;
  std::cout << "doubleValue: " << doubleValue << std::endl;
  std::cout << "refDoubleValue: " << refDoubleValue << std::endl;
  std::cout << "pDoubleValue: " << pDoubleValue << std::endl;
  std::cout << "*pDoubleValue: " << *pDoubleValue << std::endl;
  
  //* make the pointer point something else

  pDoubleValue = &someOtherDouble;
  
  std::cout << "Making the reference refer something else...." << std::endl;
  std::cout << std::endl
  std::cout << "doubleValue: " << doubleValue << std::endl;
  std::cout << "refDoubleValue: " << refDoubleValue << std::endl;
  std::cout << "&doubleValue: " << &doubleValue << std::endl;
  std::cout << "&refDoubleValue: " << &refDoubleValue <<std::endl;
  std::cout << "pDoubleValue: " << pDoubleValue << std::endl;
  std::cout << "*pDoubleValue: " << *pDoubleValue << std::endl;

  *pDoubleValue = 555.5;
  
  std::cout << std::endl;
  std::cout << "doubleValue: " << doubleValue << std::endl;
  std::cout << "refDoubleValue: " << refDoubleValue << std::endl;
  std::cout << "&doubleValue: " << &doubleValue << std::endl;
  std::cout << "&refDoubleValue: " << &refDoubleValue <<std::endl;
  std::cout << "pDoubleValue: " << pDoubleValue << std::endl;
  std::cout << "*pDoubleValue: " << *pDoubleValue << std::endl;
```

