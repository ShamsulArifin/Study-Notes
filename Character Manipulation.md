- Check if [[character]] is alphanumeric
- Check if [[character]] is alphabetic
- Check if [[character]] is blank
- Check if [[character]] is lowercase or uppercase
- Check if [[character]] is digit
- Turning a [[character]] to lowercase/uppercase using the 
		std::tolower() and std::toupper functions


``` c++
  //* Check if character is alphanumeric
  std::cout << std::endl;
  std::cout << "std::isalnum: " << std::endl;
  std::cout << "C is alphanumeric: " << std::isalnum('C') << std::endl;
  std::cout << "^ is alphanumeric: " << std::isalnum('^') << std::endl;
  
  //* Can use this as a test condition
  char inputChar{'*'};
  if (std::isalnum(inputChar))
  {
    std::cout << inputChar << " is alphanumeric." << std::endl;
  }
  else
  {
    std::cout << inputChar << " is not alphanumeric." << std::endl;
  }
  
  //* Check if character is alphabetic
  std::cout << std::endl;
  std::cout << "std::isalpha: " << std::endl;
  std::cout << "C is alphabetic: " << std::isalpha('C') << std::endl;
  std::cout << "^ is alphabetic: " << std::isalpha('^') << std::endl;
  std::cout << "7 is alphabetic: " << std::isalpha('7') << std::endl;
  
  if(std::isalpha('e')){
    std::cout << 'e' << " is alphabetic" << std::endl;
  }else {
    std::cout << 'e' << " is NOT alphabetic" << std::endl;
  }
  
  //* check if character is blank
  std::cout << std::endl;
  std::cout << "std::isblank:" << std::endl;
  char message[]{"Hello there. How are you doing? The sun is shining."};
  std::cout << "message: " << message << std::endl;

  //* Find blank print blank index
  size_t blankCount{};
  for (size_t i{0}; i < std::size(message); ++i)
  {
    // std::cout << "Value: " << message[i] << std::endl;
    if (std::isblank(message[i]))
    {
      std::cout << "Blank found at index: [" << i << "]" << std::endl;
      ++blankCount;
    }
  }
  std::cout << "In total we found " << blankCount << " blank characters." << std::endl;
  
  //* check if character is lowercase or uppercase
  std::cout << "std::islower and std::isupper : " << std::endl;
  std::cout << std::endl;
  char thought[]{"The C++ Programming Language is one of the most used on the Planet"};
  int countLowercase{}, countUppercase{};

  //* print original string for ease of comparison on the terminal
  std::cout << "Original string: " << thought << std::endl;
  for (auto character : thought)
  {
    if (std::islower(character))
    {
      std::cout << " " << character;
      ++countLowercase;
    }
    if (std::isupper(character))
    {
      ++countUppercase;
    }
  }

  std::cout << std::endl;
  std::cout << "Found " << countLowercase << " lowercase characters and "
            << countUppercase << " uppercase characters." << std::endl;
  
  //* check if character is a digit
  std::cout << std::endl;
  std::cout << "std::isdigit: " << std::endl;
  
  char statement[] {"Mr Hamilton owns 221 cows. THat's a lot of cows! The kid exclaimed."};
  std::cout << "statement: " << statement << std::endl;

  int digitCount{};
  for(auto character: statement){
    if(std::isdigit(character)){
      std::cout << "Found digit: " << character << std::endl;
      ++digitCount;
    }
  }
  std::cout << "Found " << digitCount << " digits in the statement string" << std::endl;
  
  //* turning character to lowercase using the std::tolower() function
  std::cout << std::endl;
  std::cout << "std::tolower and std::toupper: " << std::endl;
  char originalStr[] {"Home. The feeling of belonging"};
  char destStr[std::size(originalStr)];

  //* turn this to uppercase. change the array in place
  for(size_t i {}; i < std::size(originalStr); ++i){
    destStr[i] = std::toupper(originalStr[i]);
  }
  
  std::cout << "Original string: " << originalStr << std::endl;
  std::cout << "Uppercase string: " << destStr << std::endl;

  //* turn this to lowercase. change the array in place
  for(size_t i {}; i < std::size(originalStr); ++i){
    destStr[i] = std::tolower(originalStr[i]);
  }
  std::cout << "Lowercase string: " << destStr << std::endl;
```
