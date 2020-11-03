## Go

- developed by google
- open source
- compiled language (can compile to any OS)
- Uses garbage collection
- statically typed
- a lot of built in functionalities (test, profile and formatter


### Problems that made google want a new language:
slow builds
uncontrolled dependencies
each programmer using a different subset of the language
poor program understanding (code hard to read, poorly documented, and so on)
duplication of effort
cost of updates
version skew
difficulty of writing automatic tools
cross-language builds


### Dependecy management in Go:
- unused dependencies are a compile-time error (guarantees that no extra code will be compiled when building the program, which minimizes compilation time).
- A imports B who import C. A uses C transitively. In this case, first C is compiled, than B, finally A.  When A is compiled, the compiler reads the object file for B, not its source code. That object file for B contains all the type information necessary for the compiler. This design has the important effect that when the compiler executes an import clause, it opens exactly one file this way the time to execute the dependency graph, and hence to compile, can be exponentially less than in the "include of include file" model of C and C++. Another feature of the Go dependency graph is that it has no cycles. The language defines that there can be no circular imports in the graph, and the compiler and linker both check that they do not exist. Although they are occasionally useful, circular imports introduce significant problems at scale. As with many of the design decisions in Go, it forces the programmer to think earlier about a larger-scale issue (in this case, package boundaries) that if left until later may never be addressed satisfactorily.


### Syntax:

can infer type on init, does not need to specify in this case:
buf := bytes.NewBuffer(x)

access modifiers
upper case initial letter: public
lowercase (or with underscore at beggining) private


### Semantics:

You can specify when to use a pointer or not, but there is no pointer arithmetic. When pointer is not used the object is copy not a reference as in java. There are no implicit numeric conversions. Array bounds are always checked. 


### Concurrency:

- Go is not purely memory safe in the presence of concurrency. Sharing is legal and passing a pointer over a channel is idiomatic (and efficient).But The motto is, "Don't communicate by sharing memory, share memory by communicating."


### Garbage Collection

The current design is a parallel mark-and-sweep collector

Go has no explicit memory-freeing operation: the only way allocated memory returns to the pool is through the garbage collector. In a concurrent object-oriented language it's almost essential to have automatic memory management because the ownership of a piece of memory can be tricky to manage as it is passed around among concurrent executions. It's important to separate behavior from resource management.



### Composition not inheritance

Go encourages composition over inheritance, using simple, often one-method interfaces to define trivial behaviors that serve as clean, comprehensible boundaries between components.


### Errors

No exceptions. (panic/recover)
If errors use special control structures, error handling distorts the control flow for a program that handles errors. The Java-like style of try-catch-finally blocks interlaces multiple overlapping flows of control that interact in complex ways. Although in contrast Go makes it more verbose to check errors, the explicit design keeps the flow of control straightforward—literally.
There is no question the resulting code can be longer, but the clarity and simplicity of such code offsets its verbosity. Explicit error checking forces the programmer to think about errors—and deal with them—when they arise. Exceptions make it too easy to ignore them rather than handle them, passing the buck up the call stack until it is too late to fix the problem or diagnose it well.



Usefull links:
https://talks.golang.org/2012/splash.article