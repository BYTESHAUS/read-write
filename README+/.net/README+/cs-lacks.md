# `C#` &nbsp;&mdash;&nbsp; Nice to have &nbsp;&mdash;&nbsp; Syntax, constructs and features

> ### <sub>[![C#](https://custom-icon-badges.demolab.com/badge/C%23-%23239120.svg?logo=cshrp&logoColor=white)](#)</sub> isn't a universal formula, and its team (counting the community) doesn't possess unbounded resources.<br />However, this platform could offer extra features and foundations, which would only boost its charm.

## More common interfaces

The general interface defines members like `Count`, `Clone()`, `Equals()`, `CompareTo()`, which developers are eager to apply to their code too.\
However, much more remains uncovered, e.g., Max/Min for limiting collections and object size.

Other promising members (like `IsReadOnly`) are defined within specific interfaces.

## Constraints

Constraints could allow much more freedom. **Firstmost**, `new()` shall not limit type to a parameterless constructor of objects without `required` fields.

<details>
    <summary><ins>&nbsp;Other syntax proposals&nbsp;</ins></summary>
&nbsp;
    
```diff csharp
Flush<T>(T stream) where T :  IDisposable AND System.IO.Stream

... where T : NOT Exception

// help with not "coupling" enums
- Bonus.Calc(IEnumerable<T> months) where T : Enum
+ Bonus.Calc(IEnumerable<T> months) where T : Month OR Months // Months is Month but [Flags]
```

I long for better [numbers](cs-drawbacks.md#Numbers) in C#, but meanwhile, constraints could improve the state.

```csharp
// rationally limited natural number
Retail.Price<N>(N val) where N : byte, short;

// other syntax variants
Retail.Price<N>(N val) where N : byte OR short;
Retail.Price<N>(N val) where N : byte || short;
```

To a turn (for me), numbers and constraints shall be like this sketch:

```csharp

method<N>(N arg) where N : number, N > 0 AND N < 150

method<N1, N2>(N1 left, N2 right) where N1, N2 : integer
   where N1 < 100  
   where N2 < 0

// and much more similar to your imagination
```

</details>

\__________\
☝️ Numerours high-rated queries on Q&A sites formulate demands for _constraints_ "grammar" further, better, and wider.

# Syntax

### Method arguments as in object initializer

If a method has arguments of compatible types, the chances are good that one shuffles them by mistake.

Named arguments are fine but optional. Some patterns and practices (sub-calls, side-typing) ensure the right assignment but bring overhead, and you still must deal with established calls and obey the args order.

Using an object initializer technique would be a relief.

```csharp
// a method with a confusing signature
Register(string firstName, string secondName, byte age, short numOrders, bool knownUser = false);

// alternate call
Register { lastName = "Deer", firstName = "John", numOrders = 2, age = 18 }
```

This would also make the initialization of objects from factory/builder methods prettier.

## Sugar

There's no excuse why shortcuts like `ArgumentNullException.ThrowIfNull(...)` aren't added to most exceptions. 
There could also be static classes without an evident _Exception_ suffix (e.g. `NotImplemented.Throw()`). 

Meanwhile, such substitutes are available in use-dev➡️ [exception shortcuts](https://github.com/Kyriosity/use-dev/tree/main/src/TuttiFrutti/ExtensionsTests/Exceptions) 🧪.

### Extra inheritance

<details>
<summary><ins>&nbsp;<b>Enum</b> &thinsp;&mdash;&thinsp; Design sketch&nbsp;</ins></summary>
&nbsp;

```csharp
enum FundamentalState 
{
    Solid,
    Liquid,
    Gas,
    Plasma
}

enum AppliedTheoryState : FundamentalStates
{
    CrystallLiquid,
    BoseEinsteinCondensate,
    NeutronDegenerate,
    QuarkGluonPlasma,
}

[Flags]
enum MyLabReagentStates : FundamentalStates
{
    Unknown = 0,
    NotApplicable
}
```

with downcast only, e.g.:

```diff csharp
-  FundamentalState state = AppliedTheoryState.Gas;
+  AppliedTheoryState state = FundamentalState.Gas;
```

---

</details>

<details>
<summary><ins>&nbsp;<b>Arguments signature</b> &thinsp;&mdash;&thinsp; Design sketch&nbsp;</ins></summary>
&nbsp;

Let's forget that long signatures are bug buddies and should be encapsulated into classes/structs or tuples. 

In fact, repetitive sequences of arguments occur (sometimes dictated by external tools), and it would be pleasing to ensure the same names are used in order.

```csharp

// one of the possible syntax through the attribute
[Args("Name")]
bool Login(string name, string familyName) { ... }

[Args("Name.Western")]
void Personalize([Name], string middleName, Degree title) { ... }

Guid Register(int attempt, [Name.Western], byte age) { ... }

```

</details>

## "In-line" Interfaces junction

Fine-grained interfaces and their multi-inheritance into more substantial ones are sound design practices.

Another story is a combination of primitive (or feature) interfaces as options for casting or *builders*.\
Suppose there are `ILimited`, `ITimestamped`, and `INotifyPropertyChanged`, which combinations imply 2<sup>3</sup> nominal declarations. And what if this could be done with `<IInterfaceA, IInterfaceB[, IInterfaceC[, ...]]>`

<details>
<summary><ins>&nbsp;Interface con-/disjunction &thinsp;&mdash;&thinsp; <b>Design sketch&nbsp;</ins></b></summary>
&nbsp;
    
```csharp
static class AircraftBuilder
{
// as return
        static <IAirSpecs, IPowerplant> BusinessJet(...) { ... }
        static <IAirSpecs, IPowerplant, ILoadSpecs> Cargo(...) { ... }
        static <IAirSpecs, IPowerplant, ILoadSpecs, IPassengerConfig> Liner(...) { ... }
}

// as arguments
IList<IataAirportCode> Planning.Destinations.FindOptimal(IataAirportCode from, <IAirSpecs, IPowerplant> vehicle) { ... }
void Planning.Capacity.Register(<ILoadSpecs, IPassengerConfig> transport) { ... }

```

\___________</details>

Such a feature can be extremely useful for object composition by builders and wizards.

This wish isn't new &thinsp;&mdash;&thinsp; here's a long old discussion of [types intersection](https://github.com/dotnet/csharplang/discussions/399)<sup>:octocat:</sup>.


### Builders / Wizards

The intuitive supply of syntax in chained calls (for code completion) is one of the best programming techniques. 
`C#` could provide out-of-the-box templates for builders and wizards boiling down custom projects (as my attempted [WizConstr](https://github.com/Kyriosity/use-dev/tree/main/src/TuttiFrutti/WizConstr/README.md)).


<ins>&nbsp;**More nice-to-have:**&nbsp;</ins>\
|- [Parts and frameworks](parts/cs-lacks-parts.md)\
|- [WPF lacks](wpf/README+/wpf-drawbacks.md)

🔚 🌓 2021-2025
