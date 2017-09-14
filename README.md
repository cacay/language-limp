# Limp

Limp is an attempt at defining a programming language syntax that is a mix of [Haskell](https://www.haskell.org) and [YAML](http://www.yaml.org). Limp pushes indentation dependence to the limit by using it more uniformly and more broadly. For example, the following Limp code
```limp
some-function
    nested-function1 arg1 arg2
    nested-function2 arg3 arg4
```
is parenthesized as
```limp
(some-function
    (nested-function1 arg1 arg2)
    (nested-function2 arg3 arg4))
```
as a reasonable person might expect, whereas Haskell would interpret it as
```haskell
((((((some-function
    nested-function1) arg1) arg2)
    nested-function2) arg3) arg4)
```
or the more familiar
```haskell
some-function nested-function1 arg1 arg2 nested-function2 arg3 arg4
```
This happens because Haskell ignores indentation in expressions, whereas they are treated uniformly in Limp.

Additionally, Limp is almost [homoiconic](https://en.wikipedia.org/wiki/Homoiconicity) in the sense that a Limp program is spiritually a YAML document (except with a slightly different syntax): it is composed of (nested) lists and dictionaries of some base syntactic categories like integer literals and identifiers.

The name "Limp" is meant to be reminiscent of [Lisp](https://en.wikipedia.org/wiki/Lisp_(programming_language), since Limp is similar to Lisp syntactically except for it's use of indentation to signify grouping as opposed to parentheses.

Also featuring:
* [Mixfix operators](http://agda.readthedocs.io/en/v2.5.2/language/mixfix-operators.html) borrowed form [Agda](http://wiki.portal.chalmers.se/agda/pmwiki.php).
* Syntactically meaningful comments: comments are not plain strings; they have the same nested structure as code, and in fact, code and comments can be mutually nested. Code in comments is type-checked.


## Installation

Use [Stack](https://docs.haskellstack.org): `stack install limp`.


## Development

We exclusively use [Stack](https://docs.haskellstack.org) for development.


## Usage

```
limp --help
```

