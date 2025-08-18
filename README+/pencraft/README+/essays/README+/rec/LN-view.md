<h1 align="center">Lotus Notes: "<i>This used to be my playground</i>"</h1>

<table><tr><td>

#### `Lotus Notes` (henceforth also `LN`), the multiplatform groupware, was first released at the turn of 1991. 

Joining the best of computer sciences from the 1980s with _laissez-faire_ IT in the 1990s, it rapidly became the core asset for companies and teams.

</td><td width="30%">
<picture><img alt="&nbsp; Lotus Notes R5 splash screen" src="../../../../../_rsc/_img/af/LN/LotusNotesR5_SplashWin.jpg" title="&nbsp;Splash screen of &#010;Lotus Notes R5"></picture>
</td><td>

As a developer of Line-of-Business and corporate applications on Lotus Notes for over a decade<sup><mark>#</mark></sup>, I&nbsp;must have deserved the privilege of personal (Lotus) notes.

<p align="right"><sup><mark>#</mark></sup> <samp>Before I cast my lot with <a href="../../../../../.net">C#.NET</a>.</samp></p>
</td></tr></table>

### IBM PC users remember (or not) that it was a time and a <b>word</b> &thinsp;&mdash;&thinsp; not Microsoft's one or WordPerfect, but <br />«<mark>&thinsp;L<samp>&thinsp;O&thinsp;T&thinsp;U&thinsp;S&thinsp;</samp></mark>» &thinsp;&mdash;&thinsp; a synonym for spreadsheet, text processor, calendar, E-Mail client, and collaboration tools.

<table><tr><td width="30%"><picture><img alt="&nbsp; Lotus Notes R8 workspace"
  src="../../../../../_rsc/_img/af/LN/LN-WS_snapshot(computerwoche.de).jpg" title="Screenshot of casual Lotus Notes R8 workspace&#013;&#010;(source: computerwoche.de)" /></picture>
</td><td>

Developers and admins will reminisce about genuine Rapid Application Development with fluent installation/evaluation<sup>🙋</sup> and leading-edge editors.

**LN** paved the public road to diverse innovations: client-server, multirole/group access, distributed/synchronized doc-oriented DB<sup>📜</sup>, **replication**<sup>⭐</sup>, asymmetric encryption from authorization down to selected fields on demand &thinsp;&mdash;&thinsp; to name a few of the extraordinary goodies.

There were similar suites &thinsp;&mdash;&thinsp; legacy, alternative, or tailor-made &thinsp;&mdash;&thinsp; but this aquatic flower dominated the market garden ... until Microsoft began to win large chunks of the office software market.
  
</td></tr></table>

* In **1995**, <samp><sub>[![IBM Badge](https://img.shields.io/badge/IBM-052FAD?logo=ibm&logoColor=fff&style=for-the-badge)](#)</sub> gained Lotus in full<sup>💰</sup></samp>.\
It was a big chance not only to gain from sales and internal installations, but also to reform at least _LN_ by leaning on the influence and technological capital of Big Blue.\
However, mediocre and inaccurately focused efforts caused Lotus to wilt.<sup>🍦</sup>

* In **2001**, <samp><sub>[![Microsoft](https://img.shields.io/badge/Microsoft-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)](#)</sub></samp> released its "bird of a feather" &thinsp;<samp>&mdash;</samp>&thinsp; **SharePoint** &thinsp;<samp>&mdash;</samp>&thinsp; much more sophisticated and bulkier but promoting the next generation of a product and API.\
SharePoint was deprived of many inherent vices of the Lotus pioneer and gradually began to supersede _LN_ in the one-way migration. 

* In **2018**, the sell-out of Domino/Notes and granting the office's source code to freeware pushed **_LN_** out to IT margins.

___________\
&nbsp; &nbsp; <sup>🙋</sup> <samp>I can't feature a newbie installing SharePoint on a notebook and writing the first useful application within a week.</samp>\
&nbsp; &nbsp; <sup>📜</sup> <samp>Long before NoSQL became mainstream.</samp>\
&nbsp; &nbsp; <sup>⭐</sup> <samp>Emphasized for rare ease, versatility, productivity, and robustness. Besides synchronizing DBs it allowed us to seamlessly use/develop LN offline, guarantee messaging, and merge design much simpler than in Git or TFS.</samp>\
&nbsp; &nbsp; <sup>💰</sup> <samp>For a $3.5 billion &mdash; pretty good deal before IT procurements had skyrocketed in the 2000s.</samp>\
&nbsp; &nbsp; <sup>🍦</sup> <samp>It's not a top secret that IBM's cold shoulder urged many top Lotus contributors to leave.</samp>

<h2 align="center">Postscriptum. Alternate history</h2>

_Lotus Domino/Notes_ had enough outdated and weak facets to surrender to the rival from Redmond (WA), but let's dream up what the "surviving" LN would be.

### 💿 Storage as a sound object-relational model over IBM DB2

There was a never-realized plan to put DB2 under LN (like MS SQL behind SharePoint) instead of an enclosed and specific Notes Storage Facility (NSF). 

**NSF** didn't support foreign keys, thus requiring "amateurish" boilerplate for any document relations (as a hierarchy). 

### ☕ Replacement of `LotusScript`

 Most developers _nolens volens_ coded in the out-of-date and too elementary _LotusScript_ &thinsp;&mdash;&thinsp; a branch of Visual Basic with built-in LN API (with C++ API behind). 
 
 LN also rendered C++ and Java API, but it was limited and tricky (its version always lagged and required knowledge of specific workarounds, like calling the garbage collector in a cycle of LN docs.

`Java`, `C++` or a flavor of `JavaScript` as a main language

### 🌩️ Single-Page Web-Application as the only user client

Akin to Angular or React, eliminating desktop premises and porting _@formula_ language to JavaScript utilities. Though Notes Server could render applications on HTTP since 1996, designing forms required pretty much fine-tuning with HTML/JS.

**XPages** (since R8.5) came too late and were half-hearted.

### 📎 Seamless UI integration of office parts

Either from Microsoft or those updated from Lotus< (1-2-3 and Word Pro were already outmoded in 2000), in popular open formats 

### 🏬 Learning and development resources

The difference between IBM's "_search for_" and Microsoft's "_select from_" reading materials was notorious.

#### Libraries of UX elements and utils, dev environment extensions
 
Lotus Notes could be on the wave of Open Source.

### 🙋 Last but not least

Top pro and liable  _Notes_ team/community to fulfill this wishlist and prevent quality degradation. 

"Migrating" myself from LN to .NET, I experienced, for certain, that beta versions of Visual Studio&nbsp;2010 crashed less often than the release of Notes Designer.
FOSS

<h2 align="center">⬆️ <mark>Was it technically doable? &thinsp;&mdash;&thinsp; <b>Absolutely</b> ⚫</mark></h2>

> Let me finish with the quote from another single: "_**Now I know what made Lotus blue**_."\
> (Yes, I know &mdash; **_Otis_** but, in earnest, I was pretty sure that _Lotus_ until [proof](https://en.wikipedia.org/wiki/Now_I_Know_What_Made_Otis_Blue)<sup>&thinsp;<b>W</b></sup>. This should suffice to demonstrate my involvement.)

______\
 🔚 &nbsp;🌘 kyriosity 2023-2025 ..


