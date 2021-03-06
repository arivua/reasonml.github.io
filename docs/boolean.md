---
title: Boolean
---

A boolean has the type `bool` and can be either `true` or `false`. Common operations:

- `&&`: logical and
- `||`: logical or
- `!`: logical not.
- `<=`, `>=`, `<`, `>`
- `==`: structural equal, compares data structures deeply: `(1, 2) == (1, 2)` is `true`. Convenient, but use with caution
- `===`: referential equal, compares shallowly. `(1, 2) === (1, 2)` is `false`. `let myTuple = (1, 2); myTuple === myTuple` is `true`.
- `!=`: structural unequal
- `!==`: referential unequal

## Usage

**Note**: Reason/Bucklescript `true` and `false` [compile to JS `true` and `false` since Bucklescript 3.0](https://bucklescript.github.io/blog/2018/04/16/release-3-0-0.html). Before that release you had to use `Js.to_bool` and `Js.Boolean.to_js_boolean` but thankfully this is no longer the case!

## Tips & Tricks

**Use structural equal tastefully**. It's convenient, but might accidentally make you compare two deeply nested data structures and incur a big performance hit. It's also not always clear what counts as "equal". For example, is a piece of data `foo` equal to a lazy `foo`? Ideally, it'd have been pluggable. Future changes are coming to make this possible and reliable; if you're interested, check [modular implicit](https://www.reddit.com/r/ocaml/comments/2vyk10/modular_implicits/).
