This is a specially-made compiler that takes in "code" from a made-up, java-like language 
and consequently generates/executes real java code to reflect the semantics of the input "code".

This process is achieved through 4 main steps:

1. Tokenizing - Achieved using a deterministic finite automation tree.

2. Parsing - Using an LL(1) recursive descent parser, an abstract syntax tree is generated.

3. Type Checking - By creating an AST visitor class, the visit/accept method is used to denote AST nodes with a type, a 'coerce' type (for implied type casting) and finally ensure the type of each node is legal.

4. Code Generation - Using the legal AST, another AST visitor class is implemented to generate actual java code, which is then compiled.