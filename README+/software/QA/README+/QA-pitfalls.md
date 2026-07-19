# Quality Assurance &nbsp;&mdash;&nbsp; Pitfalls

> **I've collected some observations and bookmarks to share &ndash; not for tirades but as theses for countermeasures.**
 
<h2 align="center">Conceptual</h2>

### Fatigue

Even a minor change may require a thick layer of test coverage along with the modification of existing. And this can be temporary.

### Apathy

QA doesn't deliver end products but consumes resources and thus is the first to spare: declared or concealed, individually and by whole teams/departments. Consequences are the subject of luck or misfortune. 

Non-critical features may be neglected for years &mdash; don't expect all popular (especially mobile) apps to support 125% (150%, 200%) view scaling. Localization of enough applications may be unreadable. 

###  Formality vs. Engagement 

🚧 

Observation is harder than action. 

Fulfilling all test procedures manually or writing tests that may report a few non-critical errors disappoints and looks profligate.

### "Wishful thinking"

A software product or a team can deserve high credit. The side effects are non-critical and shallow checks, particularly of the established parts.

Good personal relationships may (note **may**) turn a blind eye.

### "Blaming the messenger"

The mirrored twin of _wishful thinking_ is the negative reaction of developers to reports. 
They may treat discovered omissions and bugs as accusations of bad performance (mostly wrong).

And yes, this means more efforts, stress, and diversion.

This will discourage testers from reporting the facts or soft-pedaling them.

### Bad domain knowledge

"Blind" programming and testing of the subjects is akin to technical translation by linguists.

### Undervaluation of foolproof checks, "criminal energy", and vandalism

Stories of many system breaches and epic fails began with "Who would ever...". 

<h1 align="center">Practical</h1>

 ### QA for TDD

This means careless development  [Test Driven Development](../../tests/asDrive)

This means careless development with QA in the loop as TDD LINK! and the hope that they will give fast feedback. This overloads the QA

### Sandbox and greenhouses

Usual conditions can be too good and stable.  Select a bad loc. A must for network, async, and high-load applications.

The easiest recipe is to develop/test applications in [unusual locations](../../../pencraft/README%2B/offtopic/anti-home-office.md).

<h1 align="center">REMEDIES ?</h1>

Easter eggs

**Continued in**\
|- [QA Tests pitfalls](../../tests/asQA/README+/QA_tests-pitfalls.md)

🔚
