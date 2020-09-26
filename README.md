## Sequensa

Read more about Sequensa programming language [here](http://darktree.net/projects/sequensa/)  
Learn how to compile/install Sequensa [here](./COMPILE.md)  
This repository contains:

 * __Sequensa API__  - single file embeddable C++ Sequensa API
 * __Sequensa Standard Libraries__  - shared libraries injected into Sequensa at runtime
 * __Sequensa__  - application used to compile and run Sequensa programs

##### Sequensa API

The API itself is located in `/src/api/SeqAPI.hpp` and contains basic documentation to get you started

```C++
#define SEQ_IMPLEMENT
#include "SeqAPI.hpp"

int main() {

	seq::string code = "#exit << \"Hello World!\""_b;
	
	auto buffer = seq::Compiler::compile( code );
	seq::ByteBuffer bb( buffer.data(), buffer.size() );

	seq::Executor exe;
	exe.execute( bb );
	
	std::cout << exe.getResultString();
	
}
```