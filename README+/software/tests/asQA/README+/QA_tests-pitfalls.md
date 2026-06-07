........... 🚧🐝🚧 ... WORK in PROGRESS... 🚧✏️🚧

# <picture><img alt="&nbsp;PROG TESTS &nbsp;&mdash;&nbsp;" src="../../../../_rsc/_img/logo/progtests/hor/bw-300px.jpg" /></picture>QA &nbsp;&larr;&nbsp; Pitfalls 

<p dir=rtl>Testers hate it when<br />.developers know these catches<br/>(Clickbait🪝)</p>

> This is the continuation of [QA Pitfalls](../../../QA/README+/QA-pitfalls.md)

## Conceptual

### Redundant coding and automation

<p align="right">The key is to <b>test the areas that you are most worried about going wrong</b>.<br/>
That way you get the most benefit for your testing effort.<br />
It is better to write and run incomplete tests than not to run complete tests.<br />
<a href="../../../../pencraft/README+/quotes/README+/contributors/README.md#Kent-Beck"">Kent Beck</a>, "Refactoring", 1999</p>


Not every test should/could be written in code. Not every test automation will pay off. Furthermore, not every test must be formulated in steps.

UI tests are a protruding example, but on top of other specific, badly formulated, and irregular tests.

## "Technical"

### Tests of tests

Writing tests of test frameworks may put one into an infernal loop while running and analyzing application tests, which will find the errors there.

### Falsely green tests

The worst case of malfunctioning tests is a passing one that indeed shields a fail. And the worst of the worst is when such a fail-pass is sporadic and arduous to reproduce - imagine a crossroad with the random switch of green lights.

The following guidelines help to avoid the trap:

+ Periodically, botch and then check vital tests to show the "red" result.
+ Add counterpart test with the opposite result (e.g., that shall throw exceptions)

### TDD tribute

Procedures _Test Driven Development_ can serve in coverage &thinsp;&mdash;&thinsp; not practices.

<table><tr></tr><tr align="center"><td width="30%">⚙️&thinsp;<b>TDD</b></td><td>Proof coverage</td>
  </tr><tr valign="top"><td>
  <p>🔴&thinsp;Red</p>
  <p>🟢&thinsp;Green</p>
  <p>🟡&thinsp;Refactor</p>
</td><td>
  Write something, make it pass, and improve is the antipattern for coverage. Critical parts of the code must be thoroughly covered with both positive and negative ("inverted") asserts.
</td></tr></table>

### One-to-one with DRIVER (not DATA)

LINK to use-dev

## Practical

### Formalism

### Direct reference to implementation

Contrary to TDD, unit tests. Providers as adapters. // WRITE FOR TDD !

### Blind fit to green and carousel

Woodoo fix\
... 🚧  To DESCRIBE 🚧 ....

### Excess and overlap

Rules of a project may dictate 100% unit test coverage (at least one for an accessible member), and as a rule, this will formalize proofs. The formal test is a kind of `ASSERT 2+2 IS 2*2`<sup>:large_orange_diamond:</sup>.\
&nbsp;&nbsp;&nbsp;&nbsp;<sup>:large_orange_diamond:</sup>&nbsp;<sub>Please do not take verbatim. Such tests may be legit for floating-point checks.</sub>

The overlap means that a text _x_ will never pass if there's a test _y_ that fails. 

### Extra-long naming

`ValidateShouldReturnErrorWhenFirstNameIsNull()` &thinsp;&mdash;&thinsp; .

Would you admit such a name in the code? Why should it be in the test classes?

### Ideal environment

The tests, which somehow concern performance, connections, communication, proof of smoke, 

\___________\
⏲️... TO BE CONTINUED ... 🚧
