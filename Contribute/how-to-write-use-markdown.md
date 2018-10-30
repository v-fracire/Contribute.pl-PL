---
title: Jak używać języka Markdown do tworzenia zawartości witryny Docs
description: Ten artykuł zawiera podstawy i informacje referencyjne dotyczące języka znaczników Markdown używanego do pisania artykułów w witrynie docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: 6bb8a1fa20957512addb07dda0e68abec4b0a83f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805734"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="b6d43-103">Jak używać języka Markdown do tworzenia zawartości witryny Docs</span><span class="sxs-lookup"><span data-stu-id="b6d43-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="b6d43-104">Artykuły w witrynie [docs.microsoft.com](http://docs.microsoft.com) są pisane w prostym języku znaczników o nazwie [Markdown](https://daringfireball.net/projects/markdown/), który jest łatwy do czytania i do nauczenia się.</span><span class="sxs-lookup"><span data-stu-id="b6d43-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="b6d43-105">Z tego względu stał się on szybko branżowym standardem.</span><span class="sxs-lookup"><span data-stu-id="b6d43-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="b6d43-106">Ponieważ zawartość witryny Docs jest przechowywana w serwisie GitHub, może korzystać z nadzbioru znaczników Markdown o nazwie [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), który oferuje dodatkowe funkcje spełniające typowe potrzeby związane z formatowaniem.</span><span class="sxs-lookup"><span data-stu-id="b6d43-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="b6d43-107">Ponadto platforma Open Publishing Services (OPS) implementuje parser języka Markdown o nazwie Markdig.</span><span class="sxs-lookup"><span data-stu-id="b6d43-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="b6d43-108">Parser Markdig jest w wysokim stopniu zgodny z językiem GFM, dodając funkcjonalność włączania funkcji specyficznych dla dokumentów.</span><span class="sxs-lookup"><span data-stu-id="b6d43-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="b6d43-109">Parser Markdig jest szybkim, wydajnym, zgodnym ze składnią CommonMark, rozszerzalnym procesorem języka Markdown dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="b6d43-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="b6d43-110">Lepsze wsparcie społeczności</span><span class="sxs-lookup"><span data-stu-id="b6d43-110">Better community support</span></span>
* <span data-ttu-id="b6d43-111">Lepsza obsługa standardów</span><span class="sxs-lookup"><span data-stu-id="b6d43-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="b6d43-112">Podstawy języka Markdown</span><span class="sxs-lookup"><span data-stu-id="b6d43-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="b6d43-113">Nagłówki</span><span class="sxs-lookup"><span data-stu-id="b6d43-113">Headings</span></span>

<span data-ttu-id="b6d43-114">Aby utworzyć nagłówek, użyj znaku skrótu (#) w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="b6d43-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="b6d43-115">Tekst pogrubiony i kursywa</span><span class="sxs-lookup"><span data-stu-id="b6d43-115">Bold and italic text</span></span>

<span data-ttu-id="b6d43-116">Aby sformatować tekst jako **pogrubiony**, umieść go między podwójnymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="b6d43-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="b6d43-117">Aby sformatować tekst jako *kursywę*, umieść go między pojedynczymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="b6d43-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="b6d43-118">Aby sformatować tekst jako ***pogrubiony i kursywę***, umieść go między potrójnymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="b6d43-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="b6d43-119">Listy</span><span class="sxs-lookup"><span data-stu-id="b6d43-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="b6d43-120">Listy nieuporządkowane</span><span class="sxs-lookup"><span data-stu-id="b6d43-120">Unordered list</span></span>

<span data-ttu-id="b6d43-121">Aby sformatować listę nieuporządkowaną/punktowaną, można użyć gwiazdek lub myślników.</span><span class="sxs-lookup"><span data-stu-id="b6d43-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="b6d43-122">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="b6d43-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="b6d43-123">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="b6d43-123">will be rendered as:</span></span>

- <span data-ttu-id="b6d43-124">Element listy 1</span><span class="sxs-lookup"><span data-stu-id="b6d43-124">List item 1</span></span>
- <span data-ttu-id="b6d43-125">Element listy 2</span><span class="sxs-lookup"><span data-stu-id="b6d43-125">List item 2</span></span>
- <span data-ttu-id="b6d43-126">Element listy 3</span><span class="sxs-lookup"><span data-stu-id="b6d43-126">List item 3</span></span>

<span data-ttu-id="b6d43-127">Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy.</span><span class="sxs-lookup"><span data-stu-id="b6d43-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="b6d43-128">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="b6d43-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="b6d43-129">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="b6d43-129">will be rendered as:</span></span>

- <span data-ttu-id="b6d43-130">Element listy 1</span><span class="sxs-lookup"><span data-stu-id="b6d43-130">List item 1</span></span>
  - <span data-ttu-id="b6d43-131">Element listy A</span><span class="sxs-lookup"><span data-stu-id="b6d43-131">List item A</span></span>
  - <span data-ttu-id="b6d43-132">Element listy B</span><span class="sxs-lookup"><span data-stu-id="b6d43-132">List item B</span></span>
- <span data-ttu-id="b6d43-133">Element listy 2</span><span class="sxs-lookup"><span data-stu-id="b6d43-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="b6d43-134">Lista uporządkowana</span><span class="sxs-lookup"><span data-stu-id="b6d43-134">Ordered list</span></span>

<span data-ttu-id="b6d43-135">Aby sformatować listę uporządkowaną/zawierającą kroki w kolejności ich wykonywania, należy użyć odpowiednich numerów.</span><span class="sxs-lookup"><span data-stu-id="b6d43-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="b6d43-136">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="b6d43-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="b6d43-137">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="b6d43-137">will be rendered as:</span></span>

1. <span data-ttu-id="b6d43-138">Pierwsza instrukcja</span><span class="sxs-lookup"><span data-stu-id="b6d43-138">First instruction</span></span>
2. <span data-ttu-id="b6d43-139">Druga instrukcja</span><span class="sxs-lookup"><span data-stu-id="b6d43-139">Second instruction</span></span>
3. <span data-ttu-id="b6d43-140">Trzecia instrukcja</span><span class="sxs-lookup"><span data-stu-id="b6d43-140">Third instruction</span></span>

<span data-ttu-id="b6d43-141">Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy.</span><span class="sxs-lookup"><span data-stu-id="b6d43-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="b6d43-142">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="b6d43-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="b6d43-143">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="b6d43-143">will be rendered as:</span></span>

1. <span data-ttu-id="b6d43-144">Pierwsza instrukcja</span><span class="sxs-lookup"><span data-stu-id="b6d43-144">First instruction</span></span>
   1. <span data-ttu-id="b6d43-145">Instrukcja podrzędna</span><span class="sxs-lookup"><span data-stu-id="b6d43-145">Sub-instruction</span></span>
   2. <span data-ttu-id="b6d43-146">Instrukcja podrzędna</span><span class="sxs-lookup"><span data-stu-id="b6d43-146">Sub-instruction</span></span>
2. <span data-ttu-id="b6d43-147">Druga instrukcja</span><span class="sxs-lookup"><span data-stu-id="b6d43-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="b6d43-148">tabelami</span><span class="sxs-lookup"><span data-stu-id="b6d43-148">Tables</span></span>

<span data-ttu-id="b6d43-149">Tabele nie są częścią podstawowej specyfikacji języka Markdown, ale są obsługiwane przez język GFM.</span><span class="sxs-lookup"><span data-stu-id="b6d43-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="b6d43-150">Tabele możesz tworzyć przy użyciu znaków kreski pionowej (|) i łącznika (-).</span><span class="sxs-lookup"><span data-stu-id="b6d43-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="b6d43-151">Łączniki tworzą nagłówki poszczególnych kolumn, a kreski pionowe rozdzielają kolumny.</span><span class="sxs-lookup"><span data-stu-id="b6d43-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="b6d43-152">Aby tabela była poprawnie renderowana, dodaj przed nią pusty wiersz.</span><span class="sxs-lookup"><span data-stu-id="b6d43-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="b6d43-153">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="b6d43-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="b6d43-154">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="b6d43-154">will be rendered as:</span></span>

| <span data-ttu-id="b6d43-155">Zabawa</span><span class="sxs-lookup"><span data-stu-id="b6d43-155">Fun</span></span>                  | <span data-ttu-id="b6d43-156">z</span><span class="sxs-lookup"><span data-stu-id="b6d43-156">With</span></span>                 | <span data-ttu-id="b6d43-157">tabelami</span><span class="sxs-lookup"><span data-stu-id="b6d43-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="b6d43-158">kolumna wyrównana do lewej</span><span class="sxs-lookup"><span data-stu-id="b6d43-158">left-aligned column</span></span>  | <span data-ttu-id="b6d43-159">kolumna wyrównana do prawej</span><span class="sxs-lookup"><span data-stu-id="b6d43-159">right-aligned column</span></span> | <span data-ttu-id="b6d43-160">kolumna wyśrodkowana</span><span class="sxs-lookup"><span data-stu-id="b6d43-160">centered column</span></span> |
| <span data-ttu-id="b6d43-161">100 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-161">$100</span></span>                 | <span data-ttu-id="b6d43-162">100 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-162">$100</span></span>                 | <span data-ttu-id="b6d43-163">100 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-163">$100</span></span>            |
| <span data-ttu-id="b6d43-164">10 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-164">$10</span></span>                  | <span data-ttu-id="b6d43-165">10 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-165">$10</span></span>                  | <span data-ttu-id="b6d43-166">10 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-166">$10</span></span>             |
| <span data-ttu-id="b6d43-167">1 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-167">$1</span></span>                   | <span data-ttu-id="b6d43-168">1 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-168">$1</span></span>                   | <span data-ttu-id="b6d43-169">1 USD</span><span class="sxs-lookup"><span data-stu-id="b6d43-169">$1</span></span>              |

<span data-ttu-id="b6d43-170">Więcej informacji na temat tworzenia tabel można znaleźć w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="b6d43-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="b6d43-171">[Funkcja zawijania tabel](#table-wrapping) parsera Markdig, która może ułatwić formatowanie szerokich tabel.</span><span class="sxs-lookup"><span data-stu-id="b6d43-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="b6d43-172">Artykuł [Organizing information with tables (Organizowanie informacji przy użyciu tabel)](https://help.github.com/articles/organizing-information-with-tables/) w usłudze GitHub.</span><span class="sxs-lookup"><span data-stu-id="b6d43-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="b6d43-173">Aplikacja internetowa [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="b6d43-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="b6d43-174">[Markdown Cheatsheet (Ściągawka dotycząca języka Markdown), autor: Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="b6d43-174">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="b6d43-175">[Markdown Extra, autor: Michel Fortin](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="b6d43-175">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="b6d43-176">[Konwertowanie tabel HTML na znaczniki języka Markdown](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="b6d43-176">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="b6d43-177">Linki</span><span class="sxs-lookup"><span data-stu-id="b6d43-177">Links</span></span>

<span data-ttu-id="b6d43-178">Składnia języka Markdown dla linku śródwierszowego składa się z części `[link text]`, czyli tekstu do uwzględnienia w hiperlinku, oraz następującej po niej części `(file-name.md)`, czyli adresu URL lub nazwy pliku dołączanego przy użyciu linku:</span><span class="sxs-lookup"><span data-stu-id="b6d43-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="b6d43-179">Więcej informacji na temat łączenia zawierają następujące zasoby:</span><span class="sxs-lookup"><span data-stu-id="b6d43-179">For more information on linking, see:</span></span>

- <span data-ttu-id="b6d43-180">[Przewodnik po składni języka Markdown](https://daringfireball.net/projects/markdown/syntax#link) (szczegóły dotyczące obsługi podstawowego łączenia w języku Markdown).</span><span class="sxs-lookup"><span data-stu-id="b6d43-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="b6d43-181">Sekcja [Linki](how-to-write-links.md) tego przewodnika (szczegóły dodatkowej składni łączenia oferowanej przez parser Markdig).</span><span class="sxs-lookup"><span data-stu-id="b6d43-181">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="b6d43-182">Fragmenty kodu</span><span class="sxs-lookup"><span data-stu-id="b6d43-182">Code snippets</span></span>

<span data-ttu-id="b6d43-183">Język Markdown obsługuje umieszczanie fragmentów kodu jako śródwierszowych w zdaniu oraz jako oddzielnego, „ogrodzonego” bloku między zdaniami.</span><span class="sxs-lookup"><span data-stu-id="b6d43-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="b6d43-184">Szczegóły znajdziesz w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="b6d43-184">For details, see:</span></span>

- [<span data-ttu-id="b6d43-185">Natywna obsługa bloków kodu w języku Markdown</span><span class="sxs-lookup"><span data-stu-id="b6d43-185">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="b6d43-186">Obsługa ogradzania kodu i wyróżniania składni w rozwiązaniu GFM</span><span class="sxs-lookup"><span data-stu-id="b6d43-186">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="b6d43-187">Ogrodzone bloki kodu to prosty sposób włączania wyróżniania składni wybranych fragmentów kodu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="b6d43-188">Ogólny format ogrodzonych bloków kodu to:</span><span class="sxs-lookup"><span data-stu-id="b6d43-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="b6d43-189">Alias po trzech początkowych znakach „\`” definiuje wyróżnianie składni do użycia.</span><span class="sxs-lookup"><span data-stu-id="b6d43-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="b6d43-190">Poniżej przedstawiono listę języków programowania najczęściej używanych w zawartości witryny Docs oraz odpowiadających im etykiet:</span><span class="sxs-lookup"><span data-stu-id="b6d43-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="b6d43-191">Te języki obsługują przyjazne nazwy i w większości obsługują wyróżnianie składni.</span><span class="sxs-lookup"><span data-stu-id="b6d43-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="b6d43-192">Nazwa</span><span class="sxs-lookup"><span data-stu-id="b6d43-192">Name</span></span>|<span data-ttu-id="b6d43-193">Etykieta języka Markdown</span><span class="sxs-lookup"><span data-stu-id="b6d43-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="b6d43-194">Konsola .NET</span><span class="sxs-lookup"><span data-stu-id="b6d43-194">.NET Console</span></span>|<span data-ttu-id="b6d43-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="b6d43-195">dotnetcli</span></span>|
|<span data-ttu-id="b6d43-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="b6d43-196">ASP.NET (C#)</span></span>|<span data-ttu-id="b6d43-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="b6d43-197">aspx-csharp</span></span>|
|<span data-ttu-id="b6d43-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="b6d43-198">ASP.NET (VB)</span></span>|<span data-ttu-id="b6d43-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="b6d43-199">aspx-vb</span></span>|
|<span data-ttu-id="b6d43-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="b6d43-200">AzCopy</span></span>|<span data-ttu-id="b6d43-201">azcopy</span><span class="sxs-lookup"><span data-stu-id="b6d43-201">azcopy</span></span>|
|<span data-ttu-id="b6d43-202">Interfejs wiersza polecenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="b6d43-202">Azure CLI</span></span>|<span data-ttu-id="b6d43-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="b6d43-203">azurecli</span></span>|
|<span data-ttu-id="b6d43-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6d43-204">Azure PowerShell</span></span>|<span data-ttu-id="b6d43-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="b6d43-205">azurepowershell</span></span>|
|<span data-ttu-id="b6d43-206">C++</span><span class="sxs-lookup"><span data-stu-id="b6d43-206">C++</span></span>|<span data-ttu-id="b6d43-207">cpp</span><span class="sxs-lookup"><span data-stu-id="b6d43-207">cpp</span></span>|
|<span data-ttu-id="b6d43-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="b6d43-208">C++/CX</span></span>|<span data-ttu-id="b6d43-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="b6d43-209">cppcx</span></span>|
|<span data-ttu-id="b6d43-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="b6d43-210">C++/WinRT</span></span>|<span data-ttu-id="b6d43-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="b6d43-211">cppwinrt</span></span>|
|<span data-ttu-id="b6d43-212">C#</span><span class="sxs-lookup"><span data-stu-id="b6d43-212">C#</span></span>|<span data-ttu-id="b6d43-213">csharp</span><span class="sxs-lookup"><span data-stu-id="b6d43-213">csharp</span></span>|
|<span data-ttu-id="b6d43-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="b6d43-214">CSHTML</span></span>|<span data-ttu-id="b6d43-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="b6d43-215">cshtml</span></span>|
|<span data-ttu-id="b6d43-216">DAX</span><span class="sxs-lookup"><span data-stu-id="b6d43-216">DAX</span></span>|<span data-ttu-id="b6d43-217">dax</span><span class="sxs-lookup"><span data-stu-id="b6d43-217">dax</span></span>|
|<span data-ttu-id="b6d43-218">F#</span><span class="sxs-lookup"><span data-stu-id="b6d43-218">F#</span></span>|<span data-ttu-id="b6d43-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="b6d43-219">fsharp</span></span>|
|<span data-ttu-id="b6d43-220">Go</span><span class="sxs-lookup"><span data-stu-id="b6d43-220">Go</span></span>|<span data-ttu-id="b6d43-221">go</span><span class="sxs-lookup"><span data-stu-id="b6d43-221">go</span></span>|
|<span data-ttu-id="b6d43-222">HTML</span><span class="sxs-lookup"><span data-stu-id="b6d43-222">HTML</span></span>|<span data-ttu-id="b6d43-223">html</span><span class="sxs-lookup"><span data-stu-id="b6d43-223">html</span></span>|
|<span data-ttu-id="b6d43-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="b6d43-224">HTTP</span></span>|<span data-ttu-id="b6d43-225">http</span><span class="sxs-lookup"><span data-stu-id="b6d43-225">http</span></span>|
|<span data-ttu-id="b6d43-226">Java</span><span class="sxs-lookup"><span data-stu-id="b6d43-226">Java</span></span>|<span data-ttu-id="b6d43-227">java</span><span class="sxs-lookup"><span data-stu-id="b6d43-227">java</span></span>|
|<span data-ttu-id="b6d43-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b6d43-228">JavaScript</span></span>|<span data-ttu-id="b6d43-229">javascript</span><span class="sxs-lookup"><span data-stu-id="b6d43-229">javascript</span></span>|
|<span data-ttu-id="b6d43-230">JSON</span><span class="sxs-lookup"><span data-stu-id="b6d43-230">JSON</span></span>|<span data-ttu-id="b6d43-231">json</span><span class="sxs-lookup"><span data-stu-id="b6d43-231">json</span></span>|
|<span data-ttu-id="b6d43-232">Znaczniki języka Markdown</span><span class="sxs-lookup"><span data-stu-id="b6d43-232">Markdown</span></span>|<span data-ttu-id="b6d43-233">md</span><span class="sxs-lookup"><span data-stu-id="b6d43-233">md</span></span>|
|<span data-ttu-id="b6d43-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="b6d43-234">NodeJS</span></span>|<span data-ttu-id="b6d43-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="b6d43-235">nodejs</span></span>|
|<span data-ttu-id="b6d43-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="b6d43-236">Objective-C</span></span>|<span data-ttu-id="b6d43-237">objc</span><span class="sxs-lookup"><span data-stu-id="b6d43-237">objc</span></span>|
|<span data-ttu-id="b6d43-238">OData</span><span class="sxs-lookup"><span data-stu-id="b6d43-238">OData</span></span>|<span data-ttu-id="b6d43-239">odata</span><span class="sxs-lookup"><span data-stu-id="b6d43-239">odata</span></span>|
|<span data-ttu-id="b6d43-240">PHP</span><span class="sxs-lookup"><span data-stu-id="b6d43-240">PHP</span></span>|<span data-ttu-id="b6d43-241">PHP</span><span class="sxs-lookup"><span data-stu-id="b6d43-241">php</span></span>|
|<span data-ttu-id="b6d43-242">PowerApps Formula</span><span class="sxs-lookup"><span data-stu-id="b6d43-242">Power Apps Formula</span></span>|<span data-ttu-id="b6d43-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="b6d43-243">powerappsfl</span></span>|
|<span data-ttu-id="b6d43-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b6d43-244">PowerShell</span></span>|<span data-ttu-id="b6d43-245">powershell</span><span class="sxs-lookup"><span data-stu-id="b6d43-245">powershell</span></span>|
|<span data-ttu-id="b6d43-246">Python</span><span class="sxs-lookup"><span data-stu-id="b6d43-246">Python</span></span>|<span data-ttu-id="b6d43-247">python</span><span class="sxs-lookup"><span data-stu-id="b6d43-247">python</span></span>|
|<span data-ttu-id="b6d43-248">Q#</span><span class="sxs-lookup"><span data-stu-id="b6d43-248">Q#</span></span>|<span data-ttu-id="b6d43-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="b6d43-249">qsharp</span></span>|
|<span data-ttu-id="b6d43-250">R</span><span class="sxs-lookup"><span data-stu-id="b6d43-250">R</span></span>|<span data-ttu-id="b6d43-251">r</span><span class="sxs-lookup"><span data-stu-id="b6d43-251">r</span></span>|
|<span data-ttu-id="b6d43-252">Ruby</span><span class="sxs-lookup"><span data-stu-id="b6d43-252">Ruby</span></span>|<span data-ttu-id="b6d43-253">ruby</span><span class="sxs-lookup"><span data-stu-id="b6d43-253">ruby</span></span>|
|<span data-ttu-id="b6d43-254">SQL</span><span class="sxs-lookup"><span data-stu-id="b6d43-254">SQL</span></span>|<span data-ttu-id="b6d43-255">sql</span><span class="sxs-lookup"><span data-stu-id="b6d43-255">sql</span></span>|
|<span data-ttu-id="b6d43-256">Swift</span><span class="sxs-lookup"><span data-stu-id="b6d43-256">Swift</span></span>|<span data-ttu-id="b6d43-257">swift</span><span class="sxs-lookup"><span data-stu-id="b6d43-257">swift</span></span>|
|<span data-ttu-id="b6d43-258">TypeScript</span><span class="sxs-lookup"><span data-stu-id="b6d43-258">TypeScript</span></span>|<span data-ttu-id="b6d43-259">typescript</span><span class="sxs-lookup"><span data-stu-id="b6d43-259">typescript</span></span>|
|<span data-ttu-id="b6d43-260">VB</span><span class="sxs-lookup"><span data-stu-id="b6d43-260">VB</span></span>|<span data-ttu-id="b6d43-261">vb</span><span class="sxs-lookup"><span data-stu-id="b6d43-261">vb</span></span>|
|<span data-ttu-id="b6d43-262">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="b6d43-262">VSTS CLI</span></span>|<span data-ttu-id="b6d43-263">vstscli</span><span class="sxs-lookup"><span data-stu-id="b6d43-263">vstscli</span></span>|
|<span data-ttu-id="b6d43-264">XAML</span><span class="sxs-lookup"><span data-stu-id="b6d43-264">XAML</span></span>|<span data-ttu-id="b6d43-265">xaml</span><span class="sxs-lookup"><span data-stu-id="b6d43-265">xaml</span></span>|
|<span data-ttu-id="b6d43-266">XML</span><span class="sxs-lookup"><span data-stu-id="b6d43-266">XML</span></span>|<span data-ttu-id="b6d43-267">xml</span><span class="sxs-lookup"><span data-stu-id="b6d43-267">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="b6d43-268">Przykład: C\#</span><span class="sxs-lookup"><span data-stu-id="b6d43-268">Example: C\#</span></span>

<span data-ttu-id="b6d43-269">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="b6d43-269">__Markdown__</span></span>

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

<span data-ttu-id="b6d43-270">__Renderowanie__</span><span class="sxs-lookup"><span data-stu-id="b6d43-270">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="b6d43-271">Przykład: SQL</span><span class="sxs-lookup"><span data-stu-id="b6d43-271">Example: SQL</span></span>

<span data-ttu-id="b6d43-272">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="b6d43-272">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="b6d43-273">__Renderowanie__</span><span class="sxs-lookup"><span data-stu-id="b6d43-273">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="b6d43-274">Niestandardowe rozszerzenia języka Markdown na platformie OPS</span><span class="sxs-lookup"><span data-stu-id="b6d43-274">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="b6d43-275">Platforma Open Publishing Services (OPS) umożliwia implementowanie parsera Markdig dla języka Markdown o wysokim stopniu zgodności z językiem GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="b6d43-275">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="b6d43-276">Parser Markdig dodaje pewne funkcje za pośrednictwem rozszerzeń języka Markdown.</span><span class="sxs-lookup"><span data-stu-id="b6d43-276">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="b6d43-277">Wybrane artykuły z pełnego podręcznika tworzenia platformy OPS jako takie zostały dołączone do tego przewodnika do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="b6d43-277">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="b6d43-278">(Przykład można znaleźć w częściach „Rozszerzenia parsera Markdig i języka Markdown” oraz „Fragmenty kodu” dostępnych w spisie treści).</span><span class="sxs-lookup"><span data-stu-id="b6d43-278">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="b6d43-279">W artykułach z witryny Docs rozwiązanie GFM jest używane na potrzeby większości elementów formatowania artykułów, takich jak akapity, linki, listy i nagłówki.</span><span class="sxs-lookup"><span data-stu-id="b6d43-279">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="b6d43-280">W celu skorzystania z bardziej zaawansowanego formatowania można w artykułach użyć funkcji parsera Markdig, takich jak:</span><span class="sxs-lookup"><span data-stu-id="b6d43-280">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="b6d43-281">Bloki uwag</span><span class="sxs-lookup"><span data-stu-id="b6d43-281">Note blocks</span></span>
- <span data-ttu-id="b6d43-282">Operacje dołączania</span><span class="sxs-lookup"><span data-stu-id="b6d43-282">Includes</span></span>
- <span data-ttu-id="b6d43-283">Selektory</span><span class="sxs-lookup"><span data-stu-id="b6d43-283">Selectors</span></span>
- <span data-ttu-id="b6d43-284">Osadzone filmy wideo</span><span class="sxs-lookup"><span data-stu-id="b6d43-284">Embedded videos</span></span>
- <span data-ttu-id="b6d43-285">Fragmenty/przykłady kodu</span><span class="sxs-lookup"><span data-stu-id="b6d43-285">Code snippets/samples</span></span>

<span data-ttu-id="b6d43-286">Kompletną listę można znaleźć w częściach „Rozszerzenia parsera Markdig i języka Markdown” oraz „Fragmenty kodu” dostępnych w spisie treści.</span><span class="sxs-lookup"><span data-stu-id="b6d43-286">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="b6d43-287">Bloki uwag</span><span class="sxs-lookup"><span data-stu-id="b6d43-287">Note blocks</span></span>

<span data-ttu-id="b6d43-288">Aby zwrócić uwagę czytelnika na określoną zawartość, można wybrać jeden z czterech typów bloków uwag:</span><span class="sxs-lookup"><span data-stu-id="b6d43-288">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="b6d43-289">UWAGA</span><span class="sxs-lookup"><span data-stu-id="b6d43-289">NOTE</span></span>
- <span data-ttu-id="b6d43-290">OSTRZEŻENIE</span><span class="sxs-lookup"><span data-stu-id="b6d43-290">WARNING</span></span>
- <span data-ttu-id="b6d43-291">PORADA</span><span class="sxs-lookup"><span data-stu-id="b6d43-291">TIP</span></span>
- <span data-ttu-id="b6d43-292">WAŻNE</span><span class="sxs-lookup"><span data-stu-id="b6d43-292">IMPORTANT</span></span>

<span data-ttu-id="b6d43-293">Ogólnie rzecz biorąc, bloków uwag należy używać oszczędnie, ponieważ mogą zaburzać czytelność artykułu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-293">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="b6d43-294">Obsługują one również bloki kodu, obrazy, listy i linki, ale należy starać się, aby były proste i czytelne.</span><span class="sxs-lookup"><span data-stu-id="b6d43-294">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="b6d43-295">Operacje dołączania</span><span class="sxs-lookup"><span data-stu-id="b6d43-295">Includes</span></span>

<span data-ttu-id="b6d43-296">Jeśli masz pliki tekstu lub obrazów do wielokrotnego użytku, które chcesz dołączyć do plików artykułu, możesz użyć odwołania do pliku dołączania za pomocą funkcji dołączania plików w parserze Markdig.</span><span class="sxs-lookup"><span data-stu-id="b6d43-296">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="b6d43-297">Ta funkcja nakazuje platformie OPS dołączenie pliku do pliku artykułu podczas kompilacji, co sprawia, że plik staje się częścią publikowanego artykułu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-297">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="b6d43-298">Istnieją trzy typy operacji dołączania, które ułatwiają wielokrotne użycie zawartości:</span><span class="sxs-lookup"><span data-stu-id="b6d43-298">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="b6d43-299">Śródwierszowe: wielokrotne użycie typowego fragmentu tekstu jako śródwierszowego w innym zdaniu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-299">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="b6d43-300">Blokowe: wielokrotne użycie całego pliku Markdown jako bloku zagnieżdżonego w sekcji artykułu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-300">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="b6d43-301">Obraz: jest to standardowa operacja dołączania implementowana w witrynie Docs.</span><span class="sxs-lookup"><span data-stu-id="b6d43-301">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="b6d43-302">Śródwierszowe i blokowe operacje dołączania dotyczą prostego pliku Markdown (md).</span><span class="sxs-lookup"><span data-stu-id="b6d43-302">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="b6d43-303">Może on zawierać dowolny prawidłowy kod w języku Markdown.</span><span class="sxs-lookup"><span data-stu-id="b6d43-303">It can contain any valid Markdown.</span></span> <span data-ttu-id="b6d43-304">Wszystkie dołączane pliki Markdown należy umieścić we [wspólnym podkatalogu `/includes`](git-github-fundamentals.md#includes-subdirectory) w głównym katalogu repozytorium.</span><span class="sxs-lookup"><span data-stu-id="b6d43-304">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="b6d43-305">Podczas publikowania artykułu dołączany plik jest płynnie z nim integrowany.</span><span class="sxs-lookup"><span data-stu-id="b6d43-305">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="b6d43-306">Poniżej przedstawiono wymagania i uwagi dotyczące operacji dołączania:</span><span class="sxs-lookup"><span data-stu-id="b6d43-306">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="b6d43-307">Operacji dołączania należy używać, gdy ten sam tekst ma pojawiać się w wielu artykułach.</span><span class="sxs-lookup"><span data-stu-id="b6d43-307">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="b6d43-308">Blokowe operacje dołączania są używane w przypadku znaczących ilości zawartości — akapitu lub dwóch, procedury udostępnianej lub sekcji udostępnianej.</span><span class="sxs-lookup"><span data-stu-id="b6d43-308">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="b6d43-309">Nie należy ich używać dla części mniejszych niż zdanie.</span><span class="sxs-lookup"><span data-stu-id="b6d43-309">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="b6d43-310">Operacje dołączania nie będą renderowane w renderowanym widoku Twojego artykułu w usłudze GitHub, ponieważ korzystają z rozszerzeń parsera Markdig.</span><span class="sxs-lookup"><span data-stu-id="b6d43-310">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="b6d43-311">Będą one renderowane tylko po publikacji.</span><span class="sxs-lookup"><span data-stu-id="b6d43-311">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="b6d43-312">Upewnij się, że cały tekst w operacji dołączania został napisany w postaci kompletnych zdań lub fraz, które nie zależą od poprzedniego ani następującego tekstu w artykule odwołującym się do dołączenia.</span><span class="sxs-lookup"><span data-stu-id="b6d43-312">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="b6d43-313">Zignorowanie tej wskazówki spowoduje powstanie w artykule ciągu niemożliwego do przetłumaczenia, który zakłóci spójność zlokalizowanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-313">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="b6d43-314">Operacji dołączania nie należy osadzać w innych dołączeniach.</span><span class="sxs-lookup"><span data-stu-id="b6d43-314">Don't embed includes within other includes.</span></span> <span data-ttu-id="b6d43-315">Nie są one obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="b6d43-315">They are not supported.</span></span>
- <span data-ttu-id="b6d43-316">Umieść pliki multimedialne w folderze media, który jest specyficzny dla podkatalogu include — na przykład w folderze `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="b6d43-316">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="b6d43-317">Katalog główny względem katalogu multimediów nie powinien zawierać obrazów.</span><span class="sxs-lookup"><span data-stu-id="b6d43-317">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="b6d43-318">Jeśli dołączenie nie zawiera obrazów, odpowiadający mu katalog multimediów nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="b6d43-318">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="b6d43-319">Podobnie jak w przypadku zwykłych artykułów nie należy udostępniać multimediów między dołączanymi plikami.</span><span class="sxs-lookup"><span data-stu-id="b6d43-319">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="b6d43-320">Użyj oddzielnego pliku z unikatową nazwą dla każdego dołączenia i artykułu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-320">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="b6d43-321">Plik multimedialny należy przechowywać w folderze media skojarzonym z dołączeniem.</span><span class="sxs-lookup"><span data-stu-id="b6d43-321">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="b6d43-322">Nie należy używać dołączenia jako jedynej zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-322">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="b6d43-323">Operacje dołączania mają stanowić uzupełnienie pozostałej zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-323">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="b6d43-324">Selektory</span><span class="sxs-lookup"><span data-stu-id="b6d43-324">Selectors</span></span>

<span data-ttu-id="b6d43-325">Selektorów należy używać w tworzonych artykułach technicznych z wieloma wariantami tego samego artykułu w celu przedstawienia różnic między implementacjami w ramach różnych technologii lub platform.</span><span class="sxs-lookup"><span data-stu-id="b6d43-325">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="b6d43-326">Ma to przeważnie zastosowanie w przypadku mobilnej zawartości platformy dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="b6d43-326">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="b6d43-327">Obecnie w parserze Markdig istnieją dwa różne typy selektorów: selektor pojedynczy i selektor wielokrotny.</span><span class="sxs-lookup"><span data-stu-id="b6d43-327">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="b6d43-328">Ponieważ ten sam kod języka Markdown selektora znajduje się w każdym artykule w zaznaczeniu, zalecamy umieszczanie selektora artykułu w dołączeniu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-328">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="b6d43-329">Następnie można się odwołać do tego dołączenia we wszystkich artykułach, które używają tego samego selektora.</span><span class="sxs-lookup"><span data-stu-id="b6d43-329">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="b6d43-330">Fragmenty kodu</span><span class="sxs-lookup"><span data-stu-id="b6d43-330">Code snippets</span></span>

<span data-ttu-id="b6d43-331">Parser Markdig obsługuje zaawansowane dołączanie kodu do artykułu za pośrednictwem rozszerzenia fragmentu kodu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-331">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="b6d43-332">Oferuje ono zaawansowane możliwości renderowania współpracujące z funkcjami GFM, takie jak wybór języka programowania i kolorowanie składni, oraz użyteczne funkcje, takie jak:</span><span class="sxs-lookup"><span data-stu-id="b6d43-332">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="b6d43-333">dołączanie scentralizowanych przykładów/fragmentów kodu z repozytorium zewnętrznego;</span><span class="sxs-lookup"><span data-stu-id="b6d43-333">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="b6d43-334">interfejs użytkownika z kartami przedstawiającymi wiele wersji przykładów kodu w różnych językach.</span><span class="sxs-lookup"><span data-stu-id="b6d43-334">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="b6d43-335">Problemy i ich rozwiązywanie</span><span class="sxs-lookup"><span data-stu-id="b6d43-335">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="b6d43-336">Tekst alternatywny</span><span class="sxs-lookup"><span data-stu-id="b6d43-336">Alt text</span></span>

<span data-ttu-id="b6d43-337">Nie można prawidłowo renderować tekstu alternatywnego, który zawiera znaki podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="b6d43-337">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="b6d43-338">Na przykład zamiast używać tego:</span><span class="sxs-lookup"><span data-stu-id="b6d43-338">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="b6d43-339">Omiń podkreślenia w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="b6d43-339">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="b6d43-340">Apostrofy i cudzysłowy</span><span class="sxs-lookup"><span data-stu-id="b6d43-340">Apostrophes and quotation marks</span></span>

<span data-ttu-id="b6d43-341">W przypadku kopiowania z programu Word do edytora języka Markdown tekst może zawierać „eleganckie” (zawinięte) apostrofy lub cudzysłowy.</span><span class="sxs-lookup"><span data-stu-id="b6d43-341">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="b6d43-342">Należy je zakodować lub zmienić na podstawowe apostrofy lub znaki cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="b6d43-342">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span>
<span data-ttu-id="b6d43-343">W przeciwnym razie po opublikowaniu pliku otrzymasz coś takiego: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="b6d43-343">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="b6d43-344">Oto sposoby kodowania „eleganckich” wersji tych znaków interpunkcyjnych:</span><span class="sxs-lookup"><span data-stu-id="b6d43-344">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="b6d43-345">Lewy cudzysłów (otwierający): `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="b6d43-345">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="b6d43-346">Prawy cudzysłów (zamykający): `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="b6d43-346">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="b6d43-347">Prawy pojedynczy cudzysłów lub apostrof (zamykający): `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="b6d43-347">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="b6d43-348">Lewy pojedynczy cudzysłów (otwierający) (rzadko używany): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="b6d43-348">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="b6d43-349">Nawiasy kątowe</span><span class="sxs-lookup"><span data-stu-id="b6d43-349">Angle brackets</span></span>

<span data-ttu-id="b6d43-350">Często stosuje się nawiasy kątowe w celu oznaczenia symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="b6d43-350">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="b6d43-351">W przypadku użycia nawiasów kątowych w tekście (nie w kodzie) należy je zakodować.</span><span class="sxs-lookup"><span data-stu-id="b6d43-351">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="b6d43-352">W przeciwnym razie w języku Markdown nawiasy kątowe zostaną potraktowane jak tag HTML.</span><span class="sxs-lookup"><span data-stu-id="b6d43-352">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="b6d43-353">Na przykład `<script name>` należy zakodować jako `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="b6d43-353">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="b6d43-354">Zobacz też:</span><span class="sxs-lookup"><span data-stu-id="b6d43-354">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="b6d43-355">Zasoby dotyczące języka Markdown</span><span class="sxs-lookup"><span data-stu-id="b6d43-355">Markdown resources</span></span>

- <span data-ttu-id="b6d43-356">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Wprowadzenie do języka Markdown)</span><span class="sxs-lookup"><span data-stu-id="b6d43-356">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="b6d43-357">Docs Markdown cheat-sheet (Ściągawka dotycząca języka Markdown w witrynie Docs)</span><span class="sxs-lookup"><span data-stu-id="b6d43-357">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="b6d43-358">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (Podstawy języka Markdown w serwisie GitHub)</span><span class="sxs-lookup"><span data-stu-id="b6d43-358">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
- [<span data-ttu-id="b6d43-359">The Markdown Guide</span><span class="sxs-lookup"><span data-stu-id="b6d43-359">The Markdown Guide</span></span>](https://www.markdownguide.org/)
