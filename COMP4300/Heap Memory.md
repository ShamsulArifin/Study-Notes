- Much more space available than stack\
- Allocation via the 'new' keyword
``` c++
Type * varName = new Type;
```
 - Calls C function malloc under the hood
 - Operating system find a  contiguous chunk of memory and returns a pointer to it
	 - This is very complicated and expensive
- You then access the memory via pointer