This is a specially-made compiler that takes in "code" from a made-up, java-like language 
and consequently generates/executes real java code to reflect the semantics of the input "code".

This process is achieved through 4 main steps:
==============================================

1. Tokenizing - Achieved using a deterministic finite automation tree.

2. Parsing - Using an LL(1) recursive descent parser, an abstract syntax tree is generated.

3. Type Checking - By creating an AST visitor class, the visit/accept method is used to denote AST nodes with a type, a 'coerce' type (for implied type casting) and finally ensure the type of each node is legal.

4. Code Generation - Using the legal AST, another AST visitor class is implemented to generate actual java code, which is then compiled.

To use this compiler, complete the following steps:
---------------------------------------------------

1. Download the zipped folder from this repository and 'Extract all' to the local folder of your choice. 

2. In this folder of your choice, place a '.txt' file with ONLY the PicLang "code" to be converted and compiled (should be in same directory folder as 'edu').

3. Navigate to the folder from extraction in the command line. Run the following 

```
javac edu/ufl/cise/plc/*.java edu/ufl/cise/plc/runtime/*.java edu/ufl/cise/plc/ast/*.java

java edu/ufl/cise/plc/run.java
```

Additional Notes
----------------

**PicLangGrammar.txt** denotes the grammar for this language. Unfortunately, for the purposes of portability, I was not able to set up function arguments. All variables must be initialized within the function by either a literal or a read ('<-') from console. (Enter an image by passing web URL. Enter a color by passing a space separated list of 3 integers (0-255).


An example piece of code and its output can be seen below:

```
void testImagetoFile()
	int size = 500;
	image[size,size] f;
	f[x,y] = <<x,x,x>>%<<256,256,256>> + <<y,y,y>>%<<256,256,256>>;
   	write f -> console;
```

![image](https://user-images.githubusercontent.com/68303855/166309068-90677f7e-264b-4d6d-aeec-30df23c2a9a2.png)
