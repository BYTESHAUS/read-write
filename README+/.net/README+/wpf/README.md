<h1 align="center"><code>WPF</code>.<samp>NET</samp> &nbsp;&mdash;&nbsp; <i>Freshener</i></h1>

### Despite justifiable and fetched skepticism, regardless of hard criticism from the very dawn, **WPF** (Windows Presentation Foundation) became a fully established successor of _WinForms_.

(Unlike its Web companion _manqué_ <code><b>Silverlight</b></code>, and cross-platform offshoots, like Xamarin.)

Now (in the 2020s C.E.) **WPF** is the number one platform for Windows desktops, hosting millions codelines of custom and enterprise software and enjoying a definite ebb in cross-platform demand.
 
Thus, WPF to .NET/Win is like the Moon to Earth &thinsp;&mdash;&thinsp; the natural and permanent satellite. Alternatives are either petite, marginal, exotic, still immature, or already deprecated<sup>🌘</sup>.\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>🌘</sup> <samp>You must know about WinForms and may have heard about [Avalonia XPF](https://avaloniaui.net/XPF)<sup>🔗</sup>, Xamarin, WinUI.</samp>

Web framework [**Blazor**](https://learn.microsoft.com/aspnet/core/blazor/hybrid/tutorials/wpf)<sup>🪟</sup> may become the same native unconstrained "bridge" to web browsers and tug a big part of applications, but it's too early to predict this.

### For developers `WPF`:

+ is "native" to Windows (64-bit memory addressing, multitasking, and direct hardware acceleration since _Windows&nbsp;7_),
+ is backed by Microsoft and .NET experts, concerned with its stability and progress,
+ implies [MVVM](https://learn.microsoft.com/en-us/dotnet/architecture/maui/mvvm)<sup>🪟</sup> and has promoted it to other platforms,
+ grants <ins>true</ins> **RADD** (Rapid Application Development and Deployment),
+ provides **full stack** development on .NET (+MS&nbsp;SQL) without the mix of platforms (and involvement of their providers), languages, and tools with differing paradigms<sup>☕</sup>.

___________\
&nbsp; &nbsp; <sup>☕</sup> <samp>Compare to Java, JavaScript/TypeScript stacks with a "botanical garden" of frameworks, libraries, and technologies. When scaffolding and interops may devour a quarter of the programmer's time (and most at the start).</samp>\
&nbsp; &nbsp; <sup>🌳</sup> <samp>Full stack here means more than the language and platforms, but a single-point definition of entities and functions (mitigating the front-back-end impedance).</samp>

## Rapid Development and Deployment with `WPF`

The learning curve of WPF is distinctly steeper, and the concepts to learn are much broader than those of _WinForms_. 
Nonetheless, a WPF newbie<sup>🔰</sup> entering either a new or established project has the luck to delay advanced topics till less stressful times. 

&nbsp; &nbsp; <sup>🔰</sup> <samp>But experienced in .NET and thinking in MVW<sup>hatever</sup> patterns.</samp>

This includes IDEs/tools, sketching, running, testing, and deployment.

### Initiatives

The best way to learn WPF is to build a basic MVVM application on a green field: proof of concept, prototype, or initial commit. You need a few minutes to start, as in this [basic demo](README+/mvvm/README.md#demo).

Even better is to take a renowned trial or freeware template, learn it, and design the application around it.

### Large projects

If the application is a grown WPF product, its components must make up a huge construction set, pieces of which a novice may soon manipulate with declarative tools. 

For example, take a pro table component from a gallery, declare it in a view, back it with the model data, and adorn it with custom logic in the ViewModel.

And most of these components are already available in miscellaneous suites.

### Deployment

Even if there are no DevOps or dedicated admins, clients can install or update their WPF applications (either as a prototype, test, or release) as easily as unpacking an archived folder. 
A kind of container that will work not only "[on my machine](../../../pencraft/README+/memes/README+/polyptych_works.md)".

---

__Further notes__:\
|&thinsp;- [**WPF and MVVM**](README+/mvvm/)\
|&thinsp;- [WPF lacks](README+/wpf-drawbacks.md)\
|&thinsp;- [WPF hints](README+/wpf-hints.md)\
|&thinsp;- [XAML view](README+/wpf-xaml_view.md)

➡️ **use-dev**:\
|&thinsp;-&thinsp;- 📖&thinsp;[MVVM Coherernce](https://github.com/BYTESHAUS/use-dev/blob/main/README%2B/decisions/README%2B/mvvm/mvvm-vmodel_cohesion.md)\
|&thinsp;-&thinsp;- 📖&thinsp;[MVVM Orchestration](https://github.com/BYTESHAUS/use-dev/blob/main/README+/decisions/README+/mvvm/mvvm-notification_orchestration.md)\
|&thinsp;-&thinsp;- ⌨️&thinsp;improved [Visibility converter](https://github.com/BYTESHAUS/use-dev/blob/main/src/TuttiFrutti/WinClay/Converters/bool2viz_improved.md)

__Resources__:\
|&thinsp;- [Awesome WPF](https://github.com/Carlos487/awesome-wpf)<sup>🔗</sup> &thinsp;&mdash;&thinsp; big collection of links about literally everything that may concern WPF developers\
|&thinsp;- [Prism](https://github.com/PrismLibrary/Prism)<sup>🔗</sup> &thinsp;&mdash;&thinsp; reputable representative of WPF/MVVM bootstrapping 

🔚 2021..2026..
