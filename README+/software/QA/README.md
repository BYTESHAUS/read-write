<h1 align="center">Software &nbsp; &mdash; &nbsp; Quality Assurance (QA)</h1>

<table><tr valign="center"><td width="42%">
 
**Software is a pure abstraction ether poured into fragile containers made of code.**
 
The frivolous, fleeting, and exploding spirit of development makes it inherently and largely
 
<div align="center"><b><samp>E&thinsp;R&thinsp;R&thinsp;O&thinsp;R&thinsp;-&thinsp;p&thinsp;r&thinsp;o&thinsp;n&thinsp;e&thinsp;.</samp></b></div>
</td><td><picture><img alt="&nbsp;Bug in flask" src="../../_rsc/_img/signs/bugs/bug_in_flask-pencil-250px.jpg" /></picture></td><td width="42%">

**Software has become an irreplaceable stratum of civilization, as technology.**

Its applications manage crucial systems of all kinds and must be

<div align="center"><b><samp>S&thinsp;T&thinsp;A&thinsp;B&thinsp;L&thinsp;e&thinsp; </samp>and<samp> &thinsp;R&thinsp;O&thinsp;B&thinsp;U&thinsp;S&thinsp;T&thinsp;.</samp></b></div>
</td></tr></table>

<h2 align="center">And «<i>never the twain shall meet</i>» unless &thinsp;<b>.&thinsp;.&thinsp;.</b> <b><mark>&thinsp;Quality Assurance&thinsp;<mark></b>.</h2>

```mermaid
---
config:
  look: handDrawn
  theme: neutral
---
graph TB
 c1-->QA2
    subgraph "<h3><a href="https://github.com/BYTESHAUS/read-write/tree/main/README%2B/software/tests">Programmatic Tests</a></h3>"
    c1("<b>Proof</br>coverage</b>")
      TDD("<a href="https://github.com/BYTESHAUS/read-write/blob/main/README%2B/software/tests/asDrive/README.md">Test driven</a>")-->TDDev("Development")
      TDD-->TDDes("Design")
     c1 o--o TDDev
    end
    subgraph "<h3>Quality Assurance</h3>"
    a1(<b>Code</b>)-->a2(<a href="https://github.com/BYTESHAUS/read-write/blob/main/README%2B/software/QA/code_quality/README.md">Quality</a>)
  a1-->a3("Review")
    T1("<b>Testing</b>")-->QA1("Manual")
    T1("<b>Testing</b>")-->QA2(Automated)
    end
```

<h2 align="center">Prerequisites</h2>

Knowledge of/Experience in

+ **domain**/subjects,\
`//` or it will be programming "telephone charades" with the customer, or a great overhead of specifications
+ **tools** (as a platform and programming language),\
`//` learning complex technologies on critical projects is a burnout path or/and programming what's already available,
+ **fails** and retreats (preferably of others).

When security risks are a concern, other approaches for hacking vulnerabilities come into play &thinsp;&mdash;&thinsp; and devs aren't writing code in a criminal-minded mode.

This statement applies to all other cases where IT pundits lack the expertise to test the domain.

### Velvet gloves of discipline

Breaking changes as close as fingers to the keyboard, commits that can be rolled back with a click, development playgrounds and tesring sandboxes, ["it works on my machine"](../../pencraft/README+/memes/README+/polyptych_works.md), ...

What's admissible on "tangible" projects may lead to epic fails on a larger scale.

<h2 align="center">In process</h2>

<table><tr>
 <td>
  <picture><img width="250px" alt="&nbsp;Drake helps Lil Yachty with laptop (&quot;Life Is Good&quot;)" title="&nbsp;Drake helps Lil Yachty with laptop&#013;&#010;(&quot;Life Is Good&quot;)" 
   src="../../_rsc/_img/memes/Drake_LilYachty-LifeIsGood_laptop.jpg" /></picture></td>
 <td>
 <p>These are continuous measures within teams:</p>
 <ul>
  <li>Code reviews, pair programming, friendly discussions, and lessons.</li>
  <li>Preferred approaches as <a href="../tests/asDrive/">Test Driven Development</a>.</li>
 <li>Selection of popular or custom <a href="https://github.com/BYTESHAUS/use-dev/tree/main/README+/frames">guidelines</a> and <a href="https://github.com/BYTESHAUS/use-dev/tree/main/README%2B/techniques">techniques</a>.</li>
 </ul>
</td>
</tr></table>

<h2 align="center">Retrospective</h2>

<table><tr valign="top">
 <td>

### User feedback

Customer/user experience is the top mark (not only on the positive scale), and not every user is eager to share it.

Besides errors, surveys must find out frustration and, even more important &mdash; neglected features.
 
</td>
 <td><picture><img alt="&nbsp;&nbsp;IT came from the outer space" width="250px"
    src="../../_rsc/_img/snap/movies/IT_came_from_outer_space.1953-frag.jpg" title="IT came from the outer space&#013;&#010;&#013;&#010;director Jack Arnold, 1953" /></picture></td>
</tr></table>

### Meetings

With many "lessons learned", "sprint reviews" and similar behind I must say that they make sense provided the attendees will apply what they heard ASAP.

<h2 align="center">🧪Tests📏🪲</h2>

_Tests_ and _Testing_ are a <samp>CENTERPIECE</samp> of QA and <ins>&thinsp;w&thinsp;i&thinsp;d&thinsp;e&thinsp;</ins> umbrella terms for the check of code and its products (including documentation). Bug searching and quality proofing tests are optional but highly recommended and a natural part of software creation. 

### Manual (spontaneous and planned)

There's no full replacement of manual tests &thinsp;&mdash;&thinsp; only their underestimate

Unlike the olden days with blind commits of punchcards and tapes, most development allows its creators to assess the product (in whole or by feature) with every step and at the same time: just build and run.
 Responsible programmers are the primary, most prepared, most effective, and critical testers.

P.S. Opening this page was your manual test. 

### Programmatic tests

Executable code routines are the biggest cornerstone of modern QA. Automation of their run is fundamental to continuous quality and safety.

### Simulators

IT's more challenging to find an unavailable UI simulator or platform emulator, or virtual machine than a popular one.

## Appendix. Natural born quality

There were and will be remarkable works done from scratch **without** allotted proof and validation measures (let alone code reviews and test automation) **but robust** from the first release. 

This may (but mostly _will not_) happen in localized high-pro teams of responsible individuals, but as an exclusion underlines the need for __QA__.

> Coding cleanly and qualitatively must be the primary goal, but teams will be uneven, distributed/&thinsp;fluctuating, and stressed. Add human nature to sweep problems under the carpet &thinsp;&mdash;&thinsp; one quite big and thick in the software.
<h3 align="center"><ins>&nbsp;bottom line&nbsp;</ins></h3>

**QA** couldn't exist without errors &thinsp;&mdash;&thinsp; the catch-all term, with a dedicated [**corner**](README+/errors/) for its inmates. Where 🪲[bugs](README+/errors/README+/bugs.md)🪳 are the first-class citizens.

___________\
:end: ... continued in ... &nbsp;🚧[Errors](README+/errors/)  .&thinsp;.&thinsp;.  [Code quality](code_quality) &nbsp;.&thinsp;.&thinsp;.&nbsp; [Tests for QA](../tests/asQA/) &nbsp;...&nbsp; [Pitfalls](README+/QA-pitfalls.md) &nbsp;.&thinsp;.&thinsp;.&nbsp; [**TDD**](../tests/asDrive)
