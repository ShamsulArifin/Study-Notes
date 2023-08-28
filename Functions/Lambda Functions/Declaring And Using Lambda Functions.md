``` c++
#include <iostream>

int main()
{
  //* Lambda function signature : [capture list](parameters) -> return type
  //* {
  //*   function body
  //* }

  //* declaring lambda function
  auto func = []()
  {
    std::cout << "Hello World" << std::endl;
  };

  func();

  //* declaring lambda function and call it directly
  []()
  { std::cout << "Hello World" << std::endl; }();

  //* lambda function that takes parameters
  [](double a, double b)
  { std::cout << "a + b: " << (a + b) << std::endl; }(10.6, 4.8);

  auto func1 = [](double a, double b)
  {
    std::cout << "a + b: " << (a + b) << std::endl;
  };

  func1(10.5, 8.9);
  func1(5.87, 4.99);

  //* lambda function that returns something
  auto result = [](double a, double b)
  {
    return (a + b);
  }(10, 20);

  std::cout << "result: " << result << std::endl;
  std::cout << "result: " <<
      [](double a, double b)
  {
    return (a + b);
  }(10, 70)
            << std::endl;

  auto func1 = [](double a, double b)
  {
    return a + b;
  };

  // auto result1 = func1(23, 7);
  // auto result2 = func1(9, 45);


  // std::cout << "resul1: " << result1 << std::endl;
  // std::cout << "result2: " << result2 << std::endl;

  //* explicitly specify the return type
  auto func3 = [](double a, double b) -> int
  {
    return a + b;
  };

  auto func4 = [](double a, double b)
  {
    return a + b;
  };

  double a{6.768}, b{3.654};

  auto result3 = func3(a, b);
  auto result4 = func4(a, b);


  std::cout << "result3: " << result3 << std::endl;
  std::cout << "result4: " << result4 << std::endl;
  std::cout << "sizeof(result3): " << sizeof(result3) << std::endl;  //* 4
  std::cout << "sizeof(result4): " << sizeof(result4) << std::endl;  //* 8

  std::cout << "Done!" << std::endl;

  return 0;
}
```