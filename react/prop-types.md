# PropTypes
Are a way of defining what kind of code a component expects. It is like a very
basic type system that is run at runtime not complie time. They are useful but
often go out of date and are forgotten about.

## Whack-a-mole
I really like PropTypes, but this is an unfortunate problem that most teams
have, PropType Whack-a-mole. If a component is passed different types let's say
a string instead of a number. One engineer may fix the definition of the
component to expect a string, causing a PropType warning to pop up in a
different area of the application. Proptypes are great, use them, but be
cautious when "fixing" warnings and make sure that you aren't letting the usage
change the source.

## Typescript
This is actually what you want. If you feel the need for prop-types, just make the leap to Typescript. I believe in you.
