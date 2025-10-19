# `C#` &nbsp;&mdash;&nbsp; Good sides &nbsp;&mdash;&nbsp; _underused_

> ### Parts of <sub>[![C#](https://custom-icon-badges.demolab.com/badge/C%23-%23239120.svg?logo=cshrp&logoColor=white)](#)</sub> syntax, its certain features, libraries, and frameworks are <ins>preferable</ins> in development but often remain <ins>unrevealed</ins>.

## Freshly released

`C#` evolves swiftly with a regular release pace, but not every developer is an early adopter, and not every team is eager to update the breadwinning environment.

However, staying fit with `C#` is a reasonable and feasible attitude. Releases of .NET are cumulative and stable; besides introducing new syntax and structures, they provide improved performance, enhanced security, and extended support. 

Devoted bloggers and speakers<sup>👨‍👩‍👧‍👦</sup> do a great job of separating the wheat from the chaff while IDEs hint at new features.

___________\
&nbsp; &nbsp; <sup>👨‍👩‍👧‍👦</sup> <samp>No distinct recommendation here since this must be a personal experience, selection of the active, and a matter of taste.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; <samp>**Advice:** It's rational to begin with the original [dev blog](https://devblogs.microsoft.com/dotnet/)<sup>🪟</sup> and [officially released features](https://learn.microsoft.com/en-us/dotnet/csharp/whats-new/)<sup>🪟</sup>. (Many nice things are delayed from release to release, let alone those experimental.)</samp>

### C#13.NET9 (2024) ... but wait! ...

Among other features, two could be rather practical. Announced and promoted by bloggers, but "still in active development" (2025).

+ `using` aliases improved: 1) full qualification not required for imported namespaces, 2) generics supported.
+ `extension` keyword for shortened signatures, and properties support.

#### <mark>UPDATE:</makr> C#14.NET10 Preview (Apr/2024)

Lastly, they appeared with an alternate syntax!

### Earlier

The following "old" practical syntax and features remain unused in enough programs I've seen.

