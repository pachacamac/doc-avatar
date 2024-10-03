# doc-avatar
Tiny web component that shows a unique'ish SVG based doc icon depending on a name. Think identicon/gravatar for doc icons.

[DEMO](https://raw.githack.com/pachacamac/doc-avatar/main/index.html)

## Some motivation details
I needed/wanted an easy way of displaying different icons for different documents for a project. Got carried away a bit and had a bit of fun with procedural generation.

## Some implementation details
The seeded random number generation is based on the Mulberry32 PRNG which I think I ported from [here](https://gist.github.com/tommyettinger/46a874533244883189143505d203312c).
And the string hashing is ported from [here](https://burtleburtle.net/bob/hash/integer.html) if I remember correctly.

Other than this the implementation is be pretty straight forward and goes something like this:

- create a vanilla web component
- hook up attributeChangedCallback
- read the name attribute
- hash the name
- seed the PRNG with the hash
- create an SVG with a path that looks like an empty document
- draw some random lines and boxes based on the seeded PRNG into the SVG
- throw the SVG into the shadow dom
- and done

## Usage
The full implementation and usage examples are in the index.html file.
If you find it cool and would like to use it you can do so free of charge in any kind of project including commercial ones.
Please respect the chosen license and include a reference of it and the original work.

## Contribution
More than welcome and appreciated. Just open a PR! You can also open an issue with ideas/suggestions/questions etc.
