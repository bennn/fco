First-Class Overloading
===


Experimental
---

Racket, TemplateHaskell, OCaml -ppx, Typescript
(Is Sweet.JS compatible with typescript? Probabably)

Catch bugs?


Rules (ASCII)
---

```
|- e : t 
==========

A valid        A |- t -> t'
--------------------------------------------------------  [V-Intro]
|- new-sig (A) (t -> t') : V (A) \in \emptyset (t -> t')


|- e_1 : V (A) \in S (t -> t')
|- e_2 : (t -> t')[A//t'']
(t'', _) \not\in S
--------------------------------------------------------  [V-Add]
|- add-sig e_1 e_2 : V (A) \in S \cup {(t'', e_2)} (t -> t')


|- e : V (A) \in S (t -> t')
(t'', e_2) \in S
------------------------------------- [V-elim]
|- cut-sig e t'' : (t -> t')[A//t'']
```


Related
---

#### [Aspect Classes, Darais](http://david.darais.com/assets/aspect-classes.pdf)

For "programming in the abstract".
An _aspect_ is something we can associate instances to.
Typeclasses use types as aspects.
This paper uses symbols.
A new _using-context_ construct explicitly resolves an application site.
(Tho, non-functional values may be overloaded.)


#### [Type Classes without Types, Garcia & Lumsdaine](http://www.deinprogramm.de/scheme-2005/scheme-2005-proceedings.pdf)

Generic functions, implementation depends on arguments (data-directed programming).
Predicate classes.



#### Typeclasses
- Multiple related behaviors, not just 1 function
- Change the meaning of a type
- Whole-program, else introduce incompatibilities (Int != Int)


#### SML
SML has overloading, I think.
Try Jun Furuse's [ppx implementation](http://caml-list.inria.narkive.com/wJewjBzV/ann-ppx-overload-ppx-for-user-definable-sml-style-overloading) before overriding (=) in OCaml
(does Jun handle arbitrary -> signatures? arbitrary type variables?)


#### Kaes
