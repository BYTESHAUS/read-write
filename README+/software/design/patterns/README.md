# Code first &thinsp;&mdash;&thinsp; Patterns and Anti-patterns

The famed vision of code constructs as [Design Patterns](https://en.wikipedia.org/wiki/Design_Patterns)<sup><b>w</b></sup> has spread over software templates, project solutions, methodologies, and even developers' manners, but let's stay on its initial meaning &thinsp;&mdash;&thinsp; __code organisation__.

> [!NOTE]
> As the growth of hardware instruction sets lifted abstractions to the next level, clever programmers spotted useful code repeats to follow and recommend (beyond the vulgar copy-paste).
> 
> In the 1970s-1990s, these notes were augmented, systematized, and popularized &mdash; the most admitted of them became dogmatic and featured in languages/frameworks.

A pattern or anti- one may fit to a code line or embrass the whole class.

🚧 BIG BALL of Mud

:construction: ... TO BE CONTINUED with samples ...:pencil2:

## Pitfalls

### "Patterns-for-themselves"

Coercing the code to an appealing pattern is like inventing a sentence for a buzzword. 

#### Complicating

This also refers to overuse when, for example,  _Builders_ cover trivial constructors or their  `Create()`/`New()`. Or wrapping personal cleverness in a [monad](https://en.wikipedia.org/wiki/Monad_(functional_programming))<sup><b>w</b></sup>

### Pattern as anti-pattern

An unsuitable context may negate any pattern. Specimens? 

- Doubtful _singleton_ in Java or C# where injection is an escape: `void ProvePeriphery(ILog sharedLog);`
- any `Lazy<...>` loading that could be done async or custom

### Naming

Custom/personal (nick)names for established patterns aren't a good way unless it's a breakthrough idea or a remarkable workaround.

## Bottom line

**Keen developers will intuitively follow design patterns even if they are unaware of them.** However, learning is essential to keep rational thinking, know the recent, and use proper names with signatures.

___________\
**Going further:**\
|- [**Patterns** thru **techniques**](https://github.com/BYTESHAUS/use-dev/tree/main/README+/techniques) ➡️ (_use-dev_)

|- Design principles and methodologies\
|--- 🚧 reviewed SOLID 🚧

🔚 _<samp><b>BYTESHAUS</b></samp>meister_ 2025-2026...
