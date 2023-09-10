# What Is Functional Programming?

Simple Answer: Building programs by applying and composing functions.

- Functional programming harnesses language support by using functions as variables, arguments, and return values—creating elegant and clean code in the process.
- FP also uses immutable data and avoids concepts like shared states. This is in contrast to object-oriented programming (OOP), which uses mutable data and shared states.
- Functional programming languages focus on declarations and expressions rather than the execution of statements.
- Functions are also treated like first-class citizens—meaning they can pass as arguments, return from other functions, and attach to names.
- FP focuses on the results, not the process, while iterations like loop statements and conditional statements (e.g., If-Else) aren’t supported.
- Languages pure functional programming langugae:
  - Haskel
  - Erlang
  - Common Lisp
  - Scala
  - Now all programming lang have the feature of functional programming

### Pure Functional Programming

```javascript
function updateMyAddress(newAddress) {

   const myAddress = [“ChurchSt”, “CovingtonCross”];

   myAddresses[myAddresses.length] = newAddress;

   return myAddresses;

}

```

- updateMyAddress() doesn’t need any external code to accomplish its tasks. This means it’s a pure function.

### Impure Functional Programming

```javascript
​​const myAddresses = [“ChurchSt.”, “CovingtonCross”];

function updateMyAddress(newAddress) {

  myAddresses.push(newAddress);

  return myAddresses;

}
```

- updateMyAddess() is an impure function since it contains code (myAddress). `This code mutates an external state`, which gives updateMyAddress() some side effects.

# Why does functional programming matter?

- `For Data Science, Big Data and Machine Learning`
- A side effect occurs in a program when you insert external code into your function. This prevents the function from properly performing its task. Impure functions, in contrast, contain one or more side effects. But `functional programming no side effects`
- `Keeps concurrency safe` – Code is thread-safe when no two concurrent processes try to access the same data simultaneously. This bug is a race condition. Since pure functions never share a state with other sections of the program, race conditions can’t occur
- `immutable code` is easier to update, more efficient to manage, and easier to test and debug. And because variables are constant, the resulting code is easier to understand and reason about.

# When should a functional programming language be used?

- Due to its pure nature, FP is ideally suited `for analyzing extensive data sets and machine learning`.
- Pure functions `will always generate the same results`, with no outside values to influence the final results.
- Because of its `modularity`. Modularity breaks down large and complex projects into simpler modules. You can test the modules separately, which lessens the amount of time spent on unit testing and debugging.
- OOP works best for standardized and straightforward projects,
- whereas FP works best for projects that require scalability and flexibility.

## Object-Oriented Programming vs Functional Programming

- OOP --> imperative programming model, meaning functions are invariably coded in every step needed to solve a problem. You code each operation with the code itself specifying how to solve the problem. This model requires the programmer to know which functions are necessary to solve a problem instead of relying on models that can solve the problems.

- FP --> declarative programming model, meaning it relies on the underlying concepts of a programming language to execute the necessary steps to reach the predetermined outcome.
  </br>
- `Imperative programs` focus on the step-by-step process of solving a problem, whereas `Declarative` programs focus on the result of solving a problem.

- Another critical difference is mutability: OOP uses mutable data while FP uses immutable data. You can alter (or mutate) mutable objects after creation, whereas you can’t for immutable objects. In FP, you’ll need to make a copy of the object and use that copy to write the rest of your code.

## Resources:

- [By Coding Dojo](https://www.codingdojo.com/blog/what-is-functional-programming)
- [And the Best One by John Hughes](https://www.cs.kent.ac.uk/people/staff/dat/miranda/whyfp90.pdf)
