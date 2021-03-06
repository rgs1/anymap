``AnyMap``, a safe and convenient store for one value of each type
==================================================================

[![Build Status](https://travis-ci.org/chris-morgan/anymap.svg?branch=master)](https://travis-ci.org/chris-morgan/anymap)

If you’re familiar with Go and Go web frameworks, you may have come across the common “environment” pattern for storing data related to the request. It’s typically something like ``map[string]interface{}`` and is accessed with arbitrary strings which may clash and type assertions which are a little unwieldy and must be used very carefully. (Personally I would consider that it is just *asking* for things to blow up in your face.) In a language like Go, lacking in generics, this is the best that can be done; such a thing cannot possibly be made safe without generics.

As another example of such an interface, JavaScript objects are exactly the same—a mapping of string keys to arbitrary values. (There it is actually *more* dangerous, because methods and fields/attributes/properties are on the same plane.)

Fortunately, we can do better than these things in Rust. Our type system is quite equal to easy, robust expression of such problems.

The ``AnyMap`` type is a friendly wrapper around a ``HashMap<TypeId, Box<Any + 'static>>``, exposing a nice, easy typed interface, perfectly safe and absolutely robust.

What this means is that in an ``AnyMap`` you may store zero or one values for every type.

Instructions
------------

Cargo all the way.

The documentation, with examples, [is also available online](http://www.rust-ci.org/chris-morgan/anymap/doc/anymap/struct.AnyMap.html).

Future work
-----------

I think that the only thing left for this is filling out additional methods from ``HashMap`` as appropriate.

It’s a very simple thing. (The initial implementation time was under ten minutes.)

Author
------

[Chris Morgan](http://chrismorgan.info/) ([chris-morgan](https://github.com/chris-morgan)) is the primary author and maintainer of AnyMap.

License
-------

This library is distributed under similar terms to Rust: dual licensed under the MIT license and the Apache license (version 2.0).

See LICENSE-APACHE, LICENSE-MIT, and COPYRIGHT for details.
