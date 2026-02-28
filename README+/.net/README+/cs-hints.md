# `C#` &nbsp;&mdash;&nbsp; <samp>from everyday praxis</samp> &nbsp;&mdash;&nbsp; Hints

## Syntactic reminder

<details><summary><ins>&nbsp;Argument</ins> <code>out</code>&nbsp;<ins>for readability&nbsp;</ins></summary>
&nbsp;

```csharp
if (!PauseOver(out var remaining))
   _worker.Sleep(remaining);
```

Exception dampers (see in _Gimmicks_ below) can also use `out`.

</details>

<details><summary><ins>&nbsp;Discard with <i>underscore</i> when possible&nbsp;</ins></summary>
&nbsp;

```csharp
 // Remove visual noise of nominal arguments
  void OnMouseMove(object _, EventArgs __) { MyApp.Unfreeze(); };
// explicitly tells that signature parameters aren't used
```

 ```csharp
 // to point that the return value isn't required or a method/constructor is called for side-effect only
 _ = myShoppingCart.Pay(); // users don't care for the receipt returned 
 _ = new ResourceBlocker(filename); // stub objects (e.g., to invoke and prove constructor logic only) 
```
  
+ Not always the best choice:
  
```csharp
// null guard with *null-coalescing* ...
_ = myOrder?? throw new ArgumentNullException(nameof(myOrder)); 
// ... has a readable and shorter way
ArgumentNullException.ThrowIfNull(myOrder);
```
  
+ Not a _discard_, but pleasing

```csharp
const int milesToMars_CloseApproach = 38_600_000;
var rfidTagFilter = 0b_0111_1100_0100_0011;
```

</details>

<details><summary><ins>&nbsp;Avoid "magic" constants&nbsp;</ins></summary>
&nbsp;

Moving "magic values" to constants or predefined values doesn't clean the code **unless** named well.
  
```diff csharp
-     legacySystem.ModuleD1.Abracadabra = true; // specifies that text input is treated as case-sensitive
+     const bool InputIsCaseSensitive = true;
+     legacySystem.ModuleD1.Abracadabra = InputIsCaseSensitive;
```
```diff csharp
-     const int popupDuration = 3200;
-     Info(shortMessage).Popup(popupDuration); 
+     Info(shortMessage).Popup(Ux.MinToNoticePrompt.Milliseconds);
```
</details>

<details><summary><ins>&nbsp;Interpolate instead of&nbsp;</ins>&nbsp;<code>ToString</code></summary>
&nbsp;

```diff csharp
-    throw new ArgumentException(state.ToString());
// shorter and easier to decorate with text
+    throw new ArgumentException($"{state}")); 
```

</details>

<details><summary><ins>&nbsp;Extension members on </ins><code>null</code>&nbsp;<ins>...</ins></summary>
&nbsp;

