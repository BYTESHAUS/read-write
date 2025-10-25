# Code _`// Comments`_

<p align="right">Compilers don't read comments (or design documents) <br/>and neither do many programmers (consistently).<br />
<a href="https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#p1-express-ideas-directly-in-code">C++ Core Guidelines</a></p>

<p dir="rtl">,<i>When you feel the need to write a comment<br />first try to refactor the code so that<br />.any comment becomes superfluous</i><br />
 <a href="../../../pencraft/README+/quotes/README+/contributors/README.md#Kent-Beck">Kent Beck</a>, "Refactoring", 1999</p>
<p align="right">___________</p>
<p align="right">When code resembles a manuscript<br /> consider writing the documentation.</p>
<p align="right">___________</p>

> **Comments can be eye-catching and essential, but signal design inconsistency and poor naming.**<sup>🙋</sup>

Carefully written [quality code](../../QA/code_quality/README.md) is self-descriptive by nature and needs no epistolary clarification<sup>🙋</sup>, 
and even abracadabra in _regex_ processors can be broken down into figurative methods and variables. 

However, rehearsed names of classes, functions, arguments, and properties bloat many (if not the majority) files of prominent (and lesser-known) contributors on Git (or elsewhere)<sup>📄</sup>.

Accompanied by info and copyright<sup>©️</sup> headers and footers. 

\___________\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>🙋</sup> <samp>This statement is for high-level declarative languages.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>📄</sup> <samp>Sometimes on a single purpose to enlarge the number of committed lines.</samp>\
&nbsp; &nbsp; &nbsp; &nbsp; <sup>©️</sup> <samp>As if there were no license agreement or such a spell may prohibit impudent copy-paste.</samp>

## Indulgences

🔷 First and foremost, descriptive comments and blocks of them in **demo tests** &thinsp;&mdash;&thinsp; to serve as guides for devs and presentations for users. 

Other valid points are:
 
+ stamps on auto-generated stuff,
+ bizarre workarounds (especially for third-party bugs),
+ courtesy of Q&A sites,
+ worthy tricks that harm readability,
+ code snippets in documentation,
+ informal notes on test data,
+ domain-explaining quotes from sources like a wiki,
+ explanation of voids **when** significant (`intentionally left blank`, `this class must be void`)
 
One other distinct and legitimate niche is [comment-driven development](https://en.wikipedia.org/wiki/Comment_programming)<sup><b>w</b></sup> (though it's more fun).

Comments may be anchored _theses_ for documentation, if you can effectively support two-way updates.

##  Wrap up❗Breaking exclusion &thinsp;&mdash;&thinsp; Nota bene

Some members may require clarification, e.g., a _natural number_  constraint **may** include zero or not. Then a name may specify it (`IsNaturalNonzero` / `IsNaturalOrZero`). 
This can't be a solution for cases such as `RemovePunctiation()`: what symbols exactly shall include `«»»` (guillemets), is `_` punctuation, ...?

Tests shall fragment distinctions but are not comfortable for hints and unavailable through API, services, or, generally speaking, interfaces.

> **Then a comment can be necessary to appear as a hint.**

(And such comments shall be reserved for interfaces/core public entities.)

<picture><img alt="&nbsp;Tip for MiscSymbols listing these symbols" src="../../../_rsc/_img/snap/screen/VisualStudio/Tip-MiscSymbols.jpg" /></picture>

## Appendix. Commenting the code 🧹out

Switching off code lines is a common manipulation, but committing one requires a comment at least stating that it was intentional. 
It might be just three slashes `///` or a team may decide on acronyms like:

&nbsp; &nbsp; `///DEL` — delete after review\
&nbsp; &nbsp; `///ALT` — alternative implementation \
&nbsp; &nbsp; `///ERR` — doesn't work\
&nbsp; &nbsp; `///EXC` — causes an exception\
&nbsp; &nbsp; `///IDEA` — It was a fast sketch, which one may simplify or elaborate\
&nbsp; &nbsp; `///LOL` — i did it for lulz


\___________\
 🔚 🌘 2023-2025 ..
