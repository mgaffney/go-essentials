# Go Essentials

Reading, and understanding, Golang's "[Effective
Go](https://golang.org/doc/effective_go.html)" document is absolutely
essential for writing clear, idiomatic Go code.

_Rob Pike's_ article "[Go at Google: Language Design in the Service of
Software Engineering](https://talks.golang.org/2012/splash.article)" is
a must read for learning Go. He explains the very real problems they
were having at Google which lead them to create Go.

The book "[The Go Programming Language](http://www.gopl.io/)" by _Alan
Donovan_ and _Brian Kernighan_ is a must read. It is assumes you already
know how to program so it is very concise while still being very
readable.
Make sure you read both
Chapter 8 "Goroutines and Channels" and
Chapter 9 "Concurrency with Shared Variables"
carefully.
Overall, one of the best programming books I have read.


## Naming

Naming is always an important topic.
In Go, understanding how package names are used
is key to picking good names for your own packages.
The Go Blog's article
"[Package Names](https://blog.golang.org/package-names)"
is worth reading at least twice.

_Andrew Gerrand's_
"[What's in a name?](https://talks.golang.org/2014/names.slide)"
talk is also a good reference for Go's naming conventions including
"[length of variable names](https://talks.golang.org/2014/names.slide#5)".
Specific slides cover naming of:

- [Local variables](https://talks.golang.org/2014/names.slide#7)
- [Parameters](https://talks.golang.org/2014/names.slide#10)
- [Return values](https://talks.golang.org/2014/names.slide#11)
- [Receivers](https://talks.golang.org/2014/names.slide#12)
- [Interface Types](https://talks.golang.org/2014/names.slide#14)
- [Errors](https://talks.golang.org/2014/names.slide#15)

## Pointers

Understanding pointers is critical to writing clean and efficient Go
code. Unfortunately, pointers are difficult to understand.

Bill Kennedy's [four part
series](https://www.goinggo.net/2017/05/language-mechanics-on-stacks-and-pointers.html)
on "the mechanics and design behind pointers, stacks, heaps, escape
analysis and value/pointer semantics in Go" is a must read.

1. [Language Mechanics On Stacks And
   Pointers](https://www.goinggo.net/2017/05/language-mechanics-on-stacks-and-pointers.html)
   explains the basics of pointer mechanics using two examples in which
   a value is shared down a goroutine's stack. Bill steps through each
   of the examples and provides figures visualizing the layout of the
   stack at each step.

2. [Language Mechanics On Escape
   Analysis](https://www.goinggo.net/2017/05/language-mechanics-on-escape-analysis.html)
   focuses on the heap by using an example in which a value is shared up
   a goroutine's stack. Again, Bill steps through the example and
   provides figures visualizing the memory. Along the way, Bill talks
   about the readability of code when returning a pointer from a
   function and how the compiler performs static code analysis to
   determine if a value can be placed on the stack frame for the
   function constructing it, or if the value must “escape” to the heap.
   He also shows how to see the decisions the compiler is making for
   each of these values.

3. [Language Mechanics On Memory
   Profiling](https://www.goinggo.net/2017/06/language-mechanics-on-memory-profiling.html)
   shows other scenarios that can cause values to escape. Bill does this
   by debugging a program that is allocating in surprising ways. This
   article shows how to use a standard benchmark test and the memory
   profiler to find and fix a memory and performance issue.

4. [Design Philosophy On Data And
   Semantics](https://www.goinggo.net/2017/06/design-philosophy-on-data-and-semantics.html)
   is an absolute must read. When you declare a new data type, you must
   decide whether to use value or pointer semantics for the data type.
   Bill provides "semantic guidelines" to help with this decision.

5. __Bonus__: Bill's [For Range
   Semantics](https://www.goinggo.net/2017/06/for-range-semantics.html)
   article explores how the `for range` statement in Go provides both a
   value and pointer semantic form. He also shows a simple example of
   how easy it is to mix these semantics and the problems it can cause.
