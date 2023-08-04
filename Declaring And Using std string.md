``` c++
  std::string fullName;                               //* empty string
  std::string planet{"Earth. Where the sky is blue"}; //* Initialize with string literal
  std::string preferredPlanet{planet};                //* Initialize with other existing string
  std::string message{"Hello there", 5};              //* Initialize with part of a string literal
  std::string weirdMessage(4, 'e');                   //* Initialize with multiple copies of a character
  std::string greeting{"Hello World"};
  std::string sayingHello{greeting, 6, 5}; //* Initialize with part of an existing string

  std::cout << "fullName: " << fullName << std::endl;
  std::cout << "planet: " << planet << std::endl;
  std::cout << "preferredPlanet: " << preferredPlanet << std::endl;
  std::cout << "message: " << message << std::endl;
  std::cout << "weirdMessage: " << weirdMessage << std::endl;
  std::cout << "greeting: " << greeting << std::endl;
  std::cout << "sayingHello: " << sayingHello << std::endl;
  
  //* changing std::string at runtime
  planet = "Earth is a polluted planet";
  std::cout << "planet: " << planet << std::endl;
  
  //* use a raw array
  const char * planet1 {"Earth , where the land is polluted and the sky is cloudless"};
  std::cout << "planet1: " << planet1 << std::endl;
```