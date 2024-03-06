+++
title = "Go"
date = 2019-11-28
+++

* The Execution speed of Go is faster than interpreted languages(the languages that are not compiled) like JS,Python,Ruby,PHP.
* Compiled languages like Rust, Java, C, C++, C# the compilation speed of Go is faster that is it compiles the code faster. **But It does not necessarily true that the execution speed of Go is faster than the above compiled languages.**

 - **Untyped meaning the type is not typed or wrote for a data e.g `var a = 20 or const a = 20 or a:= 30 `
* factored import statement and variables declaration can also be done in factored manner
* packages - Go program is made up of packages.
* type of data is at last.
* Naked return.
* `:-` only be used in inside function.
* Type Conversion
* Type inference
  when type is not declared it will automatically assume the type based on the value it has been assigned.
* Go has only `for loop
* Defer
  defer statement get executed after the surrounding function is finished executing.
  Defer function calls are pushed into stacked and the function return in LIFO manner.
* Dereferencing or indirecting is where a pointer is changing the value of an variable by using pointer's underlying value(value of variable).
  ```go
   var p *int
   i:=41
   //pointer p generates a pointer to it's operand(i.e is 'i')
   p = &i
   fmt.Print(i)
   fmt.Print(p)
   //*p will point to the pointer's underlying value
   fmt.Print(*p)
   //changing the value of pointer's underlying value it will also change the value of 'i'
   *p = 21
   fmt.Print(i)
   fmt.Print(*p)

   ```
* Structs
  Collection of Fields or it's like a data type which uses different data types.
  * Struct Literals
    Struct literal denotes the a newly allocated struct values by listing the values of it's fields.
* Arrays
* Slices

#### values
Go has various data types including integer,strings,floats,booleans etc..

#### variables
Variables are declared explicitly and used by the compiler to e.g. check the type-correctness of function calls.

`var` can delcares 1 or more variables
Go will infer(Type inference meaning automatic detection of the (data type)type of an expression) the type of initialized variables.
Declared variables without initialization are zero-value. e.g for an int is 0. for floats is 0.0
`:=` is shorthand for declaring and initializing a variable. e.g var f string = "apple" ==> f:="apple"

#### Constant
value cannot be changed once it has been initialized
Constant expression perform arithmetic with arbitrary precision.
Numeric Constant has no type , until it's given one by explicit conversion
So it can be given a type by using it in a function that requires one type of data.
Such as in `math.Sin`it requires  `float64` data type so that's why we convert our `d` got converted into `float64` bcuz that's what `math.Sin` requires.

### What is Struct?
   - Struct is a collection of fields(data types) or collection of different data types.
### struct literals
   - The initializing the values of struct field implicitly is called struct literals.
   - Another meaning of literal is a constant value. but this is not the case here.
### slices
  - slices in Go are references to the arrays.
  - slices have length and capacit.
  - slice length is the no. of elements it contains not the noraml length in java and slice capacity is the no. of elements in the underlying array.
