<p dir="rtl">,Junior developer writes poor code<br/>
,advanced one - good code<br/>
,experts write no code<br/>
guru deletes code<br/></p>
<p dir="rtl"><i>Anonymous</i></p>

# `Code` Quality 

<table><tr></tr><tr valign="center"><td width=30%>
  <picture><img src="../../../_rsc/_img/photo/misc/pour_concrete.jpg" alt="&nbsp;pouring concrete" title="&nbsp;Image credit: jkcement.com&#013;&#010;(for illustration purposes only)" /></picture>
</td><td>
<h3>Code is the <mark>cement</mark> of software. Its quality is imperceptible for spectators and doesn't matter much for booths.</h3>
<h3>Still, it ought to be of superior grade for sky-scraping, heavy-duty, or complex constructions — poor quality, as in buildings, leads to menacing cracks.</h3>
</td></tr></table>

## High-quality code

That's <sub>🪳</sub>bug-unfriendly<sub>⛔</sub> 👓reviewed/tested🧪 **`clean code`** that follows acknowledged guidelines (ꜱᴏʟɪᴅ, ᴅʀʏ, ᴋɪꜱꜱ, ...) and also:

+ [x] **reads** in both directions<sup>↔️</sup>,
+ [x] **teaches** techniques and gimmicks,
+ [x] **inspires** to contribute (<ins>rather than to re-implement</ins>).

&nbsp;&nbsp;&nbsp;&nbsp;<sup>↔️</sup> <sub>On-boarding developers can learn the domain from code (sure, not alone), while the domain expert (with some assistance) will grasp the implemented application logic.</sub>

### Re: Bugs 🪳

Bug-**free** code can be bug-**prone**. Code style must be bug-unfriendly to minimize risks of introducing an error by change (regardless of whether unit tests will pick one).

High-quality code shall present

+ syntax that prevents typos<sup>🎼</sup> and mistakes<sup>🥎</sup>,
+ pronounced logical flows (e.g., early returns, shallow enclosures),
+ minimum redundancies and repetitions.

The highest merit is that even a breaking change won't surprise devs and users with unexpected side effects.

Code optimization (deleting redundancies, merging common logic and data, shortening syntax) that retains readability is prizewinning:\
less code gives less soil for bugs.

\___________

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>🎼</sup> <sub>e.g. `String.Empty` instead of `""` and some [C# tricks](../../../.net/README+/cs-hints.md)</sub>\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>🥎</sup> <sub>Plenty of magic strings and numbers, deceptive names, accidental casts, or "ghost" arguments (to name a few).</sub>

### Re: Tests 🧪

Test coverage may (and shall) share realization with or even origin from [Test Driven Development](../../tests/) but is **primarily** intended to examine software mechanically (no matter whether implemented before the subject or postfactum).

Efficient, ample test coverage allows only patching buggy and badly joined applications, while good code doesn't need a whole scale of automated scrutiny: unit, integration, and performance testing.

_Errare humanum est_, and enough quality code allows one to focus tests on ...

* bottlenecks: intricate logic, performance, accuracy,
* subjects of frequent changes,
* dependencies on imports and external parts.

... and get more breath to avoid [tests pitfalls](../../tests/asQA/README+/QA_tests-pitfalls.md).

## Afterword

**1)** Coding isn't a self-contained activity but an ingredient of <sub>[![Arc Deco.](../../../_rsc/_img/ArcDeco/ArcDeco-bar-14px.jpg)](../../../software/ArcDeco/README.md)</sub>&thinsp;, where quality is a motive, derivative, and bonus.

**2)** While design sets formworks of code **concrete**, [coding frames](https://github.com/Kyriosity/use-dev/tree/main/README%2B/frames) reinforce it.

**3)** The traits listed above are NOT acceptance criteria, but utmost aims. Even if your team comes close to them the code won't be a book of design revelation — you still owe quality [documentation](../../docu).

## Moralité

With all that said, why does flawed code prevail and _clean code_ migrate to buzzwords? 

**1.** Poor-quality code is written much faster, cheaper, and without heated debates.<sup>🥴</sup> And as it does the job, counter-arguments fade.

**2.** Benefits of quality code lag for all beneficiaries<sup>:family_man_woman_boy_boy:</sup> and exponentially growing issues from bad software parts.\
The point when controllable chaos goes out of control or a security breach manifests itself may be crucial but will lay far in the next releases.<sup>:parachute:</sup>

**3.** Intention for quality is good. Albeit if efforts aren't complete, deficient code will still come, but with a massive overhead. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>🥴</sup>&nbsp;<sub>Provided one doesn't bother with [development] principles.</sub>\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>:family_man_woman_boy_boy:</sup>&nbsp;<sub>Customers, developers, testers, users, and project organizers.</sub>\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>:parachute:</sup>&nbsp;<sub>When its originators may be safely on other projects, leaving the headache to others.</sub>

Top up with the fact that not every developer self-reflects on "submit and forget" doing, and not every project management will draw a golden section between profanity and academism. 

<table><tr></tr><tr valign="top"><td>

## Appendix. Still mediocre code &nbsp;&mdash;&nbsp; Why&thinsp;?&thinsp;!

Apart from environments where seeds of good code won't bloom<sup>:wilted_flower:</sup> or shall not be planted<sup>:desert:</sup>, even motivated smart teams may not reach high quality in very good conditions with enough resources and freedoms. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>:wilted_flower:</sup>&nbsp;<sub>Budget/time jaws, code conveyors, unsuited teams, bad management, or intentional obfuscation.</sub>\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<sup>:desert:</sup>&nbsp;<sub>Prototypes, stand-alone auxiliaries, temporary solutions.</sub>

Besides _classical_ over-creativity and procrastination, the reasons could be:

+ overweight of formal processes at the expense of design and communication,
+ "egocentrism": low feedback (code review, pair programming, coaching) and reluctance to learn (especially from critique),
+ canceled/postponed iterations/refactoring/cleaning,
+ hesitation in using and contributing to shared code (from team/enterprise foundations up to open source)

Some prominent individuals develop great apps alone and are so good at keeping all details and the whole picture in mind that they don't need and like to lose time with code organization. 
However, this is exceptional and not about enterprise development.

</td><td width="30%">
  <picture><img alt="&nbsp;Stone monolyth" src="../../../_rsc/_img/photo/nat/DerAlteSchwede.jpg" title="Waterfall monolyth again..." /></picture>
</td></tr></table>

🔚 ...🌜2023-2025
