# Monadic Parser Combinator written in swift
A simple haskell-style monadic combinator-based parser written in Swift.

A minium interpreter is also implemented in this tiny project.

## Try 

```swift
let c: String = " i = 0 print i sum = 0 while i<100  {sum=sum+i i=i+1 }   print sum"
let ast = (space() >>= {_ in com()}).p(c)[0].0
interpreter(ast)
```

## Features:

- Pure parser process without any side effects.
- Implemented with Haskell-like monad based operator `return`,`>>=`, and `zero`.
- Easy to scale up to deal with complex language parse and interprete.
- Concise code which extremely easy to understand and modify.


## Drawbacks:

- In order to keep it simple and stupid, there are lots of string construct operation, which has pool performance.
- Same reason as above, there are lots of direct array construct/deconstruct operation, which has pool performance, consider replace it with swift lazy evaluation feature such as AnyGenerator/AnySequence if u want imporve it.
