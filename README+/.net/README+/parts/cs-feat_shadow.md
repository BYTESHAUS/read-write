# `C#` &nbsp;&mdash;&nbsp; Features and Parts in shade

> ### Different from [underused sides](../cs-feat_underused.md), these shaded parts of <sub>[![C#](https://custom-icon-badges.demolab.com/badge/C%23-%23239120.svg?logo=cshrp&logoColor=white)](#)</sub> (both good or not) are specific, and a developer may never need any.<br />However, one must be aware of them to use on demand or weigh against a tailored realization.

## ReactiveX

Ironically, it was Microsoft that introduced [ReactiveX](https://reactivex.io/)<sup>🔗</sup>, but its fame was established through platforms of others, e.g., Angular.

[IObservable](https://docs.microsoft.com/en-us/dotnet/api/system.iobservable-1)<sup>🪟</sup> is in base classes, [Reactive extensions](https://github.com/dotnet/reactive)<sup>:octocat:</sup> are at least a decade in .NET and properly integrated with LINQ, but ... seldom utilized.\
Sure, event/stream-based development isn't for every use, and its paradigm requires some learning curve, but this isn't an excuse not to look in `System.Reactive.Linq`.

### Use cases

* Messaging. In evolved scenarios, you may like to group messages or give a grace period to revoke one.
* Hardware. Dealing with APIs, you may deal with physical effects and remedies (e.g., bouncing switches).

## Extensions properties - C#14❗

Now they are available as a preview.

```csharp
public static class NameDoesNotMatter
{
    extension(string test)
    {
        public string Test => test; 
}
```

## Miscellaneous
|&thinsp;- **General**&thinsp;<sup>🪟</sup>\
|&thinsp;-&thinsp;- [`DataObject`](https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.dataobject)\
|&thinsp;- Accelerated calculations\
|&thinsp;-&thinsp;- [Single instruction, multiple data (SIMD)](https://learn.microsoft.com/en-us/dotnet/standard/simd)\
|&thinsp;-&thinsp;- [Hardware acceleration](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/advanced/optimizing-performance-taking-advantage-of-hardware)

🔚 2022-2025 ...
