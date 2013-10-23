# Day 2 - October 23rd

## Which Way is Forward
Speaker: Crockford

Progress does not wait for the next new idea.

### Djikstra
* [The Humble Programmer](http://www.cs.utexas.edu/~EWD/transcriptions/EWD03xx/EWD340.html)
* [GOTO Statement Considered Harmful](http://david.tribble.com/text/goto.html#part-1)

#### Eliminate the GOTO Statement

##### Radicals
* Disaster.

##### Reactionaries
* Performance
* Tradition
* Freedom
* Pride
* Majority

##### Moderates
* Avoid where possible, but it is sometimes useful.

### Chronology
* 1968 GOTO Considered Harmful
* 1973 C - DR puts GOTO in the language
* 1985 C++ - GOTO is still in the language
* 1995 Java - does not have a GOTO and world does not end

### Paradigm Shift
I have never... so I don't see why...

### A Bug Story
`private int index;`

2001 Crock wrote in Java a package for JSON. Could create and parse JSON text.

11 years later someone creates JSON text that was GB's in size. `int` doesn't work anymore because of this.

Should have made it a `long`.

#### int
* Overflow and wraparound
* Complement: saving gates in subtraction
* Memory used to be really expensive and scarce

#### Number types

java:
* byte
* short
* int
* long
* float
* double

javascript:
* number(same as double)

You have one type, which is awesome because you can't pick the wrong type. The problem with js is that it's the wrong one.

##### Binary Floating Point
Made a lot of sense in the 1950s, but not a lot now.

Two branches of computing in the 50s: Scientific and Business.

### DEC64
Number = Coefficient * 10^exp

### +
adds and concats. :(

* Introduce the ~ concatenation operator
* JSLint and IDEs warn when + is used with strings
* A future edition redefines + to add only

rejected for es6. maybe try again in es7.

### Proof of Correctness
Tests can only prove the existence of bugs, not their absence. 1960s TDD was rejected because it didn't prove program was correct.

"Beware of bugs in the above code. I have only proved it correct, not tried it." - Knuth (1977)

### Types
* What do the bits mean?
* Easier than Proofs of Correctness?

"Well typed programs cannot go wrong." - Robin Milner (1978) 
overstating the benefits that type systems could give us.

#### Static Type Checking
Reactionaries:
* Little extra effort
* it is helping you

Moderates:
* Should be optional
* taste

Radicals (dynamic type):
* not worth the fight

### Classical Inheritance vs. Prototypal Inheritance
Inheritance comes at a cost. If you make design flaw in the lower levels it propagates up. 

`extends` makes programs and systems more brittle. 

#### Classification Taxonomy
Working with classes is hard to do correctly because you have to make a taxonomy at the beg. of the project when you don't know
what sort of objects you will need.

In the prototypal system you don't do any of this. You just make objects and use them.

#### Prototypal Inheritance
* may have made sense in 1995
* memory conservation
* confusing: own vs inherited
* retroactive heredity
* performance inhibiting

Brilliant idea in js is not prototypes, but class free inheritance.

### Milner's Promise
Will static typing ever be worth the freight?

### Functional Programming
* 1958 LISP
* 1973 ML
* 1975 Scheme
* 1984 Common Lisp
* 1990 Haskell
* 1999 JavaScript

### Paradigm Shift - Bad Idea
Hard to distinguish the two. 

One way, is if the reason you think it's a bad idea is emotional it might be a paradigm shift.

