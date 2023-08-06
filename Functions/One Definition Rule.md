Definitions can't show up more than once in entire program, or [[Translation units]].

**One Definition rule: context**
- Free standing variables
- Functions
- Classes
- Class member functions
- Class static member variables

``` c++
//* variable : declaration and definition
double weight{};

//! cant define same variable again
//! will cause compile error
// double weight{};


double add(double a, double b);

int main()

{
  double result = add(10, 30);
  std::cout << "result: " << result << std::endl;

  return 0;
}

double add(double a, double b)
{
  return a + b;
}

  

//! cant define same function again
//! will cause compile error
// double add(double a, double b)
// {
//   return a + b;
// }
```