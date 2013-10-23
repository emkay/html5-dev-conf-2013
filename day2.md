# Day 2 - October 23rd

## Which Way is Forward
Speaker: Doug Crockford (Paypal)

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


## Always Bet On JS: The Convergence of Operating System and Browser
Speaker: Nick Desaulniers (Mozilla)
Slides: http://slid.es/nickdesaulniers/jsos

The slides are really good so just go through those.

The demo with FirefoxOS dev tools in Firefox Nightly was pretty awesome.
Firefox Nightly
about:app-manager


##  Refactoring Web Interfaces
Speaker: [Jina Bolton](https://twitter.com/jina) (Do)

"It used to be that designers made an object and walked away. 
Today the emphasis must shift to designing the entire life cycle." -- Paul Saffo

People think of refactoring as busy work, but we shouldn't. There is usually always room for improvement in your codebase.

* Lack of clarity -> confusion. 
* No maintainability -> inefficiency

Refactoring: change the structure without changing the behavior.

### Refactoring, Style Guides, and Sass
Use a pre-processor:
[Sass](http://sass-lang.com)

Style Guide:
* [Writing an interface style guide](http://alistapart.com/article/writingainterfacestyleguide)
* [Front-end Maintainability with Sass and Style Guides](https://blog.engineyard.com/2011/front-end-maintainability-with-sass-and-style-guides)

Don't create pages. Create systems. Living style guides.


Make Refactoring and Documentation a regular part of your review process

"A fractured process makes for a fractured user experience" - Nate Fortin

### Css Gatekeeper
Any time anyone does anything FE related tag person in the PR to review.

Don't try to document __everything at once__.
Do document going forward.

Revising something?
__Refactor it__

When code style preferences come up in code reviews, document it for reference in later code reviews.

http://smacss.com

### Document your ideal CSS Architecture
* Vendor libs - bootstrap, compass, etc.
* Dependencies
* Foundation - typography, etc.
* Components - modular components and their states
* Regions - Page regions named after their role names.
* Helpers - clearfix, etc.
* Responsive - adjustments to type, grids, images, layout, etc.
* Tools -  Visible grids and diagnostic CSS


* Put new CSS in place
* Move old CSS as you get to it
* Move more when you have time

### Make a UI Lib
Really good example of a UI lib: Android style guide.
oocss

* Content
    * text
    * lists
    * tables
* Nav
    * tabs
    * pagination
    * filters
    * sorters
* Status
    * progress
    * alerts
    * toasts
* Interactions
* Icons

Keep documentation current and useful.

### Get to know the tools you use


### Libs 
[Susy](http://susy.oddbird.net/)

### Misc.
[Box-sizing: Border-box FTW](http://www.paulirish.com/2012/box-sizing-border-box-ftw/)
