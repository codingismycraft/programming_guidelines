## Coding basic principles

Code is written once, but read, maintained, and modified countless times.

Code should not depend on "cleverness" or "brilliance" but must be "brutally
simple" to write, read, understand, and execute.

Minimalism beats feature plurality and complexity any day of the year.

The three factors to consider when writing code are:

- Necessary time to complete the task
- Quality of the code
- Cost

None of the above is a deterministing value:

Programmers and managers are notorious for understimating the complexity of
writing code and missing deadlines.

Quality of code is almost impossible to measure up front.

Cost of writing code depends of the number of people working on it and the
time it takes to write it, the easines of testing it and deployment
coplexities.

We should prioritize:

- Readability over cleverness
- Testability over convenience
- Consistency over personal preference

We should avoid:

- Premature optimization
- Feature creep
- Over-engineering
- Complicated code

## Avoid the move fast and break things principle

 A common approach in software development is to try to  move fast and break
 things hopping to fix them later. This approach should be avoided as it
 quickly accumulates technical debt that is hard to fix and also in many cases
 it makes vendor lockin a very difficult to remove task for the future.

 Programmers must always be conservative when it comes to agreeing in tight
 deadlines since in the vast majority of cases they will not be met.

## Function signature

A change starts with the function signature. Are there any changes needed to
it? If so, what are they? Are we going to need to add default arguments to the
function? Are we going to need to change the return type? Is this function
exposed from the module or private to it?

Local changes have the advantage of being more isolated from other changes thus
being easier to reason about.

## Implementation Changes / Unit tests

The implementation changes must be reflected in the unit tests and vice versa.
Enriching the tests to cover new functionality must be the first thing to be
done.

If there are side effects in calling the function that are not reflected in the
returned values they should be tested separately. For example, if the function
is creating a file containing calculated values, the test should be written to
a well known dummy location and be tested separately.

Each module must have its testing counter part following this pattern:

```
./mymodule.py
./test/test_mymodule.py
```

## Documentation and Code Comments

Functions, classes and modules should have docstrings (Google style is
preferred) explaining parameters, return values, and behavior.

Docstrings must be written in a way that is easy to read and understand and be
as short as possible.

Docstrings explain the WHY or the WHAT but not the HOW.

## Formatting

Code must be formatted in a consistent way. For python code a tool like black
is preferred.

Naming conventions must be consistent; depending on the language camelCase is
or snake_case can be chosen.


## Security and performance (basics)

Hardcoded secrets, API keys, or credentials do not belong to the source code and
should never be committed.

Premature optimization should be avoided and code should be written in a way
that is easy to extend, maintain, and understand by others.

Still, we should watch out for obvious bottlenecks (like N+1 database queries
or unindexed loops in critical paths).


## Testing coverage

Internally used front end code, or scripts that are not exposed to user directly
do not necessarily need to be tested.

Backend code should be tested with a very high degree of coverage reaching 100%
if possible.

Missing lines from testing must be identified and fixed if possible. Code that
is difficult to test is a sign of a bad design that should be refactored.

## Functions should do one thing and do it well

Avoid long functions that are trying to do too many things simultaneously.
Instead break the function into smaller functions that do one thing, test them
separately in isolation to others and compose them together in a simple way.

## Avoid smart / complex code

Code must be as simple as possible. Avoid code that is looks concise like the
use of the functional programming style, one liners etc. Prefer verbose code
over concise code that will be difficult to read in the future.

## Git policies

Never work directly to the master branch (or main branch). Instead always work
on a feature branch.

Commit changes frequently and avoid committing large chunks of code at once.

Before commit make sure that testing is passing and has high coverage.

Push changes to the remote repository and from there merge to the main branch
as soon as possible.
