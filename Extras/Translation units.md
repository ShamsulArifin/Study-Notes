According to [standard C++](http://www.efnetcpp.org/wiki/ISO/IEC_14882) ([wayback machine link](http://web.archive.org/web/20070403232333/http://www.efnetcpp.org/wiki/ISO/IEC_14882)) : A translation unit is the basic unit of compilation in C++. It consists of the contents of a single source file, plus the contents of any header files directly or indirectly included by it, minus those lines that were ignored using conditional preprocessing statements.

A single translation unit can be compiled into an object file, library, or executable program.

The notion of a translation unit is most often mentioned in the contexts of the One Definition Rule, and templates.