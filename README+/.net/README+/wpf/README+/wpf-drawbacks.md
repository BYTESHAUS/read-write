# WPF &nbsp;&mdash;&nbsp; Drawbacks and lacks

> ### **`WPF`** is a stable, modern, and so far popular platform, alive and well despite numerous sad prognoses.

It remains the number one choice for new desktop applications (of any scale), yet without great add-ins, pivotal improvements, and new cutting-edge parts since its first release.

## "WPF <mark>2.0</mark>" ?

The wide use of WPF from 2006 has accumulated vast expertise, feedback, critique (naming), and [proposals](https://github.com/dotnet/wpf/discussions)<sup>:octocat:</sup>. 
Microsoft resources allow its professionals to transform them into a breaking, cutting-edge version of the subsystem &thinsp;&mdash;&thinsp; not on the horizon in 2024.

Microsoft and the .NET team were more than busy with cross-platform, Web, and mobile solutions, .NET Core, but losing focus on a mainstream product (since it's all right and running) invites competitors to push it away.<sup>🥀</sup>

Since the early 2010s, Microsoft has neither ported nor created any significant proprietary product in full WPF<sup>🏗️</sup>. The legacy of the ecosystem<sup>👜</sup> doesn't excuse this for medium foundations.

&nbsp; &nbsp; <sup>🥀</sup> <samp>A lesson that Microsoft itself taught to others, as recounted in my [Lotus&nbsp;notes](../../../../pencraft/README+/essays/README+/LN-view.md).</samp>\
&nbsp; &nbsp; <sup>🏗️</sup> <samp>Visual Studio 2010, fresh [re-built in WPF]((https://devblogs.microsoft.com/visualstudio/wpf-in-visual-studio-2010-part-1-introduction)<sup>🔗</sup>), 
then supplemented with novel Blend are clear-cut hits  and role models.</samp>\
&nbsp; &nbsp; <sup>👜</sup> <samp>Windows is still much COM, and MS Office means giant stacks of C++ and Objective&nbsp;C, reckless to rewrite.</samp>

## Templating

There's no state-of-the-art MVVM backbone from Microsoft that could spare much dev time and encourage teams to select this subsystem.
Free first-class cliparts, galleries, and libraries of user controls are scattered, if available at all.

Commercial frameworks offer superb high-level boilerplate, but Microsoft could allure even more developers if `New-Project` could propose a template wizard: Editor, Drawing, Studio (code, CAD i.a.), Messenger, etc.

## XAML

### Insufficient element IDs (names)

When a grid is big enough, any insert, delete, or move of a row or column will result in an adjustment of `Grid.Row=".."` or `Grid.Column=".."` in elements.

What if a grid definition could allow `<RowDefinition Id="Total"...` or `<ColumnDefinition Id="Tags"...`, and one could set and forget `<Label Grid.Row="Total" Grid.Column="Tags">Total</Label>`.

### Bulky syntax

XML-based languages are bulky by their origin, and XAML goes even further. Many names and constructs in XAML could drastically shrink but remain readable, as in the following snippet.

<details>
<summary><ins>&nbsp;</inst>Fictitious shortened XAML&nbsp;</ins></summary>

```XAML
<Grid>
   <Grid.Rows>
      <Row Height="Auto" />
      <Row Height="Auto" />
      <Row Height="Auto" />
   </Grid.Rows>
   <Grid.Cols>
      <Col Width="Auto"/>
      <Col Width="*"/>
   </Grid.Cols>
   <Label Grid="1,0">Ja</Label>
   ...
</Grid>
```
</details>


## Converters

### Shortfall

Out-of-the-box converters are occasional and literally undeveloped. 
Not to sound unfounded, but that is what I would expect from subsystem creators ➡️ [Bool-to-Visibility](https://github.com/Kyriosity/use-dev/blob/main/src/TuttiFrutti/WinClay/Converters/bool2viz_improved.md).


### Soft-pedalling of errors

Converters fail silently, covering errors or prompting you to keep the debugger open. The easiest workaround is to reserve a value or UI element ID to indicate errors.

🚧... details to be written ... 🚧

**See further**\
|&thinsp;-&thinsp;- [MVVM](mvvm)

_________\
🔚 .. 2022-2025 ..
