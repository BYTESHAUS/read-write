# Naming &nbsp;&nbsp;&mdash;&nbsp;&nbsp; Practice

## Rules of thumb

* The higher the level of naming, the more attention.
* Name, apply, get feedback, refactor.
* At least two people with different backgrounds must confirm the top names.
* Avoid top names known in neighboring domains but with another meaning.\
(When possible, avoid names that may become language keywords, e.g., _field_ - hallo, C#13 preview.

## Guidelines

### Methods for values

* `Get` - means available values and must be a property,
* `Find` - implies efforts and queries which must bring the result (or fail with an exception),
* `Lookup` - implies querying, which may bring nothing. In other words, it's `TryFind`.

`Calculate`/`Process` is different from all the above.

## Traps

CLASS == NAME: e.g. Call(Guid guid) &rArr; design flaw

TRAP: Duplicate names in the chain!     PRINTER.PRINT

TRAP: The realm of `Helpers`, `Managers`, `Providers`. `Services`, ...

### Symbolic traps

ll -> EXAMPLES REQUIRED

INTERNATIONAL CHECK

## Verbal sins

- **Grandiloquence** 

General words sound vague (if not bombastic) unless established in the domain. Compare florid `[Fact]` to modest `[TestCase]`. 

- **Unexpected match** 

`public utility`

- **Jargonism**

### Guidelines for methods

`Get` must be taboo within method names - either this must be a property or a better description of the returned: `Read`, `Calculate`, _i.a._

## Appendix. Posers

Some naming occasions can be harder than difficult.

### "Can't touch this"

``Empty`, `Space`, `Noting`, `undefined`, `null`, `default`, `0` &ndash; all these can or may describe not available value.

Some guidelines can be derived:

* space isn't empty
* zero as other default values must be excluded

### Active or passive voice

`document.print(device)` vs. `device.print(document)`

// ToDescribe:

### Impedance with inherited domain names

// ToDescribe:

\___________\
🔚 2023-2025
