- Resource Acquisition is Initialization
- Binds the life cycle of a **resource** that must be acquired before use to the **lifetime of an object**
- Makes life easier by implementing things in a way that **automatically manages memory**/resources within an object

RAII Implementation
- **Encapsulate** each resources into a class
- The class constructor **acquires** the resource and initializes it accordingly
- The destructor **releases** the resource
- The class itself should be instantiated such that it has either automatic storage duration, or in another RAII object

``` c++
class IntArray
{
	int * array;
public:
	IntArray(size_t size) { array = new int[size]; }
	~IntArray() { delete [] array; }
	int & operator [] (size_t i) { return array[i]; }
	
}
```

``` c++
#include "IntArray.h"
int main()
{
	IntArray arr (10);  // mem allocated
	arr[5] = 21;
} // arr destructs, mem deallocated
```