Such calls can [run on null](https://github.com/Kyriosity/use-dev/blob/main/README+/frames/README+/calls_on_null.md), and they can be practical as in [⭐&thinsp;<b>I&thinsp;S&thinsp;I&thinsp;e</b>&thinsp;⭐](https://github.com/Kyriosity/use-dev/blob/main/README+/parts/_ext/ISie/README.md) .

</details>

## Gimmicks

<details><summary><ins>&nbsp;Negate with <i>exclusive or</i>❗&nbsp;</ins></summary>
&nbsp;

```diff csharp
-      isLoading = !isLoading // open for typos with other var
+      isLoading ^= true; // explicit inversion
+      isLoading = !offLoading // explicitly other var
```

```diff csharp
// Invert a longish chained property in legacy API:
-    Controller_A.CPU2.Circuits.TriggerY1.Input.S_plus = !Controller_A.CPU2.Circuits.TriggerV1.Input.S_plus;
// Have you noticed a typo (done on purpose), which can still designate a valid property
+    Controller_A.CPU2.Circuits.TriggerY1.Input.S_plus ^= true; // terser and "typo"-safe 
```

</details>

<details><summary><ins>&nbsp;Tuple to swap⭐&nbsp;</ins></summary>
&nbsp;

```csharp
(a, b) = (b, a);
```

A fantasy may suggest even more exciting snippets with "boxing" in tuples.

</details>

<details><summary><ins>&nbsp;Not only instance&nbsp;</ins><code>required</code></summary>
&nbsp;

The `required` marker might be essential, but it imposes immediate instantiation, which is impossible under some circumstances: _builder_, lazy, on-demand, and so on.

Leaving the default value for non-nullable values is bug-friendly, and nullable isn't much better.

[Use-dev stuff](https://github.com/Kyriosity/use-dev/blob/main/src/TuttiFrutti/AbcChrono/Timescales/Models/Hap.cs) shows a custom workaround, not perfect but...
```csharp
 UnixYear => _unixYear ?? NotSet.Throw(UnixYear);
```
</details>

<details><summary><ins>&nbsp;"Limit toggles" to protect runtime attributes</code></summary>
&nbsp;

Inline attributes as 
[`CallerMemberName`](https://learn.microsoft.com/dotnet/api/system.runtime.compilerservices.callermembernameattribute) or 
[`CallerArgumentExpression`](https://learn.microsoft.com/dotnet/api/system.runtime.compilerservices.callerargumentexpressionattribute) 
set value in runtime, but you can't rely on them since the caller may accidentally overwrite the values (that tastes like a flaw). 

```csharp

class Bio {
    static string Of(string firstName, string lastName, [CallerMemberName] string caller = "") {
        stats.Log(caller);
        /// ... further logic and return
    }
}

_ = Bio.Of("Paul", "Erdos"); 
_ = Bio.Of("Carl", "Freidrich", "Gauss"); // ERROR !

```

Instead of the discussion, I'd better propose an imperfect workaround in this [Extensions test](https://github.com/Kyriosity/use-dev/blob/main/src/TuttiFrutti/ExtensionsTests/Exceptions/99&#41;MiscDemos.cs).

</details>

<details><summary><ins>&nbsp;Exception dampers&nbsp;</ins></summary>
&nbsp;

It's legal to write `throw` in any C# method, but there may be motives to delegate exceptions up:

* Other concurrent methods (not only parallel) may throw, and the caller accumulates and weights exceptions without a heavy `catch` for each.
* You'd like to explicitly tell code readers what a method may throw (akin to a signature in Java).
* Method unconditionally throws and any return value (also `void`) deceives.

```csharp

ArgumentException BlockHack(params string[] args);
void Interpolate(PixelArea area, out ResourceException? exception);
bool TryParse(string raw, out ThisProjectException? exception); 
bool TryParse(string raw, out FormatException? exception, out ThisProjectException? exception); 
```

</details>

### More `using`

<details><summary><ins>&nbsp;Benchmark&nbsp;</ins><code>using</code></summary>
&nbsp;

```csharp
using (var benchmark = new Benchmark()) {
    // benchmarked flow here
}

class Benchmark : IDisposable
{
   string _caller;

   public Benchmark([CallerMemberName] string caller = "<undefined>") {
      _caller = caller;
      // Start logging/profiling
   }    

   public void Dispose() {
      // stop logging/profiling
   }
}
```
</details>

<details><summary><ins>&nbsp;Make ends meet&nbsp;</ins><code>using</code></summary>
&nbsp;

"Historical" routines, like persistence or services, often present procedural flows with opening&thinsp;/&thinsp;closing statements: e.g., `.BeginEdit()`&thinsp;/&thinsp;`.EndEdit()`, `.OpenConnection()`&thinsp;/&thinsp;`.CloseConnection()`.

Wrapping them with `IDisposable` object (no need for obvious snippet) not only provides readability but prevent bugs (forgetting to "end").

</details>

## Organization of entities

<details><summary><ins>&nbsp;Tuples as design shortcuts&nbsp;</ins></summary>
&nbsp;

Piles of interfaces, classes, and structs for every single trifle may obscure the contours of OOD, and their maintenance distracts from design. Then, sparsely applied _named tuples_ are a rational compromise.

```csharp
...
(int width, int depth, int height, DateTime availableFrom) FindMinPackageBox(Product[] products);
...
if (storehouse.FindMinPackage(goods).availableFrom < DateTime.Today.AddDays(3)) {
    goods.PremiumSupply = true;
... 
```

Further use is to streamline assignments:

```diff
// Given a chess game log ...
 chessGame.Move = "c5";
// .. you'd like to annotate moves
- chessGame.Move.Code = "c5";
- chessGame.Move.Comment = "Sicilian Defence";
- chessGame.Move.Timestamp = DateTime.Now; 
+ chessGame.Move = ("c5", "Sicilian Defence", DateTime.Now);
```

Unrestricted tuples, named or not, will be great helpers for prototyping code contracts until they solidify into interfaces and definitions. And with C#12, you can define tuples in namespaces (in global using too):

```csharp
using Book = (string title, short year, (string Name, string Surname) author);
```

</details>

<details><summary><ins>&nbsp;Distinct default of enums&nbsp;</ins></summary>
&nbsp;

Reserve, when appropriate, _none_, _undefined_ or _unknown_ as zero-value to prevent unexpected default assignment and consequent bugs.

```csharp
enum FundamentalStatesOfMatter
{
    Unknown, // implicitly = 0,
    Solid, // won't be assigned by default, e.g., to a motor coolant
    Liquid,
    Gas,
    Plasma
}
```

</details>

### Further

|- **WPF**\
|--- [WPF hints](wpf/README+/wpf-hints.md)\
|- **Rules**, **frames**, design **decisions**\
|--- ➡️ [**use-dev**](https://github.com/Kyriosity/use-dev/)

\___________\
🔚 ... 🎼 ©️# XXI&nbsp; &nbsp; &nbsp;[![C#](https://custom-icon-badges.demolab.com/badge/C%23-keyboard_fresh-orangered.svg?logo=cshrp&logoColor=white&color=tomato)](#)

