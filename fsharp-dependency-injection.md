Commonly, people associate partial function application as the main approach fro dependency injection in F# code. [[mark seeman]] claims that although this works, there is a slight gotcha that can reduce the maintainability of the code. And that comes down to the fact that partial function applications within the context of DI is not 'purely' functional because it smuggles in side effects. The reason this is important is that you, as the developer cannot depice whether a dependency that is being passed in has side effects or not as it has been **abstracted** away from you.

but why should you care whether your dependencies have side effects or not? - because they complect everything by **braiding things together**. it becomes complex. If you ignore complexity, you will slow down. You will invariably slow down over the long haul.

so whats the solution? how can we do dependency injection in F# while staying pure? you completely reject the idea of dependencies.

yes, i know. crazy right?

ignore the dependencies that take in inputs from the top level function which is unclear its state. its not a primitive value but a dependency of its own. also known as an indirect output. the idea is to decouple the fucntion from a side effect. another step may be required afterwards to fulfil the business logic but it wont be within that functions scope.

so you pick and choose what kind of 'dependencies' are passed in as 'arguments'. but those that take in an input which is a dependency of itself should be rejected completely.