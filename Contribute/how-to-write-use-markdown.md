---
title: Jak używać języka Markdown do tworzenia zawartości witryny Docs
description: Ten artykuł zawiera podstawy i informacje referencyjne dotyczące języka znaczników Markdown używanego do pisania artykułów w witrynie docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 07/13/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 96d00abc052c3b23ca62201dccdbe590a927e72d
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="de459-103">Jak używać języka Markdown do tworzenia zawartości witryny Docs</span><span class="sxs-lookup"><span data-stu-id="de459-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="de459-104">Artykuły w witrynie docs.microsoft.com są pisane w prostym języku znaczników o nazwie [Markdown](https://daringfireball.net/projects/markdown/), który jest łatwy do czytania i do nauczenia się.</span><span class="sxs-lookup"><span data-stu-id="de459-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="de459-105">Z tego względu stał się on szybko branżowym standardem.</span><span class="sxs-lookup"><span data-stu-id="de459-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="de459-106">Ponieważ zawartość witryny Docs jest przechowywana w serwisie GitHub, może korzystać z nadzbioru znaczników Markdown o nazwie [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), który oferuje dodatkowe funkcje spełniające typowe potrzeby związane z formatowaniem.</span><span class="sxs-lookup"><span data-stu-id="de459-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="de459-107">Ponadto platforma Open Publishing Services (OPS) implementuje język DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="de459-107">Additionally, Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="de459-108">Język DFM jest w wysokim stopniu zgodny z językiem GitHub Flavored Markdown (GFM), dodając funkcjonalność włączania funkcji specyficznych dla dokumentów.</span><span class="sxs-lookup"><span data-stu-id="de459-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="de459-109">Podstawy języka Markdown</span><span class="sxs-lookup"><span data-stu-id="de459-109">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="de459-110">Nagłówki</span><span class="sxs-lookup"><span data-stu-id="de459-110">Headings</span></span>

