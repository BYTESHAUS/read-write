# `C#` &nbsp;&mdash;&nbsp; Drawbacks &nbsp;&mdash;&nbsp; _"Minority report"_

> ### <sub>[![C#](https://custom-icon-badges.demolab.com/badge/C%23-%23239120.svg?logo=cshrp&logoColor=white)](#)</sub> isn't an artwork to be perfect. Despite great ideas, contributions, and the best parts, there are downsides&nbsp;...

To begin with

- **single inheritance**,
- **rigid interfaces** (e.g., no ad-hoc definition),
- **bounded _generics_** and **their _constraints_**.

The following language artifacts might be found awkward. 

## Syntax

- Rudimentary **`;`** ending a line brings nothing but visual noise.<sup><mark>&thinsp;&thinsp;🔊</mark></sup>
- Constructor names imply extra refactoring on class/struct renaming &thinsp;&mdash;&thinsp; better it was "anonymous" `ctor()` or `this()`.\
Compare to the `base()` call in the same constructors.
- Default when missing access modifier<sup>⭕</sup> shall be better reserved for "ultimate" `private` or  `public` than for a less explicit and used `internal`
- The `const` modifier shall not be limited to pre-compiled values (as in intermediate languages) but shall prevent re-assignment, as `init` and `readonly` do.
- No constant option for default values in signatures. `Do(int val, string remark=string.Empty)` won't compile.
- Nullable declaration (with `?` prefix) is evident for value types but ambiguous for references and objects, which can be nulled anyway:\
`string a = null; string? b = null;`
- a perplexing extension of nullable as `((int?)1).Value` and `((bool?)true).HasValue`<sup>❓</sup>.

Gradual releases of syntax shortcuts, such as `?` or `!`, silently erode C# readability.<sup>🙋</sup> While shortcuts as `[]` for empty collections are rational and eye-pleasing.

\_______________

&nbsp; &nbsp; &nbsp; &nbsp; <sup><mark>&thinsp;&thinsp;🔊</mark></sup> <samp>Semicolon is optional before new line and not recommended in newer Kotlin and TypeScript.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>⭕</sup> <samp>These native features can't be changed.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>🙋</sup> <samp>Though you can avoid them, and hopefully, .NET team doesn't plan to make a Perl out of their language.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>❓</sup> <samp>Isn't `null` a value too (compare to the _undefined_ notion)?</samp>

### Fishy shortcuts

Some shortcuts obfuscate original goodies with insignificant gains in size.

