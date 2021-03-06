---
title: "C Keywords"
ms.date: "10/09/2018"
helpviewer_keywords: ["keywords [C]", "redefining keywords", "Microsoft-specific keywords"]
ms.assetid: 2d932335-97bf-45cd-b367-4ae00db0ff42
---
# C Keywords

"Keywords" are words that have special meaning to the C compiler. In translation phases 7 and 8, an identifier cannot have the same spelling and case as a C keyword. (See a description of [translation phases](../preprocessor/phases-of-translation.md) in the *Preprocessor Reference*; for information on identifiers, see [Identifiers](../c-language/c-identifiers.md).) The C language uses the following keywords:

:::row:::
    :::column:::
        **`auto`**<br/>
        **`double`**<br/>
        **`int`**<br/>
        **`struct`**<br/>
        **`break`**<br/>
        **`else`**<br/>
        **`long`**<br/>
        **`switch`**<br/>
    :::column-end:::
    :::column:::
        **`case`**<br/>
        **`enum`**<br/>
        **`register`**<br/>
        **`typedef`**<br/>
        **`char`**<br/>
        **`extern`**<br/>
        **`return`**<br/>
        **`union`**<br/>
    :::column-end:::
    :::column:::
        **`const`**<br/>
        **`float`**<br/>
        **`short`**<br/>
        **`unsigned`**<br/>
        **`continue`**<br/>
        **`for`**<br/>
        **`signed`**<br/>
        **`void`**<br/>
    :::column-end:::
    :::column:::
        **`default`**<br/>
        **`goto`**<br/>
        **`sizeof`**<br/>
        **`volatile`**<br/>
        **`do`**<br/>
        **`if`**<br/>
        **`static`**<br/>
        **`while`**<br/>
    :::column-end:::
:::row-end:::

You can't redefine keywords. However, you can specify text to be substituted for keywords before compilation by using C [preprocessor directives](../preprocessor/preprocessor-directives.md).

**Microsoft Specific**

The ANSI C standard allows identifiers with two leading underscores to be reserved for compiler implementations. Therefore, the Microsoft convention is to precede Microsoft-specific keyword names with double underscores. These words cannot be used as identifier names. For a description of the ANSI rules for naming identifiers, including the use of double underscores, see [Identifiers](../c-language/c-identifiers.md).

The following keywords and special identifiers are recognized by the Microsoft C compiler:

:::row:::
    :::column:::
        **`__asm`**<sup>3</sup><br/>
        **`dllimport`**<sup>2</sup><br/>
        **`__int8`**<sup>3</sup><br/>
        **`naked`**<sup>2</sup><br/>
        **`__based`**<sup>1, 3</sup><br/>
    :::column-end:::
    :::column:::
        **`__except`**<sup>3</sup><br/>
        **`__int16`**<sup>3</sup><br/>
        **`__stdcall`**<sup>3</sup><br/>
        **`__cdecl`**<sup>3</sup><br/>
        **`__fastcall`**<br/>
    :::column-end:::
    :::column:::
        **`__int32`**<sup>3</sup><br/>
        **`thread`**<sup>2</sup><br/>
        **`__declspec`**<sup>3</sup><br/>
        **`__finally`**<sup>3</sup><br/>
        **`__int64`**<sup>3</sup><br/>
    :::column-end:::
    :::column:::
        **`__try`**<sup>3</sup><br/>
        **`dllexport`**<sup>2</sup><br/>
        **`__inline`**<sup>3</sup><br/>
        **`__leave`**<sup>3</sup><br/>
    :::column-end:::
:::row-end:::

<sup>1</sup> The **`__based`** keyword has limited uses for 32-bit and 64-bit target compilations.

<sup>2</sup> These are special identifiers when used with **`__declspec`**; their use in other contexts is not restricted.

<sup>3</sup> For compatibility with previous versions, these keywords are available both with two leading underscores and a single leading underscore when Microsoft extensions are enabled.

Microsoft extensions are enabled by default. To ensure that your programs are fully portable, you can disable Microsoft extensions by specifying the [/Za \(Disable language extensions)](../build/reference/za-ze-disable-language-extensions.md) option during compilation. When you do this, some Microsoft-specific keywords are disabled.

When Microsoft extensions are enabled, you can use the keywords listed above in your programs. For ANSI compliance, most of these keywords are prefaced by a double underscore. The four exceptions, **`dllexport`**, **`dllimport`**, **`naked`**, and **`thread`**, are used only with **`__declspec`** and therefore do not require a leading double underscore. For backward compatibility, single-underscore versions of the rest of the keywords are supported.

**END Microsoft Specific**

## See also

[Elements of C](../c-language/elements-of-c.md)