- [ ]  single file namespaces with `;` without `{}`
- [ ] [Tuple assignments](https://essentialcsharp.com/tuples#tuples)<sup>🔗</sup> &thinsp;&mdash;&thinsp; shortcuts assignment (swap!) and comparison.
- [ ] [`CallerArgumentExpressions`](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/proposals/csharp-10.0/caller-argument-expression)
(It urged me to rewrite ➡️[exception helpers](https://github.com/Kyriosity/use-dev/tree/main/src/TuttiFrutti/AbcStoppers/Errors).)
- [ ] `readonly` for `struct` methods &thinsp;&mdash;&thinsp; questionable but don't harm and may prevent bugs

##### `switch` beyond `else if`

With pattern matching, tuples, and `=>` replacing `break`, the good old statement got a second life.

## Pattern matching `switch` instead of `else if`s

"Conditional rows" with patterns and `_`-matching, "on-the-fly" tuples, and `=>` returns allow amazing tables of shortcuts.\
It's better to see once a recent video tutorial, for example [Advanced Pattern Matching in C#](https://www.youtube.com/watch?v=W-f9MHB-5TQ)<sup><picture><img src="../../_rsc/_img/logo/logo-youtube_h12px.jpg" title="&nbsp;Link to YouTube video" /></picture></sup>, Nov/2024.

## Shorter syntax

### `[..]` shortcuts

Range indexer for substrings, concatenation of arrays, ...

## Predicates and delegates as arguments

// ToDo: ➡️ move to hints ! ➡️ \
They are good for the parametrization of method calls, but are seldom seen there.

## Multitasking out-of-the-box

Exaggerated fears of intricacy may divert developers from the advantages of parallelism. C# presents high-level alternatives to custom bootstrap of multi-threading (semaphores, mutex, locks, pools). 

And it's not even about cozy [TPL](https://docs.microsoft.com/en-us/dotnet/standard/parallel-programming/task-parallel-library-tpl)<sup>🔗</sup>, PLINQ or unblocking with `async`/`await` but instant syntax alteration that unleashes the power of parallel computing.

<details>
   <summary><ins>&nbsp;Cycles get parallelized in a snap:&nbsp;</ins></summary>
   
```diff
   var nats = Enumerable.Range(1, 28_000_000).ToArray();
-  foreach (var item in nats) 
-    CalcHard(item);
+  Parallel.ForEach(nats, CalcHard); // must be faster on casual PC

static void CalcHard(int nat) {
   using var sha = SHA512.Create();
   _ = sha.ComputeHash(Encoding.UTF8.GetBytes(((int)Math.Sqrt(nat) / Math.Atan2(nat, nat)).ToString()));
 }

```

</details>

## All of the LINQ

The magic of LINQ is so practical that it's the first thing C# developers miss when coding in other languages.<sup>🔷</sup>

However, even its addicts may be unfamiliar with many tenable features. I knew about 
[`Cast`](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.cast), 
[`Zip`](https://learn.microsoft.com/dotnet/api/system.linq.enumerable.zip),
`SkipWhile`, `Append`, and `Prepend`, obscenely later than I must have used them.

Place here [`Lookup`](https://learn.microsoft.com/en-us/dotnet/api/system.linq.lookup-2) &mdash; the counterpart of the well-known `Dictionary`.

It's also better to be aware of disputable methods like 
[`OfType`](https://learn.microsoft.com/en-us/dotnet/api/system.linq.enumerable.oftype), 
[`DefaultIfEmpty`](https://learn.microsoft.com/dotnet/api/system.linq.enumerable.defaultifempty), 
[`TryGetNonEnumeratedCount`](https://learn.microsoft.com/dotnet/api/system.linq.enumerable.trygetnonenumeratedcount).

___________\
&nbsp; &nbsp;<sup>🔷</sup> <samp>If you're lucky enough not to meet this, such [cheatsheet of equivalents](https://www.garethrepton.com/TypeScript-equivalents-for-DotNet-Linq-functions/)<sup>🔗</sup> may give you a feeling.</samp>

## Reflection

The image of "illegal" hacking and rumors of slow performance follow the reflection, but are unfair for the former and exaggerated for the latter. 
It performs worthy tricks and has become a programming paradigm (unless trying to substitute a "direct" language construct). 

<mark><b>use-dev</b></mark>➡️ to [reflect](https://github.com/Kyriosity/use-dev/tree/main/src/TuttiFrutti/AbcRefl)

## Dynamic code generation

It doesn't involve a deranged imagination to improvise the auto-implementation of interfaces, to spare coding of countless combinations. 
[Roslyn](https://github.com/dotnet/roslyn)<sup>🔗</sup> has  much facilitated dynamic code, though there's a lack of good tutorials.

// ToDo: link to use-dev

## Extension members

+ Can spare the overload of declarations.
+ Allow calls on null.
+ Enable pseudo-dynamic switching between realisations (`using ...`)

### Props of polymorphism

// ToDo: EXAMPLE !

## Miscellany

### Value Task

[`ValueTask`](https://learn.microsoft.com/dotnet/api/system.threading.tasks.valuetask-1) was introduced in .NET Core 2.0 to wrap the result of `Task`. It won't create overhead if the result is available.

Along with another abstraction `IValueTaskSource`, it's a choice over `Task` for one-time calls without blocking and similar scenarios.

## Wrap up

There must be other useful but neglected parts, features, and syntax of `C#` and its subsystems that you may know and contribute to this document.

Plus to the mentioned above, there are:\
|&thinsp;-&thinsp;- [Parts in shade](parts/cs-feat_shadow.md)\
|&thinsp;-&thinsp;- Obsolete/bad parts, features, and [malpractices](cs-malpractice.md) 

\___________\
🔚 🌙 .. 2021-2025 ..
