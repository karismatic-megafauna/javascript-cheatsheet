# const, let, var
It used to just be `var`. Javascript was simple in this way.

Now, it is only use `const` and `let`. Never use var because it does not have
block scoping and causes bugs.

But what is the difference between these two new functions?

## const
Can not be reassigned.
> This is not the same as immutability.

## let
Can be reassigned.

# Conclusion
Always use `let` or `const`, use the one that more clearly states your purpose.
Rely heavily on your linter to help you figure out which you should be using.
