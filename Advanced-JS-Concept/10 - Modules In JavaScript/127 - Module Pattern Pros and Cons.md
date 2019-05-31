# 127 - Module Pattern Pros and Cons

## PROS
- using IIFE we create a funcition scope, avoid polluting the global scope, hide essential thing into a module, thus avoid collisions name
- the code is Reusable.


## CONS
- still pollute the global scope (the damage are juste minified)
- We are not sure of dependencies, insure that the order of import is correct.