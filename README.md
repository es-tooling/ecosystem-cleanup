# JS ecosystem cleanup

This is a place to keep track of the various ongoing efforts of
providing a cleaner, simpler dependency tree in the JS ecosystem for those
who are concerned with it.

## The problem

Packages often have dependencies, and those dependencies themselves have
dependencies, and so on. This is fine and expected with how dependency trees
are structured.

However, over the years many of these deepest dependencies are long since
obsolete utilities, polyfills, and so on. At the time they were introduced,
they were important and had their use, but are now arguably redundant to
most of us.

For example, polyfills for `Array.prototype.includes` are often found
deep in most projects' dependency trees, and yet this feature has been available
since Node 6 (released in ~2016).

Similarly, we have all collected "micro packages" over time without realising
it. These are very small (often one-liners) packages we depend on to do
simple pieces of logic the JavaScript language already allows us to do. For
example, `is-string`, `is-number`, `is-nan`, etc.

There are many reasons you could argue these are a bad idea. Security,
complexity, install time, bundle size and so on. We unnecessarily download,
install and include hundreds of these packages when the platform already
provides the same functionality.

## They have their uses

Some of these packages do have their use, and a small group of consumers
strongly disagree with removing them (usually the creators of said packages).

For example, one primary argument for using the polyfill-like packages is
that a third-party package can override built-ins and break another package's
code. To counter this, these packages use a custom implementation/wrapper around
the native functionality instead of using the native functionality directly
(since nobody can override the wrapper).

If you need this kind of protection against the way JavaScript works, then of
course this cleanup is not for you.

## The effort

This is not an easy problem to tackle since these packages are so deeply
embedded in our system, far below the packages we knowingly install day by day.

To make things easier, we will be splitting up the work into much smaller
and more manageable tasks to gradually chip away instead of a big bang solution.

Some examples of what we will be doing:

- Remove these packages from popular packages as direct dependencies
- Fork packages which have officially stated they will never move off these
packages
    - Where possible, make these forks track the original source repo (i.e.
catch up from main when the origin changes).
- Replace redundant polyfills with native functionality in popular packages
- Replace these packages with cleaner alternatives

The main goal is to _contribute_ to the packages we actually use (which depend
on these things), and as a final resort, fork what is immovable.

## Contributing

If you'd like to contribute towards the effort, simply find an issue you would
like to help with and just let us know with a reply that you are going to tackle
it. We will be happy to help you along the way.