For example, [`EnsureSuccessStatusCode`](https://learn.microsoft.com/en-us/dotnet/api/system.net.http.httpresponsemessage.ensuresuccessstatuscode) looks better in its expansion:

```csharp
if (response.IsSuccessStatusCode) /// or differentiate for more specific conditions
     throw new HttpRequestException(); /// or specify explicitly any custom exception
```
## Collections

- Pointer-style `0` as the start index in collections<sup>⭕</sup>, which doesn't correlate with the count and should better start from **`1`**.
- Size setters (as for arrays and collections) must have been unsigned integers: <code><b>u</b>int Length { get; }</code>. This could eliminate a big share of bugs and run-time errors.

## Generics

Advanced C# design reveals massive generic restraints and results in *Vodoo programming* to workaround them.<sup>🙋</sup>\
&nbsp; &nbsp; <sup>🙋</sup> <samp>.NET team [admits](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics)<sup>🪟</sup> that their generics are "_does nots_" of C++ templates.</samp>

Only some technical details will be listed here:

### Syntactic redundancies

The next definition is terse and clear, `class CollWrapper<C, T> where C : ICollection<T> { ... }`, but not the redundancy in its declaration `new CollWrapper<List<int>, int>()`.

## Type system
  
- Root `object`, both non-abstract and interface-less, asserts flaws in object-oriented design<sup>🐡</sup>. On the other hand, it brings an "original" footprint, big enough to pollute coding space with names.<sup>👣</sup>

- Either `class`, `record`, `record class`, `struct`, `record struct`, or *tuples* can declare an entity. Each has pros and cons for a particular case, but deciding between them could distract from design.

- There's no method signature to specify that it must unconditionally throw an exception, and `void` as a return is incorrect.\
(The workaround may be to [declare the return as an exception to be thrown](cs-hints.md#Gimmicks)).

- `void` could be a type. At least to make _Actions_ compatible with _Funcs_.

&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <sup>🐡</sup> <samp>Besides, the override of dummy `Equals()` and `ToString()` may bring nontrivial logic and violate _single responsibility_.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; <sup>👣</sup> <samp>Strongly annoying in inter-methods within builders, when you expect to select only among next steps.</samp>

## Single-class inheritance

A class may refer to only one base class but have multiple interfaces with default method implementations. This dismantles the argument for conceptual single-class inheritance (which must have been technically restrained).

However, arranging the code from some interfaces is rather cumbersome and restrictive &thinsp;&mdash;&thinsp; shall be reserved for limited technical purposes (not multiinheritance design).

Other peculiar and arbitrary alternatives are [extension members](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)<sup>🪟</sup> and dynamic composition (notably facilitated with [Roslyn](https://weblog.west-wind.com/posts/2022/Jun/07/Runtime-CSharp-Code-Compilation-Revisited-for-Roslyn)<sup>🔗</sup>).

&nbsp; &nbsp; <sup>🙋</sup> <samp>I do object to multi-inheritance for logic as destructive for single-responsibility but would like it for operational adornment: `ToString()`, `NotifyPropertyChanged`, `Compare`, and similar.</samp>

## Namespaces and class organization

* Historic namespaces as [`System`](https://learn.microsoft.com/en-us/dotnet/api/system) are bloated and mixed.
First of all, numerous errors should be moved from `System` to their own `namespace Exception`.__*__
* Classes like [`Math`](https://docs.microsoft.com/en-us/dotnet/api/system.math), [`MathF`](https://docs.microsoft.com/en-us/dotnet/api/system.mathf) shall be namespaces for granulated domain classes.

&nbsp; &nbsp; &nbsp; &nbsp; __*__<samp> System.SystemException &rArr; Exception.System</samp>

## Casting limitations

- [Named tuples](https://docs.microsoft.com/en-us/archive/msdn-magazine/2017/august/essential-net-csharp-7-0-tuples-explained)<sup>🪟</sup> and anonymous objects are very handy to submit sporadic composed results, but can't cast to an interface or class.
- Some obvious inheritance is missing (e.g., can't cast `DateTime` to `DateOnly`).
- Neither implicit nor explicit downcasting works while JSON (de)serialization legally does this operation.\
Allowing this cast doesn't contradict type safety.\
`// ToDo:` an example with [contravariance](https://learn.microsoft.com/en-us/dotnet/standard/generics/covariance-and-contravariance)<sup>🪟</sup>

## Built-in and shipped types 

### Numbers
  
- Does either developer ponder ten(!) primitive whole types when writing ordinary `for (var i = 0; i < count; i++)`?
- Summing up 0.1 and 0.2 will reveal a [floating arithmetic flaw](https://docs.oracle.com/cd/E19957-01/806-3568/ncg_goldberg.html)<sup>🔗</sup> unless explicitly declared decimal.<sup>🪲</sup>\
&nbsp; &nbsp; &nbsp; <sup>🪲</sup> Debug `var roundErr = 0.1 + 0.2;` to prove.

Developers should better declare just a *numeric* and distinguish only the way it's processed: fixed (default) or floating. It would be a great option to derive subclasses from this _numeric_ could (with range and precision constraints).

C#11 introduced [INumber](https://learn.microsoft.com/en-us/dotnet/api/system.numerics.inumber-1)<sup>🪟</sup>, which genericizes numbers but in a bulky and restricted fashion.<sup>🙋</sup>

### String

Laconic `==` implies _ordinal_ _case-sensitive_ comparison while `String.Compare()` is bulky and turbid.
`IndexOf` and other methods with numerous overloads invoke comparison, for which Microsoft advises explicit `Comparison` options.

Syntax shortcuts here could make the code both shorter and readable.

### DateTime

`DateTime` and refined `DateOnly` (non-casting from the first) are error-prone, awkward, and limited. 
Ironically, you may specify a date close to the year 9999 (when only regular astronomical events can be predicted that precisely) but not a recorded one before [Common&nbsp;Era](https://en.wikipedia.org/wiki/Common_Era)<sup><b>w</b></sup>.

Ambiguous order and `int` input of year/month/day allows nonsense values, which only the running code may or may not detect (_viz_. a bad bug).<sup>🐛</sup>.

&nbsp; &nbsp; <sup>🐛</sup> <samp>Test initalization and `.Tostring()` with `new DateOnly(2023, 02, 29)`, `new DateOnly(31, 12, 1975)`, `var May = 5; new DateOnly(2007, 1, May)`, `new DateTime(0, 0, 0)`</samp>

Continued in [C# lacks - Dates](parts/cs-lacks-parts.md#Dates).

## Inborn naming

### Interfaces

> The term *Interface* itself is too broad and common (and not only in `C#`). In fact, they are _contract_ specifications.

The **`I...`**_ prefix is not that essential for distinguishing interfaces (especially with the cawling merge of abstract classes and interfaces). _**I**_ may significantly harm the wording.

### One-liners

- LINQ [`Reverse()`](https://learn.microsoft.com/de-de/dotnet/api/system.linq.enumerable.reverse), is actually *flip*.
- Type modifiers _in_/_out_ for contra-/covariance collide with the same name parameter modifiers (_more_/_less_ can be better)

## Bottom line

The list is far from being complete, but maybe one day (more correctly to say a year) the team will strike a higher note &thinsp;&mdash;&thinsp; D-flat or even&nbsp;`D#`. Or it will be `TypeScript`.

<div align="center">🔚 ... 🌘 2023-2025, to be continued ...</div>
