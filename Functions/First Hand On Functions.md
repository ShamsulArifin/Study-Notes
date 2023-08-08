``` c++
//* function that takes a single parameter, and doesn't
//* give back the result explicitly

void enterBar(size_t age) //? function parameters
{
  if (age > 18)
  {
    std::cout << "You are " << age << ", old enough to drink" << std::endl;
  }
  else
  {
    std::cout << "Sorry you aren't old enough yet." << std::endl;
  }
  return;
}

//* function that takes multiple parameters and returns the result of the computation
int max(int a, int b)
{
  if (a > b)
  {
    return a;
  }
  else
  {
    return b;
  }
}

  

//! functions with same signature will cause errors
// void max(int a, int b)
// {
//   if (a > b)
//   {
//     return a;
//   }
//   else
//   {
//     return b;
//   }
// }

  

//* function that doesn't take parameters and returns nothing
void sayHello()
{
  std::cout << "Hello there" << std::endl;
  return; //? you could omit this return statement for functions returning void
}

  

//* function that takes no parameters and return something
int luckyNumber()
{
  return 99;
}

  

//* changes to function are not visible outside the function. what we
//* have inside the function are COPIES of the arguments
//* passed to the function
double incrementMultiply(double a, double b)
{
  std::cout << "Inside function, before increment: " << std::endl;
  std::cout << "a: " << a << std::endl;
  std::cout << "b: " << b << std::endl;

  double result = ((++a) * (++b));

  

  std::cout << "Inside function, after increment: " << std::endl;
  std::cout << "a: " << a << std::endl;
  std::cout << "b: " << b << std::endl;

  return result;
}

  

int main()

{

  enterBar(22); //? function arguments
  // enterBar(15);
  // enterBar(8);

  // for (size_t i{1}; i < 20; ++i)
  // {
  //   enterBar(i);
  // }

  int x{22}, y{44};

  int result = max(10, 20); //? passing arguments
  result = max(x, y);

  

  std::cout << "max: " << result << std::endl;

  //* calling sayHello
  sayHello();

  

  //* calling luckyNumber
  result = luckyNumber();
  std::cout << "lucky number is : " << result << std::endl;

  double h{3.00}, i{4.00};

  

  std::cout << "Outside function, before increment: " << std::endl;
  std::cout << "h: " << h << std::endl;
  std::cout << "i: " << i << std::endl;

  

  double incrMultResult = incrementMultiply(h, i);

  std::cout << "Outside function, after increment: " << std::endl;
  std::cout << "h: " << h << std::endl;
  std::cout << "i: " << i << std::endl;

  return 0;

}
```