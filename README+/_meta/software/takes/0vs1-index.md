<table align="right"><tr><td>
  
**What's common for**\
Paris, Australia, Mayan calendar, `C++`, and `Java`,\
**but differs from**\
Santiago<sup>&thinsp;🇨🇱</sup>, `FORTRAN` with `Basic`, and Common Era&thinsp;**?**

POINTER RUDIMENT

<details><summary><b><ins>&thinsp;Answer</ins>&thinsp;:</b></summary>
Base index of floors, years, and arrays.
</details>
</td></tr></table>

<br /><br /><br /><br /><br /><br /><br />

off by one errors. 

# <sup>_CODING_</sup> &nbsp; `++`Take on `zero` Index

Instead of [NullRefError.md](Null error) the RUDIMENT of 0-index is an EXPENSIVE error in HIGH-LEVEL LANGUAGEs

> ### There're different opinions, but my "Greek" take is:<br />one-base index is natural;<br />zero-base index in error-prone

INITIALIZATION OVERKILL (either declare extra nullability (undefined) or use signed (mark -1 but it's error-prone further)


PREHISTORY and A SIDE-BUGsy
REAL BUG when cross-referencing language modules (e.g., C# to Basic).

// NOTE: `1` is the `default` for Basic, which can be changed

<table align="center"><tr><th width="50%">0️⃣-based</th><th width="50%">1️⃣-based</th></tr>
<tr><td colspan="2" align="center">indexer <code><b>i</b></code>: default value <code><b>0</b></code></td></tr>
<tr><td>points to the first element, but collection may be empty<sup>🙋</sup></td><td>points to no element - GET MISTIQUE NULL REF ERR</td></tr>
<tr><td colspan="2" align="center">is first element </td></tr>
<tr align="center"><td><code><b>i == 0</b></code></td><td><code>i == 1</code></td></tr>
<tr><td colspan="2" align="center">is last elenent</td></tr>
<tr><td>i == count - 1</td><td><code>i == count</code></td></tr>
<tr><td colspan="2" align="center">is in upper bound</td></tr>
<tr><td>i < count</td><td><code><b>i</b> =< count</code></td></tr>
<tr><td colspan="2" align="center">is over bound</td></tr>
<tr align="center"><td><b><code>i > count - 1</code></b></td><td><code>i > count</code></td></tr>
</table>

<sup>🙋</sup> <samp>Programming languages may mask NullReference there as out-of-range</samp>

🥇🥇🥇         🥇🥇🥇🥇🥇🥇


___________\
🔚 🌔.. 2025-2026 .. <b>Β</b>ytesHausMeister