<span data-ttu-id="de459-111">Aby utworzyć nagłówek, użyj znaku skrótu (#) w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="de459-111">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="de459-112">Tekst pogrubiony i kursywa</span><span class="sxs-lookup"><span data-stu-id="de459-112">Bold and italic text</span></span>

<span data-ttu-id="de459-113">Aby sformatować tekst jako **pogrubiony**, umieść go między podwójnymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="de459-113">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="de459-114">Aby sformatować tekst jako *kursywę*, umieść go między pojedynczymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="de459-114">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="de459-115">Aby sformatować tekst jako ***pogrubiony i kursywę***, umieść go między potrójnymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="de459-115">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="de459-116">Listy</span><span class="sxs-lookup"><span data-stu-id="de459-116">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="de459-117">Listy nieuporządkowane</span><span class="sxs-lookup"><span data-stu-id="de459-117">Unordered list</span></span>

<span data-ttu-id="de459-118">Aby sformatować listę nieuporządkowaną/punktowaną, można użyć gwiazdek lub myślników.</span><span class="sxs-lookup"><span data-stu-id="de459-118">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="de459-119">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="de459-119">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="de459-120">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="de459-120">will be rendered as:</span></span>

- <span data-ttu-id="de459-121">Element listy 1</span><span class="sxs-lookup"><span data-stu-id="de459-121">List item 1</span></span>
- <span data-ttu-id="de459-122">Element listy 2</span><span class="sxs-lookup"><span data-stu-id="de459-122">List item 2</span></span>
- <span data-ttu-id="de459-123">Element listy 3</span><span class="sxs-lookup"><span data-stu-id="de459-123">List item 3</span></span>

<span data-ttu-id="de459-124">Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy.</span><span class="sxs-lookup"><span data-stu-id="de459-124">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="de459-125">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="de459-125">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="de459-126">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="de459-126">will be rendered as:</span></span>

- <span data-ttu-id="de459-127">Element listy 1</span><span class="sxs-lookup"><span data-stu-id="de459-127">List item 1</span></span>
  - <span data-ttu-id="de459-128">Element listy A</span><span class="sxs-lookup"><span data-stu-id="de459-128">List item A</span></span>
  - <span data-ttu-id="de459-129">Element listy B</span><span class="sxs-lookup"><span data-stu-id="de459-129">List item B</span></span>
- <span data-ttu-id="de459-130">Element listy 2</span><span class="sxs-lookup"><span data-stu-id="de459-130">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="de459-131">Lista uporządkowana</span><span class="sxs-lookup"><span data-stu-id="de459-131">Ordered list</span></span>

<span data-ttu-id="de459-132">Aby sformatować listę uporządkowaną/zawierającą kroki w kolejności ich wykonywania, należy użyć odpowiednich numerów.</span><span class="sxs-lookup"><span data-stu-id="de459-132">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="de459-133">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="de459-133">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="de459-134">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="de459-134">will be rendered as:</span></span>

1. <span data-ttu-id="de459-135">Pierwsza instrukcja</span><span class="sxs-lookup"><span data-stu-id="de459-135">First instruction</span></span>
2. <span data-ttu-id="de459-136">Druga instrukcja</span><span class="sxs-lookup"><span data-stu-id="de459-136">Second instruction</span></span>
3. <span data-ttu-id="de459-137">Trzecia instrukcja</span><span class="sxs-lookup"><span data-stu-id="de459-137">Third instruction</span></span>

<span data-ttu-id="de459-138">Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy.</span><span class="sxs-lookup"><span data-stu-id="de459-138">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="de459-139">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="de459-139">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="de459-140">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="de459-140">will be rendered as:</span></span>

1. <span data-ttu-id="de459-141">Pierwsza instrukcja</span><span class="sxs-lookup"><span data-stu-id="de459-141">First instruction</span></span>
    1. <span data-ttu-id="de459-142">Instrukcja podrzędna</span><span class="sxs-lookup"><span data-stu-id="de459-142">Sub-instruction</span></span>
    2. <span data-ttu-id="de459-143">Instrukcja podrzędna</span><span class="sxs-lookup"><span data-stu-id="de459-143">Sub-instruction</span></span>
2. <span data-ttu-id="de459-144">Druga instrukcja</span><span class="sxs-lookup"><span data-stu-id="de459-144">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="de459-145">tabelami</span><span class="sxs-lookup"><span data-stu-id="de459-145">Tables</span></span>

<span data-ttu-id="de459-146">Tabele nie są częścią podstawowej specyfikacji języka Markdown, ale są obsługiwane przez język GFM.</span><span class="sxs-lookup"><span data-stu-id="de459-146">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="de459-147">Tabele możesz tworzyć przy użyciu znaków kreski pionowej (|) i łącznika (-).</span><span class="sxs-lookup"><span data-stu-id="de459-147">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="de459-148">Łączniki tworzą nagłówki poszczególnych kolumn, a kreski pionowe rozdzielają kolumny.</span><span class="sxs-lookup"><span data-stu-id="de459-148">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="de459-149">Aby tabela była poprawnie renderowana, dodaj przed nią pusty wiersz.</span><span class="sxs-lookup"><span data-stu-id="de459-149">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="de459-150">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="de459-150">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="de459-151">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="de459-151">will be rendered as:</span></span>

| <span data-ttu-id="de459-152">Zabawa</span><span class="sxs-lookup"><span data-stu-id="de459-152">Fun</span></span>                  | <span data-ttu-id="de459-153">z</span><span class="sxs-lookup"><span data-stu-id="de459-153">With</span></span>                 | <span data-ttu-id="de459-154">tabelami</span><span class="sxs-lookup"><span data-stu-id="de459-154">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="de459-155">kolumna wyrównana do lewej</span><span class="sxs-lookup"><span data-stu-id="de459-155">left-aligned column</span></span>  | <span data-ttu-id="de459-156">kolumna wyrównana do prawej</span><span class="sxs-lookup"><span data-stu-id="de459-156">right-aligned column</span></span> | <span data-ttu-id="de459-157">kolumna wyśrodkowana</span><span class="sxs-lookup"><span data-stu-id="de459-157">centered column</span></span> |
| <span data-ttu-id="de459-158">100 USD</span><span class="sxs-lookup"><span data-stu-id="de459-158">$100</span></span>                 | <span data-ttu-id="de459-159">100 USD</span><span class="sxs-lookup"><span data-stu-id="de459-159">$100</span></span>                 | <span data-ttu-id="de459-160">100 USD</span><span class="sxs-lookup"><span data-stu-id="de459-160">$100</span></span>            |
| <span data-ttu-id="de459-161">10 USD</span><span class="sxs-lookup"><span data-stu-id="de459-161">$10</span></span>                  | <span data-ttu-id="de459-162">10 USD</span><span class="sxs-lookup"><span data-stu-id="de459-162">$10</span></span>                  | <span data-ttu-id="de459-163">10 USD</span><span class="sxs-lookup"><span data-stu-id="de459-163">$10</span></span>             |
| <span data-ttu-id="de459-164">1 USD</span><span class="sxs-lookup"><span data-stu-id="de459-164">$1</span></span>                   | <span data-ttu-id="de459-165">1 USD</span><span class="sxs-lookup"><span data-stu-id="de459-165">$1</span></span>                   | <span data-ttu-id="de459-166">1 USD</span><span class="sxs-lookup"><span data-stu-id="de459-166">$1</span></span>              |

<span data-ttu-id="de459-167">Więcej informacji na temat tworzenia tabel można znaleźć w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="de459-167">For more information on creating tables, see:</span></span>

- <span data-ttu-id="de459-168">Opis [funkcji zawijania tabel](#table-wrapping) języka DFM, która może ułatwić formatowanie szerokich tabel</span><span class="sxs-lookup"><span data-stu-id="de459-168">The DFM [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="de459-169">Artykuł [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/) (Organizowanie informacji przy użyciu tabel) w serwisie GitHub</span><span class="sxs-lookup"><span data-stu-id="de459-169">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="de459-170">Aplikacja internetowa [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="de459-170">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- <span data-ttu-id="de459-171">[Markdown Cheatsheet, autor: Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Ściągawka dotycząca języka Markdown)</span><span class="sxs-lookup"><span data-stu-id="de459-171">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)</span></span>
- [<span data-ttu-id="de459-172">Markdown Extra, autor: Michel Fortin</span><span class="sxs-lookup"><span data-stu-id="de459-172">Michel Fortin's Markdown Extra</span></span>](https://michelf.ca/projects/php-markdown/extra/#table)
- [<span data-ttu-id="de459-173">Konwertowanie tabel HTML na znaczniki języka Markdown</span><span class="sxs-lookup"><span data-stu-id="de459-173">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="de459-174">Linki</span><span class="sxs-lookup"><span data-stu-id="de459-174">Links</span></span>

<span data-ttu-id="de459-175">Składnia języka Markdown dla linku śródwierszowego składa się z części `[link text]`, czyli tekstu do uwzględnienia w hiperlinku, oraz następującej po niej części `(file-name.md)`, czyli adresu URL lub nazwy pliku dołączanego przy użyciu linku:</span><span class="sxs-lookup"><span data-stu-id="de459-175">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="de459-176">Więcej informacji na temat łączenia zawierają następujące zasoby:</span><span class="sxs-lookup"><span data-stu-id="de459-176">For more information on linking, see:</span></span>

- <span data-ttu-id="de459-177">[Przewodnik po składni języka Markdown](https://daringfireball.net/projects/markdown/syntax#link) (szczegóły dotyczące obsługi podstawowego łączenia w języku Markdown).</span><span class="sxs-lookup"><span data-stu-id="de459-177">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="de459-178">Sekcja [Linki](how-to-write-links.md) tego przewodnika (szczegóły dodatkowej składni łączenia oferowanej przez język DFM).</span><span class="sxs-lookup"><span data-stu-id="de459-178">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that DFM provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="de459-179">Fragmenty kodu</span><span class="sxs-lookup"><span data-stu-id="de459-179">Code snippets</span></span>

<span data-ttu-id="de459-180">Język Markdown obsługuje umieszczanie fragmentów kodu jako śródwierszowych w zdaniu oraz jako oddzielnego, „ogrodzonego” bloku między zdaniami.</span><span class="sxs-lookup"><span data-stu-id="de459-180">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="de459-181">Szczegóły znajdziesz w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="de459-181">For details, see:</span></span>

- [<span data-ttu-id="de459-182">Natywna obsługa bloków kodu w języku Markdown</span><span class="sxs-lookup"><span data-stu-id="de459-182">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="de459-183">Obsługa ogradzania kodu i wyróżniania składni w rozwiązaniu GFM</span><span class="sxs-lookup"><span data-stu-id="de459-183">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="de459-184">Ogrodzone bloki kodu to prosty sposób włączania wyróżniania składni wybranych fragmentów kodu.</span><span class="sxs-lookup"><span data-stu-id="de459-184">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="de459-185">Ogólny format ogrodzonych bloków kodu to:</span><span class="sxs-lookup"><span data-stu-id="de459-185">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="de459-186">Alias po trzech początkowych znakach „\`” definiuje wyróżnianie składni do użycia.</span><span class="sxs-lookup"><span data-stu-id="de459-186">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="de459-187">Poniżej przedstawiono listę języków programowania najczęściej używanych w zawartości witryny Docs oraz odpowiadających im etykiet:</span><span class="sxs-lookup"><span data-stu-id="de459-187">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="de459-188">Te języki obsługują przyjazne nazwy i w większości obsługują wyróżnianie składni.</span><span class="sxs-lookup"><span data-stu-id="de459-188">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="de459-189">Nazwa</span><span class="sxs-lookup"><span data-stu-id="de459-189">Name</span></span>|<span data-ttu-id="de459-190">Etykieta języka Markdown</span><span class="sxs-lookup"><span data-stu-id="de459-190">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="de459-191">Konsola .NET</span><span class="sxs-lookup"><span data-stu-id="de459-191">.NET Console</span></span>|<span data-ttu-id="de459-192">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="de459-192">dotnetcli</span></span>|
|<span data-ttu-id="de459-193">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="de459-193">ASP.NET (C#)</span></span>|<span data-ttu-id="de459-194">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="de459-194">aspx-csharp</span></span>|
|<span data-ttu-id="de459-195">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="de459-195">ASP.NET (VB)</span></span>|<span data-ttu-id="de459-196">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="de459-196">aspx-vb</span></span>|
|<span data-ttu-id="de459-197">AzCopy</span><span class="sxs-lookup"><span data-stu-id="de459-197">AzCopy</span></span>|<span data-ttu-id="de459-198">azcopy</span><span class="sxs-lookup"><span data-stu-id="de459-198">azcopy</span></span>|
|<span data-ttu-id="de459-199">Interfejs wiersza polecenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="de459-199">Azure CLI</span></span>|<span data-ttu-id="de459-200">azurecli</span><span class="sxs-lookup"><span data-stu-id="de459-200">azurecli</span></span>|
|<span data-ttu-id="de459-201">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="de459-201">Azure PowerShell</span></span>|<span data-ttu-id="de459-202">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="de459-202">azurepowershell</span></span>|
|<span data-ttu-id="de459-203">C++</span><span class="sxs-lookup"><span data-stu-id="de459-203">C++</span></span>|<span data-ttu-id="de459-204">cpp</span><span class="sxs-lookup"><span data-stu-id="de459-204">cpp</span></span>|
|<span data-ttu-id="de459-205">C++/CX</span><span class="sxs-lookup"><span data-stu-id="de459-205">C++/CX</span></span>|<span data-ttu-id="de459-206">cppcx</span><span class="sxs-lookup"><span data-stu-id="de459-206">cppcx</span></span>|
|<span data-ttu-id="de459-207">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="de459-207">C++/WinRT</span></span>|<span data-ttu-id="de459-208">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="de459-208">cppwinrt</span></span>|
|<span data-ttu-id="de459-209">C#</span><span class="sxs-lookup"><span data-stu-id="de459-209">C#</span></span>|<span data-ttu-id="de459-210">csharp</span><span class="sxs-lookup"><span data-stu-id="de459-210">csharp</span></span>|
|<span data-ttu-id="de459-211">CSHTML</span><span class="sxs-lookup"><span data-stu-id="de459-211">CSHTML</span></span>|<span data-ttu-id="de459-212">cshtml</span><span class="sxs-lookup"><span data-stu-id="de459-212">cshtml</span></span>|
|<span data-ttu-id="de459-213">DAX</span><span class="sxs-lookup"><span data-stu-id="de459-213">DAX</span></span>|<span data-ttu-id="de459-214">dax</span><span class="sxs-lookup"><span data-stu-id="de459-214">dax</span></span>|
|<span data-ttu-id="de459-215">F#</span><span class="sxs-lookup"><span data-stu-id="de459-215">F#</span></span>|<span data-ttu-id="de459-216">fsharp</span><span class="sxs-lookup"><span data-stu-id="de459-216">fsharp</span></span>|
|<span data-ttu-id="de459-217">Go</span><span class="sxs-lookup"><span data-stu-id="de459-217">Go</span></span>|<span data-ttu-id="de459-218">go</span><span class="sxs-lookup"><span data-stu-id="de459-218">go</span></span>|
|<span data-ttu-id="de459-219">HTML</span><span class="sxs-lookup"><span data-stu-id="de459-219">HTML</span></span>|<span data-ttu-id="de459-220">html</span><span class="sxs-lookup"><span data-stu-id="de459-220">html</span></span>|
|<span data-ttu-id="de459-221">HTTP</span><span class="sxs-lookup"><span data-stu-id="de459-221">HTTP</span></span>|<span data-ttu-id="de459-222">http</span><span class="sxs-lookup"><span data-stu-id="de459-222">http</span></span>|
|<span data-ttu-id="de459-223">Java</span><span class="sxs-lookup"><span data-stu-id="de459-223">Java</span></span>|<span data-ttu-id="de459-224">java</span><span class="sxs-lookup"><span data-stu-id="de459-224">java</span></span>|
|<span data-ttu-id="de459-225">JavaScript</span><span class="sxs-lookup"><span data-stu-id="de459-225">JavaScript</span></span>|<span data-ttu-id="de459-226">javascript</span><span class="sxs-lookup"><span data-stu-id="de459-226">javascript</span></span>|
|<span data-ttu-id="de459-227">JSON</span><span class="sxs-lookup"><span data-stu-id="de459-227">JSON</span></span>|<span data-ttu-id="de459-228">json</span><span class="sxs-lookup"><span data-stu-id="de459-228">json</span></span>|
|<span data-ttu-id="de459-229">Znaczniki języka Markdown</span><span class="sxs-lookup"><span data-stu-id="de459-229">Markdown</span></span>|<span data-ttu-id="de459-230">md</span><span class="sxs-lookup"><span data-stu-id="de459-230">md</span></span>|
|<span data-ttu-id="de459-231">NodeJS</span><span class="sxs-lookup"><span data-stu-id="de459-231">NodeJS</span></span>|<span data-ttu-id="de459-232">nodejs</span><span class="sxs-lookup"><span data-stu-id="de459-232">nodejs</span></span>|
|<span data-ttu-id="de459-233">Objective-C</span><span class="sxs-lookup"><span data-stu-id="de459-233">Objective-C</span></span>|<span data-ttu-id="de459-234">objc</span><span class="sxs-lookup"><span data-stu-id="de459-234">objc</span></span>|
|<span data-ttu-id="de459-235">OData</span><span class="sxs-lookup"><span data-stu-id="de459-235">OData</span></span>|<span data-ttu-id="de459-236">odata</span><span class="sxs-lookup"><span data-stu-id="de459-236">odata</span></span>|
|<span data-ttu-id="de459-237">PHP</span><span class="sxs-lookup"><span data-stu-id="de459-237">PHP</span></span>|<span data-ttu-id="de459-238">PHP</span><span class="sxs-lookup"><span data-stu-id="de459-238">php</span></span>|
|<span data-ttu-id="de459-239">PowerApps Formula</span><span class="sxs-lookup"><span data-stu-id="de459-239">Power Apps Formula</span></span>|<span data-ttu-id="de459-240">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="de459-240">powerappsfl</span></span>|
|<span data-ttu-id="de459-241">PowerShell</span><span class="sxs-lookup"><span data-stu-id="de459-241">PowerShell</span></span>|<span data-ttu-id="de459-242">powershell</span><span class="sxs-lookup"><span data-stu-id="de459-242">powershell</span></span>|
|<span data-ttu-id="de459-243">Python</span><span class="sxs-lookup"><span data-stu-id="de459-243">Python</span></span>|<span data-ttu-id="de459-244">python</span><span class="sxs-lookup"><span data-stu-id="de459-244">python</span></span>|
|<span data-ttu-id="de459-245">Q#</span><span class="sxs-lookup"><span data-stu-id="de459-245">Q#</span></span>|<span data-ttu-id="de459-246">qsharp</span><span class="sxs-lookup"><span data-stu-id="de459-246">qsharp</span></span>|
|<span data-ttu-id="de459-247">Ruby</span><span class="sxs-lookup"><span data-stu-id="de459-247">Ruby</span></span>|<span data-ttu-id="de459-248">ruby</span><span class="sxs-lookup"><span data-stu-id="de459-248">ruby</span></span>|
|<span data-ttu-id="de459-249">SQL</span><span class="sxs-lookup"><span data-stu-id="de459-249">SQL</span></span>|<span data-ttu-id="de459-250">sql</span><span class="sxs-lookup"><span data-stu-id="de459-250">sql</span></span>|
|<span data-ttu-id="de459-251">Swift</span><span class="sxs-lookup"><span data-stu-id="de459-251">Swift</span></span>|<span data-ttu-id="de459-252">swift</span><span class="sxs-lookup"><span data-stu-id="de459-252">swift</span></span>|
|<span data-ttu-id="de459-253">TypeScript</span><span class="sxs-lookup"><span data-stu-id="de459-253">TypeScript</span></span>|<span data-ttu-id="de459-254">typescript</span><span class="sxs-lookup"><span data-stu-id="de459-254">typescript</span></span>|
|<span data-ttu-id="de459-255">VB</span><span class="sxs-lookup"><span data-stu-id="de459-255">VB</span></span>|<span data-ttu-id="de459-256">vb</span><span class="sxs-lookup"><span data-stu-id="de459-256">vb</span></span>|
|<span data-ttu-id="de459-257">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="de459-257">VSTS CLI</span></span>|<span data-ttu-id="de459-258">vstscli</span><span class="sxs-lookup"><span data-stu-id="de459-258">vstscli</span></span>|
|<span data-ttu-id="de459-259">XAML</span><span class="sxs-lookup"><span data-stu-id="de459-259">XAML</span></span>|<span data-ttu-id="de459-260">xaml</span><span class="sxs-lookup"><span data-stu-id="de459-260">xaml</span></span>|
|<span data-ttu-id="de459-261">XML</span><span class="sxs-lookup"><span data-stu-id="de459-261">XML</span></span>|<span data-ttu-id="de459-262">xml</span><span class="sxs-lookup"><span data-stu-id="de459-262">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="de459-263">Przykład: C\#</span><span class="sxs-lookup"><span data-stu-id="de459-263">Example: C\#</span></span>

<span data-ttu-id="de459-264">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="de459-264">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="de459-265">__Renderowanie__</span><span class="sxs-lookup"><span data-stu-id="de459-265">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="de459-266">Przykład: SQL</span><span class="sxs-lookup"><span data-stu-id="de459-266">Example: SQL</span></span>

<span data-ttu-id="de459-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="de459-267">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="de459-268">__Renderowanie__</span><span class="sxs-lookup"><span data-stu-id="de459-268">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="de459-269">Niestandardowe rozszerzenia języka Markdown na platformie OPS</span><span class="sxs-lookup"><span data-stu-id="de459-269">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="de459-270">Platforma Open Publishing Services (OPS) umożliwia implementowanie języka „DocFX Flavored Markdown” (DFM) o wysokim stopniu zgodności z językiem GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="de459-270">Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM), which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="de459-271">Język DFM dodaje pewne funkcje za pośrednictwem rozszerzeń języka Markdown.</span><span class="sxs-lookup"><span data-stu-id="de459-271">DFM adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="de459-272">Wybrane artykuły z pełnego podręcznika tworzenia platformy OPS jako takie zostały dołączone do tego przewodnika do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="de459-272">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="de459-273">(Przykład można znaleźć w częściach „Rozszerzenia języków DFM i Markdown” i „Fragmenty kodu” dostępnych w spisie treści).</span><span class="sxs-lookup"><span data-stu-id="de459-273">(For example, see "DFM and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="de459-274">W artykułach z witryny Docs rozwiązanie GFM jest używane na potrzeby większości elementów formatowania artykułów, takich jak akapity, linki, listy i nagłówki.</span><span class="sxs-lookup"><span data-stu-id="de459-274">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="de459-275">W celu skorzystania z bardziej zaawansowanego formatowania można w artykułach użyć funkcji rozwiązania DFM, takich jak:</span><span class="sxs-lookup"><span data-stu-id="de459-275">For richer formatting, articles can use DFM features such as:</span></span>

- <span data-ttu-id="de459-276">Bloki uwag</span><span class="sxs-lookup"><span data-stu-id="de459-276">Note blocks</span></span>
- <span data-ttu-id="de459-277">Operacje dołączania</span><span class="sxs-lookup"><span data-stu-id="de459-277">Includes</span></span>
- <span data-ttu-id="de459-278">Selektory</span><span class="sxs-lookup"><span data-stu-id="de459-278">Selectors</span></span>
- <span data-ttu-id="de459-279">Osadzone filmy wideo</span><span class="sxs-lookup"><span data-stu-id="de459-279">Embedded videos</span></span>
- <span data-ttu-id="de459-280">Fragmenty/przykłady kodu</span><span class="sxs-lookup"><span data-stu-id="de459-280">Code snippets/samples</span></span>

<span data-ttu-id="de459-281">Kompletną listę można znaleźć w częściach „Rozszerzenia języków DFM i Markdown” i „Fragmenty kodu” dostępnych w spisie treści.</span><span class="sxs-lookup"><span data-stu-id="de459-281">For the complete list, refer to "DFM and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="de459-282">Bloki uwag</span><span class="sxs-lookup"><span data-stu-id="de459-282">Note blocks</span></span>

<span data-ttu-id="de459-283">Aby zwrócić uwagę czytelnika na określoną zawartość, można wybrać jeden z czterech typów bloków uwag:</span><span class="sxs-lookup"><span data-stu-id="de459-283">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="de459-284">UWAGA</span><span class="sxs-lookup"><span data-stu-id="de459-284">NOTE</span></span>
- <span data-ttu-id="de459-285">OSTRZEŻENIE</span><span class="sxs-lookup"><span data-stu-id="de459-285">WARNING</span></span>
- <span data-ttu-id="de459-286">PORADA</span><span class="sxs-lookup"><span data-stu-id="de459-286">TIP</span></span>
- <span data-ttu-id="de459-287">WAŻNE</span><span class="sxs-lookup"><span data-stu-id="de459-287">IMPORTANT</span></span>

<span data-ttu-id="de459-288">Ogólnie rzecz biorąc, bloków uwag należy używać oszczędnie, ponieważ mogą zaburzać czytelność artykułu.</span><span class="sxs-lookup"><span data-stu-id="de459-288">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="de459-289">Obsługują one również bloki kodu, obrazy, listy i linki, ale należy starać się, aby były proste i czytelne.</span><span class="sxs-lookup"><span data-stu-id="de459-289">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="de459-290">Operacje dołączania</span><span class="sxs-lookup"><span data-stu-id="de459-290">Includes</span></span>

<span data-ttu-id="de459-291">Jeśli masz pliki tekstu lub obrazów do wielokrotnego użytku, które chcesz dołączyć do plików artykułu, możesz użyć odwołania do pliku dołączania za pomocą funkcji dołączania plików w języku DFM.</span><span class="sxs-lookup"><span data-stu-id="de459-291">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the DFM file include feature.</span></span> <span data-ttu-id="de459-292">Ta funkcja nakazuje platformie OPS dołączenie pliku do pliku artykułu podczas kompilacji, co sprawia, że plik staje się częścią publikowanego artykułu.</span><span class="sxs-lookup"><span data-stu-id="de459-292">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="de459-293">Istnieją trzy typy operacji dołączania, które ułatwiają wielokrotne użycie zawartości:</span><span class="sxs-lookup"><span data-stu-id="de459-293">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="de459-294">Śródwierszowe: wielokrotne użycie typowego fragmentu tekstu jako śródwierszowego w innym zdaniu.</span><span class="sxs-lookup"><span data-stu-id="de459-294">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="de459-295">Blokowe: wielokrotne użycie całego pliku Markdown jako bloku zagnieżdżonego w sekcji artykułu.</span><span class="sxs-lookup"><span data-stu-id="de459-295">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="de459-296">Obraz: jest to standardowa operacja dołączania implementowana w witrynie Docs.</span><span class="sxs-lookup"><span data-stu-id="de459-296">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="de459-297">Śródwierszowe i blokowe operacje dołączania dotyczą prostego pliku Markdown (md).</span><span class="sxs-lookup"><span data-stu-id="de459-297">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="de459-298">Może on zawierać dowolny prawidłowy kod w języku Markdown.</span><span class="sxs-lookup"><span data-stu-id="de459-298">It can contain any valid Markdown.</span></span> <span data-ttu-id="de459-299">Wszystkie dołączane pliki Markdown należy umieścić we [wspólnym podkatalogu `/includes`](git-github-fundamentals.md#includes-subdirectory) w głównym katalogu repozytorium.</span><span class="sxs-lookup"><span data-stu-id="de459-299">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="de459-300">Podczas publikowania artykułu dołączany plik jest płynnie z nim integrowany.</span><span class="sxs-lookup"><span data-stu-id="de459-300">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="de459-301">Poniżej przedstawiono wymagania i uwagi dotyczące operacji dołączania:</span><span class="sxs-lookup"><span data-stu-id="de459-301">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="de459-302">Operacji dołączania należy używać, gdy ten sam tekst ma pojawiać się w wielu artykułach.</span><span class="sxs-lookup"><span data-stu-id="de459-302">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="de459-303">Blokowe operacje dołączania są używane w przypadku znaczących ilości zawartości — akapitu lub dwóch, procedury udostępnianej lub sekcji udostępnianej.</span><span class="sxs-lookup"><span data-stu-id="de459-303">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="de459-304">Nie należy ich używać dla części mniejszych niż zdanie.</span><span class="sxs-lookup"><span data-stu-id="de459-304">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="de459-305">Operacje dołączania nie będą renderowane w renderowanym widoku Twojego artykułu w usłudze GitHub, ponieważ korzystają z rozszerzeń języka DFM.</span><span class="sxs-lookup"><span data-stu-id="de459-305">Includes won't be rendered in the GitHub rendered view of your article, because they rely on DFM extensions.</span></span> <span data-ttu-id="de459-306">Będą one renderowane tylko po publikacji.</span><span class="sxs-lookup"><span data-stu-id="de459-306">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="de459-307">Upewnij się, że cały tekst w operacji dołączania został napisany w postaci kompletnych zdań lub fraz, które nie zależą od poprzedniego ani następującego tekstu w artykule odwołującym się do dołączenia.</span><span class="sxs-lookup"><span data-stu-id="de459-307">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="de459-308">Zignorowanie tej wskazówki spowoduje powstanie w artykule ciągu niemożliwego do przetłumaczenia, który zakłóci spójność zlokalizowanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="de459-308">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="de459-309">Operacji dołączania nie należy osadzać w innych dołączeniach.</span><span class="sxs-lookup"><span data-stu-id="de459-309">Don't embed includes within other includes.</span></span> <span data-ttu-id="de459-310">Nie są one obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="de459-310">They are not supported.</span></span>
- <span data-ttu-id="de459-311">Umieść pliki multimedialne w folderze media, który jest specyficzny dla podkatalogu include — na przykład w folderze `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="de459-311">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="de459-312">Katalog główny względem katalogu multimediów nie powinien zawierać obrazów.</span><span class="sxs-lookup"><span data-stu-id="de459-312">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="de459-313">Jeśli dołączenie nie zawiera obrazów, odpowiadający mu katalog multimediów nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="de459-313">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="de459-314">Podobnie jak w przypadku zwykłych artykułów nie należy udostępniać multimediów między dołączanymi plikami.</span><span class="sxs-lookup"><span data-stu-id="de459-314">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="de459-315">Użyj oddzielnego pliku z unikatową nazwą dla każdego dołączenia i artykułu.</span><span class="sxs-lookup"><span data-stu-id="de459-315">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="de459-316">Plik multimedialny należy przechowywać w folderze media skojarzonym z dołączeniem.</span><span class="sxs-lookup"><span data-stu-id="de459-316">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="de459-317">Nie należy używać dołączenia jako jedynej zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="de459-317">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="de459-318">Operacje dołączania mają stanowić uzupełnienie pozostałej zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="de459-318">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="de459-319">Selektory</span><span class="sxs-lookup"><span data-stu-id="de459-319">Selectors</span></span>

<span data-ttu-id="de459-320">Selektorów należy używać w tworzonych artykułach technicznych z wieloma wariantami tego samego artykułu w celu przedstawienia różnic między implementacjami w ramach różnych technologii lub platform.</span><span class="sxs-lookup"><span data-stu-id="de459-320">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="de459-321">Ma to przeważnie zastosowanie w przypadku mobilnej zawartości platformy dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="de459-321">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="de459-322">Obecnie w języku DFM istnieją dwa różne typy selektorów: pojedynczy selektor i selektor wielokrotny.</span><span class="sxs-lookup"><span data-stu-id="de459-322">There are currently two different types of selectors in DFM, a single selector and a multi-selector.</span></span>

<span data-ttu-id="de459-323">Ponieważ ten sam kod języka Markdown selektora znajduje się w każdym artykule w zaznaczeniu, zalecamy umieszczanie selektora artykułu w dołączeniu.</span><span class="sxs-lookup"><span data-stu-id="de459-323">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="de459-324">Następnie można się odwołać do tego dołączenia we wszystkich artykułach, które używają tego samego selektora.</span><span class="sxs-lookup"><span data-stu-id="de459-324">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="de459-325">Fragmenty kodu</span><span class="sxs-lookup"><span data-stu-id="de459-325">Code snippets</span></span>

<span data-ttu-id="de459-326">Język DFM obsługuje zaawansowane dołączanie kodu do artykułu za pośrednictwem rozszerzenia fragmentu kodu.</span><span class="sxs-lookup"><span data-stu-id="de459-326">DFM supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="de459-327">Oferuje ono zaawansowane możliwości renderowania współpracujące z funkcjami GFM, takie jak wybór języka programowania i kolorowanie składni, oraz użyteczne funkcje, takie jak:</span><span class="sxs-lookup"><span data-stu-id="de459-327">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="de459-328">dołączanie scentralizowanych przykładów/fragmentów kodu z repozytorium zewnętrznego;</span><span class="sxs-lookup"><span data-stu-id="de459-328">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="de459-329">interfejs użytkownika z kartami przedstawiającymi wiele wersji przykładów kodu w różnych językach.</span><span class="sxs-lookup"><span data-stu-id="de459-329">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="de459-330">Problemy i ich rozwiązywanie</span><span class="sxs-lookup"><span data-stu-id="de459-330">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="de459-331">Tekst alternatywny</span><span class="sxs-lookup"><span data-stu-id="de459-331">Alt text</span></span>

<span data-ttu-id="de459-332">Nie można prawidłowo renderować tekstu alternatywnego, który zawiera znaki podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="de459-332">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="de459-333">Na przykład zamiast używać tego:</span><span class="sxs-lookup"><span data-stu-id="de459-333">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="de459-334">Omiń podkreślenia w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="de459-334">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="de459-335">Apostrofy i cudzysłowy</span><span class="sxs-lookup"><span data-stu-id="de459-335">Apostrophes and quotation marks</span></span>

<span data-ttu-id="de459-336">W przypadku kopiowania z programu Word do edytora języka Markdown tekst może zawierać „eleganckie” (zawinięte) apostrofy lub cudzysłowy.</span><span class="sxs-lookup"><span data-stu-id="de459-336">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="de459-337">Należy je zakodować lub zmienić na podstawowe apostrofy lub znaki cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="de459-337">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="de459-338">W przeciwnym razie po opublikowaniu pliku otrzymasz coś takiego: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="de459-338">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="de459-339">Oto sposoby kodowania „eleganckich” wersji tych znaków interpunkcyjnych:</span><span class="sxs-lookup"><span data-stu-id="de459-339">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="de459-340">Lewy cudzysłów (otwierający): `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="de459-340">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="de459-341">Prawy cudzysłów (zamykający): `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="de459-341">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="de459-342">Prawy pojedynczy cudzysłów lub apostrof (zamykający): `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="de459-342">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="de459-343">Lewy pojedynczy cudzysłów (otwierający) (rzadko używany): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="de459-343">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="de459-344">Nawiasy kątowe</span><span class="sxs-lookup"><span data-stu-id="de459-344">Angle brackets</span></span>

<span data-ttu-id="de459-345">Jeśli w tekście (nie kodzie) pliku używasz nawiasów kątowych — na przykład w celu oznaczenia symbolu zastępczego — zakoduj je ręcznie.</span><span class="sxs-lookup"><span data-stu-id="de459-345">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="de459-346">W przeciwnym razie w języku Markdown nawiasy kątowe zostaną potraktowane jak tag HTML.</span><span class="sxs-lookup"><span data-stu-id="de459-346">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="de459-347">Na przykład `<script name>` należy zakodować jako `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="de459-347">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="de459-348">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de459-348">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="de459-349">Zasoby dotyczące języka Markdown</span><span class="sxs-lookup"><span data-stu-id="de459-349">Markdown resources</span></span>

- <span data-ttu-id="de459-350">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Wprowadzenie do języka Markdown)</span><span class="sxs-lookup"><span data-stu-id="de459-350">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="de459-351">Docs Markdown cheat-sheet (Ściągawka dotycząca języka Markdown w witrynie Docs)</span><span class="sxs-lookup"><span data-stu-id="de459-351">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="de459-352">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (Podstawy języka Markdown w serwisie GitHub)</span><span class="sxs-lookup"><span data-stu-id="de459-352">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
