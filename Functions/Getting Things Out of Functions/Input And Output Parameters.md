- [[output|Output]] parameters should be pass in such a way that you can modify the arguments from inside the [[Functions|function]]. Options are [[Pass By Reference|passing by reference]] or [[Pass By Pointer|by pointer]]. [[reference|References]] are preferred in c++.
- [[input|Input]] parameters shouldn't be modifiable from inside a [[Functions|function]]. The [[Functions|function]] really need to get [[input]] (read) from the arguments. You only enforce modification restrictions with the const keyword. Options are passing by const reference, passing by pointer to const or even const pointer to const.

**Passing by reference**

``` c++
#include <iostream>
#include <string>

void max_str(const std::string &input1, const std::string input2, std::string &output)
{
  if (input1 > input2)
  {
    output = input1;
  }
  else
  {
    output = input2;
  }
}

int main()
{
  std::string out_str, string1("Casablanca"), string2("Bellevue");

  max_str(string1, string2, out_str);
  std::cout << "The larger of the two strings is: "
            << out_str << std::endl;

  return 0;
}
```

**Passing by value**

``` c++
#include <iostream>
#include <string>

void max_int(int input1, int input2, int &output)
{
  if (input1 > input2)
  {
    output = input1;
  }
  else
  {
    output = input2;
  }
}

int main()
{
  int out_int;
  int in1{45}, in2{723};

  max_int(in1, in2, out_int);
  std::cout << "Max integer value: " << out_int << std::endl;

  return 0;
}
```

**Passing by pointer**

``` c++
#include <iostream>
#include <string> 

void max_double(double input1, double input2, double *output)
{
  if (input1 > input2)
  {
    *output = input1;
  }
  else
  {
    *output = input2;
  }
}

  

int main()
{

  double out_double, in_double1{45.8}, in_double2{6.9};

  max_double(in_double1, in_double2, &out_double);

  std::cout << "max_double: " << out_double << std::endl;

  return 0;
}
```