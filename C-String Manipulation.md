``` c++
  //* std::strlen : Find the length of a string
  //* real arrays and those decayed into pointers
  const char message1[] {"The sky is blue."};

  //* Array decays into pointer when we use const char*
  const char* message2 {"THe sky is blue."};
  std::cout << "message1: " << message1 << std::endl;

  //* strlen ignores null character
  std::cout << "strlen(message1): " << std::strlen(message1) << std::endl;

  //* includes the null character
  std::cout << "sizeof(message1): " << sizeof(message1) << std::endl;

  //* strlen still works with decayed arrays
  std::cout << "strlen(message2): " << std::strlen(message2) << std::endl;

  //* prints size of pointer
  std::cout << "sizeof(message2): " << sizeof(message2) << std::endl;
  
  //* std::strcmp - signature : int strcmp( const char *lhs, const char *rhs);
  //* returns negative value if lhs appears before rhs in lexicographical order,
  //* zero otherwise.
  //* ans positive value if lhs appears after rhs in lexicographical order.
  std::cout << std::endl;
  std::cout << "std::strcmp: " << std::endl;
  const char *stringData1{"Alabama"};
  const char *stringData2{"Blabama"};

  char stringData3[]{"Alabama"};
  char stringData4[]{"Blabama"};

  //* comparison
  std::cout << "std::strcmp (" << stringData1 << "," << stringData1 << ") : "
            << std::strcmp(stringData1, stringData2) << std::endl;

  std::cout << "std::strcmp (" << stringData3 << "," << stringData4 << ") : "
            << std::strcmp(stringData3, stringData4) << std::endl;
  
  stringData1 = "Alabama";
  stringData2 = "Alabamb";

  //! will cause compiler error
  // stringData3 = "Alabama";
  // stringData4 = "Alabamb";

  //* print comparison
  std::cout << "std::strcmp (" << stringData1 << "," << stringData2 << ") : "
            << std::strcmp(stringData1, stringData2) << std::endl;
            
  const char *stringData1{"Alabama"};
  const char *stringData2{"Blabama"};
  size_t n{3};

  std::cout << std::endl;
  std::cout << "std::strncmp : " << std::endl;
  std::cout << "std::strncmp (" << stringData1 << "," << stringData2 << "," << n << ") : "
            << std::strncmp(stringData1, stringData2, n) << std::endl;

  

  stringData1 = "aaaia";
  stringData2 = "aaance";

  std::cout << "std::strncmp (" << stringData1 << "," << stringData2 << "," << n << ") : "
            << std::strncmp(stringData1, stringData2, n) << std::endl;

  n = 5;

  std::cout << "std::strncmp (" << stringData1 << "," << stringData2 << "," << n << ") : "
            << std::strncmp(stringData1, stringData2, n) << std::endl;

  stringData1 = "aaaoa";
  stringData2 = "aaance";

    std::cout << "std::strncmp (" << stringData1 << "," << stringData2 << "," << n << ") : "
            << std::strncmp(stringData1, stringData2, n) << std::endl;
            
  std::cout << std::endl;
  std::cout << "std::strchr : " << std::endl;

  const char *str { "Try not. Do, or do not. There is no try." };
  char target = 'o';
  const char * result = str;
  size_t iterations{};

  while ((result = std::strchr(result, target)) != nullptr) {
    std::cout << "Found '" << target << "' starting at '" << result << "'\n";
    
    ++result;
    ++iterations;

  }
  std::cout << "iterations : " << iterations << std::endl;
  
  //! do not do this
  std::cout << std::endl;
  std::cout << "std::strchr : " << std::endl;  
  const char *str{"Try not. Do, or do not. There is no try."};
  char target = 'T';
  const char *result{nullptr};
  size_t iterations{};
  
  while ((result = std::strchr(str, target)) != nullptr)
  {
    std::cout << "Found '" << target << "' starting at '" << result << "'\n";  

    ++str;
    ++iterations;
  }

  std::cout << "iterations : " << iterations << std::endl;
  
  //* find last occurrences
  std::cout << std::endl;
  std::cout << "std::strrchr : " << std::endl;

  char input[] = "/home/user/hello.cpp";
  char *output = std::strrchr(input, '/');

  if (output)
    std::cout << output + 1 << std::endl;
```