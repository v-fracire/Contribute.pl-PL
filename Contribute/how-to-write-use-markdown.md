---
title: Jak używać języka Markdown do tworzenia zawartości witryny Docs
description: Ten artykuł zawiera podstawy i informacje referencyjne dotyczące języka znaczników Markdown używanego do pisania artykułów w witrynie docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: 21194c4bd6020d847b526a4d9544c826aa199e2a
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609527"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="a1398-103">Jak używać języka Markdown do tworzenia zawartości witryny Docs</span><span class="sxs-lookup"><span data-stu-id="a1398-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="a1398-104">Artykuły w witrynie [docs.microsoft.com](http://docs.microsoft.com) są pisane w prostym języku znaczników o nazwie [Markdown](https://daringfireball.net/projects/markdown/), który jest łatwy do czytania i do nauczenia się.</span><span class="sxs-lookup"><span data-stu-id="a1398-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="a1398-105">Z tego względu stał się on szybko branżowym standardem.</span><span class="sxs-lookup"><span data-stu-id="a1398-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="a1398-106">Ponieważ zawartość witryny Docs jest przechowywana w serwisie GitHub, może korzystać z nadzbioru znaczników Markdown o nazwie [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), który oferuje dodatkowe funkcje spełniające typowe potrzeby związane z formatowaniem.</span><span class="sxs-lookup"><span data-stu-id="a1398-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="a1398-107">Ponadto platforma Open Publishing Services (OPS) implementuje parser języka Markdown o nazwie Markdig.</span><span class="sxs-lookup"><span data-stu-id="a1398-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="a1398-108">Parser Markdig jest w wysokim stopniu zgodny z językiem GFM, dodając funkcjonalność włączania funkcji specyficznych dla dokumentów.</span><span class="sxs-lookup"><span data-stu-id="a1398-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="a1398-109">Parser Markdig jest szybkim, wydajnym, zgodnym ze składnią CommonMark, rozszerzalnym procesorem języka Markdown dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="a1398-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="a1398-110">Lepsze wsparcie społeczności</span><span class="sxs-lookup"><span data-stu-id="a1398-110">Better community support</span></span>
* <span data-ttu-id="a1398-111">Lepsza obsługa standardów</span><span class="sxs-lookup"><span data-stu-id="a1398-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="a1398-112">Podstawy języka Markdown</span><span class="sxs-lookup"><span data-stu-id="a1398-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="a1398-113">Nagłówki</span><span class="sxs-lookup"><span data-stu-id="a1398-113">Headings</span></span>

<span data-ttu-id="a1398-114">Aby utworzyć nagłówek, użyj znaku skrótu (#) w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a1398-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="a1398-115">Nagłówki powinny być tworzone przy użyciu stylu atx — w celu oznaczenia nagłówka wprowadź od 1 do 6 znaków numeru (#) na początku wiersza. Znaki te odpowiadają poziomom nagłówków HTML (od H1 do H6).</span><span class="sxs-lookup"><span data-stu-id="a1398-115">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="a1398-116">W powyższym przykładzie użyto czterech poziomów nagłówków.</span><span class="sxs-lookup"><span data-stu-id="a1398-116">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="a1398-117">W temacie **może** znajdować się tylko jeden nagłówek pierwszego poziomu (H1), który będzie wyświetlany jako tytuł strony.</span><span class="sxs-lookup"><span data-stu-id="a1398-117">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="a1398-118">Aby zapewnić prawidłowe renderowanie tytułu z nagłówkiem, który kończy się znakiem `#`, na końcu musisz wprowadzić dodatkowy znak `#`.</span><span class="sxs-lookup"><span data-stu-id="a1398-118">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="a1398-119">Na przykład `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="a1398-119">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="a1398-120">Nagłówki drugiego poziomu generują spis treści, który jest widoczny w sekcji „W tym artykule” znajdującej się pod tytułem.</span><span class="sxs-lookup"><span data-stu-id="a1398-120">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="a1398-121">Tekst pogrubiony i kursywa</span><span class="sxs-lookup"><span data-stu-id="a1398-121">Bold and italic text</span></span>

<span data-ttu-id="a1398-122">Aby sformatować tekst jako **pogrubiony**, umieść go między podwójnymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="a1398-122">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="a1398-123">Aby sformatować tekst jako *kursywę*, umieść go między pojedynczymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="a1398-123">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="a1398-124">Aby sformatować tekst jako ***pogrubiony i kursywę***, umieść go między potrójnymi gwiazdkami:</span><span class="sxs-lookup"><span data-stu-id="a1398-124">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="a1398-125">Cytat blokowy</span><span class="sxs-lookup"><span data-stu-id="a1398-125">Blockquotes</span></span>

<span data-ttu-id="a1398-126">Do tworzenia cytatu blokowego służy znak `>`:</span><span class="sxs-lookup"><span data-stu-id="a1398-126">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="a1398-127">Powyższy przykład zostanie wyrenderowany następująco:</span><span class="sxs-lookup"><span data-stu-id="a1398-127">The preceding example renders as follows:</span></span>

> <span data-ttu-id="a1398-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span><span class="sxs-lookup"><span data-stu-id="a1398-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="a1398-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span><span class="sxs-lookup"><span data-stu-id="a1398-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="a1398-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span><span class="sxs-lookup"><span data-stu-id="a1398-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="a1398-131">Listy</span><span class="sxs-lookup"><span data-stu-id="a1398-131">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="a1398-132">Listy nieuporządkowane</span><span class="sxs-lookup"><span data-stu-id="a1398-132">Unordered list</span></span>

<span data-ttu-id="a1398-133">Aby sformatować listę nieuporządkowaną/punktowaną, można użyć gwiazdek lub myślników.</span><span class="sxs-lookup"><span data-stu-id="a1398-133">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="a1398-134">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="a1398-134">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="a1398-135">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="a1398-135">will be rendered as:</span></span>

- <span data-ttu-id="a1398-136">Element listy 1</span><span class="sxs-lookup"><span data-stu-id="a1398-136">List item 1</span></span>
- <span data-ttu-id="a1398-137">Element listy 2</span><span class="sxs-lookup"><span data-stu-id="a1398-137">List item 2</span></span>
- <span data-ttu-id="a1398-138">Element listy 3</span><span class="sxs-lookup"><span data-stu-id="a1398-138">List item 3</span></span>

<span data-ttu-id="a1398-139">Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy.</span><span class="sxs-lookup"><span data-stu-id="a1398-139">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="a1398-140">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="a1398-140">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="a1398-141">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="a1398-141">will be rendered as:</span></span>

- <span data-ttu-id="a1398-142">Element listy 1</span><span class="sxs-lookup"><span data-stu-id="a1398-142">List item 1</span></span>
  - <span data-ttu-id="a1398-143">Element listy A</span><span class="sxs-lookup"><span data-stu-id="a1398-143">List item A</span></span>
  - <span data-ttu-id="a1398-144">Element listy B</span><span class="sxs-lookup"><span data-stu-id="a1398-144">List item B</span></span>
- <span data-ttu-id="a1398-145">Element listy 2</span><span class="sxs-lookup"><span data-stu-id="a1398-145">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="a1398-146">Lista uporządkowana</span><span class="sxs-lookup"><span data-stu-id="a1398-146">Ordered list</span></span>

<span data-ttu-id="a1398-147">Aby sformatować listę uporządkowaną/zawierającą kroki w kolejności ich wykonywania, należy użyć odpowiednich numerów.</span><span class="sxs-lookup"><span data-stu-id="a1398-147">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="a1398-148">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="a1398-148">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="a1398-149">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="a1398-149">will be rendered as:</span></span>

1. <span data-ttu-id="a1398-150">Pierwsza instrukcja</span><span class="sxs-lookup"><span data-stu-id="a1398-150">First instruction</span></span>
2. <span data-ttu-id="a1398-151">Druga instrukcja</span><span class="sxs-lookup"><span data-stu-id="a1398-151">Second instruction</span></span>
3. <span data-ttu-id="a1398-152">Trzecia instrukcja</span><span class="sxs-lookup"><span data-stu-id="a1398-152">Third instruction</span></span>

<span data-ttu-id="a1398-153">Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy.</span><span class="sxs-lookup"><span data-stu-id="a1398-153">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="a1398-154">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="a1398-154">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="a1398-155">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="a1398-155">will be rendered as:</span></span>

1. <span data-ttu-id="a1398-156">Pierwsza instrukcja</span><span class="sxs-lookup"><span data-stu-id="a1398-156">First instruction</span></span>
   1. <span data-ttu-id="a1398-157">Instrukcja podrzędna</span><span class="sxs-lookup"><span data-stu-id="a1398-157">Sub-instruction</span></span>
   2. <span data-ttu-id="a1398-158">Instrukcja podrzędna</span><span class="sxs-lookup"><span data-stu-id="a1398-158">Sub-instruction</span></span>
2. <span data-ttu-id="a1398-159">Druga instrukcja</span><span class="sxs-lookup"><span data-stu-id="a1398-159">Second instruction</span></span>

<span data-ttu-id="a1398-160">Zwróć uwagę, że użyto numeru „1”</span><span class="sxs-lookup"><span data-stu-id="a1398-160">Note that we use '1.'</span></span> <span data-ttu-id="a1398-161">we wszystkich pozycjach.</span><span class="sxs-lookup"><span data-stu-id="a1398-161">for all entries.</span></span> <span data-ttu-id="a1398-162">Ułatwia to dostrzeganie różnic powstałych w efekcie dodania lub usunięcia kroków w kolejnych aktualizacjach.</span><span class="sxs-lookup"><span data-stu-id="a1398-162">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="a1398-163">tabelami</span><span class="sxs-lookup"><span data-stu-id="a1398-163">Tables</span></span>

<span data-ttu-id="a1398-164">Tabele nie są częścią podstawowej specyfikacji języka Markdown, ale są obsługiwane przez język GFM.</span><span class="sxs-lookup"><span data-stu-id="a1398-164">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="a1398-165">Tabele możesz tworzyć przy użyciu znaków kreski pionowej (|) i łącznika (-).</span><span class="sxs-lookup"><span data-stu-id="a1398-165">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="a1398-166">Łączniki tworzą nagłówki poszczególnych kolumn, a kreski pionowe rozdzielają kolumny.</span><span class="sxs-lookup"><span data-stu-id="a1398-166">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="a1398-167">Aby tabela była poprawnie renderowana, dodaj przed nią pusty wiersz.</span><span class="sxs-lookup"><span data-stu-id="a1398-167">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="a1398-168">Na przykład poniższy kod w języku Markdown:</span><span class="sxs-lookup"><span data-stu-id="a1398-168">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="a1398-169">zostanie wyświetlony jako:</span><span class="sxs-lookup"><span data-stu-id="a1398-169">will be rendered as:</span></span>

| <span data-ttu-id="a1398-170">Zabawa</span><span class="sxs-lookup"><span data-stu-id="a1398-170">Fun</span></span>                  | <span data-ttu-id="a1398-171">z</span><span class="sxs-lookup"><span data-stu-id="a1398-171">With</span></span>                 | <span data-ttu-id="a1398-172">tabelami</span><span class="sxs-lookup"><span data-stu-id="a1398-172">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="a1398-173">kolumna wyrównana do lewej</span><span class="sxs-lookup"><span data-stu-id="a1398-173">left-aligned column</span></span>  | <span data-ttu-id="a1398-174">kolumna wyrównana do prawej</span><span class="sxs-lookup"><span data-stu-id="a1398-174">right-aligned column</span></span> | <span data-ttu-id="a1398-175">kolumna wyśrodkowana</span><span class="sxs-lookup"><span data-stu-id="a1398-175">centered column</span></span> |
| <span data-ttu-id="a1398-176">100 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-176">$100</span></span>                 | <span data-ttu-id="a1398-177">100 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-177">$100</span></span>                 | <span data-ttu-id="a1398-178">100 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-178">$100</span></span>            |
| <span data-ttu-id="a1398-179">10 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-179">$10</span></span>                  | <span data-ttu-id="a1398-180">10 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-180">$10</span></span>                  | <span data-ttu-id="a1398-181">10 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-181">$10</span></span>             |
| <span data-ttu-id="a1398-182">1 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-182">$1</span></span>                   | <span data-ttu-id="a1398-183">1 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-183">$1</span></span>                   | <span data-ttu-id="a1398-184">1 USD</span><span class="sxs-lookup"><span data-stu-id="a1398-184">$1</span></span>              |

<span data-ttu-id="a1398-185">Więcej informacji na temat tworzenia tabel można znaleźć w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="a1398-185">For more information on creating tables, see:</span></span>

- <span data-ttu-id="a1398-186">[Funkcja zawijania tabel](#table-wrapping) parsera Markdig, która może ułatwić formatowanie szerokich tabel.</span><span class="sxs-lookup"><span data-stu-id="a1398-186">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="a1398-187">Artykuł [Organizing information with tables (Organizowanie informacji przy użyciu tabel)](https://help.github.com/articles/organizing-information-with-tables/) w usłudze GitHub.</span><span class="sxs-lookup"><span data-stu-id="a1398-187">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="a1398-188">Aplikacja internetowa [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="a1398-188">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="a1398-189">[Markdown Cheatsheet (Ściągawka dotycząca języka Markdown), autor: Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="a1398-189">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="a1398-190">[Markdown Extra, autor: Michel Fortin](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="a1398-190">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="a1398-191">[Konwertowanie tabel HTML na znaczniki języka Markdown](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="a1398-191">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="a1398-192">Linki</span><span class="sxs-lookup"><span data-stu-id="a1398-192">Links</span></span>

<span data-ttu-id="a1398-193">Składnia języka Markdown dla linku śródwierszowego składa się z części `[link text]`, czyli tekstu do uwzględnienia w hiperlinku, oraz następującej po niej części `(file-name.md)`, czyli adresu URL lub nazwy pliku dołączanego przy użyciu linku:</span><span class="sxs-lookup"><span data-stu-id="a1398-193">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="a1398-194">Więcej informacji na temat łączenia zawierają następujące zasoby:</span><span class="sxs-lookup"><span data-stu-id="a1398-194">For more information on linking, see:</span></span>

- <span data-ttu-id="a1398-195">[Przewodnik po składni języka Markdown](https://daringfireball.net/projects/markdown/syntax#link) (szczegóły dotyczące obsługi podstawowego łączenia w języku Markdown).</span><span class="sxs-lookup"><span data-stu-id="a1398-195">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="a1398-196">Sekcja [Linki](how-to-write-links.md) tego przewodnika (szczegóły dodatkowej składni łączenia oferowanej przez parser Markdig).</span><span class="sxs-lookup"><span data-stu-id="a1398-196">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="a1398-197">Fragmenty kodu</span><span class="sxs-lookup"><span data-stu-id="a1398-197">Code snippets</span></span>

<span data-ttu-id="a1398-198">Język Markdown obsługuje umieszczanie fragmentów kodu jako śródwierszowych w zdaniu oraz jako oddzielnego, „ogrodzonego” bloku między zdaniami.</span><span class="sxs-lookup"><span data-stu-id="a1398-198">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="a1398-199">Szczegóły znajdziesz w następujących zasobach:</span><span class="sxs-lookup"><span data-stu-id="a1398-199">For details, see:</span></span>

- [<span data-ttu-id="a1398-200">Natywna obsługa bloków kodu w języku Markdown</span><span class="sxs-lookup"><span data-stu-id="a1398-200">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="a1398-201">Obsługa ogradzania kodu i wyróżniania składni w rozwiązaniu GFM</span><span class="sxs-lookup"><span data-stu-id="a1398-201">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="a1398-202">Ogrodzone bloki kodu to prosty sposób włączania wyróżniania składni wybranych fragmentów kodu.</span><span class="sxs-lookup"><span data-stu-id="a1398-202">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="a1398-203">Ogólny format ogrodzonych bloków kodu to:</span><span class="sxs-lookup"><span data-stu-id="a1398-203">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="a1398-204">Alias po trzech początkowych znakach „\`” definiuje wyróżnianie składni do użycia.</span><span class="sxs-lookup"><span data-stu-id="a1398-204">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="a1398-205">Poniżej przedstawiono listę języków programowania najczęściej używanych w zawartości witryny Docs oraz odpowiadających im etykiet:</span><span class="sxs-lookup"><span data-stu-id="a1398-205">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="a1398-206">Te języki obsługują przyjazne nazwy i w większości obsługują wyróżnianie składni.</span><span class="sxs-lookup"><span data-stu-id="a1398-206">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="a1398-207">Nazwa</span><span class="sxs-lookup"><span data-stu-id="a1398-207">Name</span></span>|<span data-ttu-id="a1398-208">Etykieta języka Markdown</span><span class="sxs-lookup"><span data-stu-id="a1398-208">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="a1398-209">Konsola .NET</span><span class="sxs-lookup"><span data-stu-id="a1398-209">.NET Console</span></span>|<span data-ttu-id="a1398-210">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="a1398-210">dotnetcli</span></span>|
|<span data-ttu-id="a1398-211">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="a1398-211">ASP.NET (C#)</span></span>|<span data-ttu-id="a1398-212">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="a1398-212">aspx-csharp</span></span>|
|<span data-ttu-id="a1398-213">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="a1398-213">ASP.NET (VB)</span></span>|<span data-ttu-id="a1398-214">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="a1398-214">aspx-vb</span></span>|
|<span data-ttu-id="a1398-215">AzCopy</span><span class="sxs-lookup"><span data-stu-id="a1398-215">AzCopy</span></span>|<span data-ttu-id="a1398-216">azcopy</span><span class="sxs-lookup"><span data-stu-id="a1398-216">azcopy</span></span>|
|<span data-ttu-id="a1398-217">Interfejs wiersza polecenia platformy Azure</span><span class="sxs-lookup"><span data-stu-id="a1398-217">Azure CLI</span></span>|<span data-ttu-id="a1398-218">azurecli</span><span class="sxs-lookup"><span data-stu-id="a1398-218">azurecli</span></span>|
|<span data-ttu-id="a1398-219">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1398-219">Azure PowerShell</span></span>|<span data-ttu-id="a1398-220">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="a1398-220">azurepowershell</span></span>|
|<span data-ttu-id="a1398-221">C++</span><span class="sxs-lookup"><span data-stu-id="a1398-221">C++</span></span>|<span data-ttu-id="a1398-222">cpp</span><span class="sxs-lookup"><span data-stu-id="a1398-222">cpp</span></span>|
|<span data-ttu-id="a1398-223">C++/CX</span><span class="sxs-lookup"><span data-stu-id="a1398-223">C++/CX</span></span>|<span data-ttu-id="a1398-224">cppcx</span><span class="sxs-lookup"><span data-stu-id="a1398-224">cppcx</span></span>|
|<span data-ttu-id="a1398-225">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="a1398-225">C++/WinRT</span></span>|<span data-ttu-id="a1398-226">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="a1398-226">cppwinrt</span></span>|
|<span data-ttu-id="a1398-227">C#</span><span class="sxs-lookup"><span data-stu-id="a1398-227">C#</span></span>|<span data-ttu-id="a1398-228">csharp</span><span class="sxs-lookup"><span data-stu-id="a1398-228">csharp</span></span>|
|<span data-ttu-id="a1398-229">C# w przeglądarce</span><span class="sxs-lookup"><span data-stu-id="a1398-229">C# in browser</span></span>|<span data-ttu-id="a1398-230">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="a1398-230">csharp-interactive</span></span>|
|<span data-ttu-id="a1398-231">Konsola</span><span class="sxs-lookup"><span data-stu-id="a1398-231">Console</span></span>|<span data-ttu-id="a1398-232">console</span><span class="sxs-lookup"><span data-stu-id="a1398-232">console</span></span>|
|<span data-ttu-id="a1398-233">CSHTML</span><span class="sxs-lookup"><span data-stu-id="a1398-233">CSHTML</span></span>|<span data-ttu-id="a1398-234">cshtml</span><span class="sxs-lookup"><span data-stu-id="a1398-234">cshtml</span></span>|
|<span data-ttu-id="a1398-235">DAX</span><span class="sxs-lookup"><span data-stu-id="a1398-235">DAX</span></span>|<span data-ttu-id="a1398-236">dax</span><span class="sxs-lookup"><span data-stu-id="a1398-236">dax</span></span>|
|<span data-ttu-id="a1398-237">F#</span><span class="sxs-lookup"><span data-stu-id="a1398-237">F#</span></span>|<span data-ttu-id="a1398-238">fsharp</span><span class="sxs-lookup"><span data-stu-id="a1398-238">fsharp</span></span>|
|<span data-ttu-id="a1398-239">Go</span><span class="sxs-lookup"><span data-stu-id="a1398-239">Go</span></span>|<span data-ttu-id="a1398-240">go</span><span class="sxs-lookup"><span data-stu-id="a1398-240">go</span></span>|
|<span data-ttu-id="a1398-241">HTML</span><span class="sxs-lookup"><span data-stu-id="a1398-241">HTML</span></span>|<span data-ttu-id="a1398-242">html</span><span class="sxs-lookup"><span data-stu-id="a1398-242">html</span></span>|
|<span data-ttu-id="a1398-243">HTTP</span><span class="sxs-lookup"><span data-stu-id="a1398-243">HTTP</span></span>|<span data-ttu-id="a1398-244">http</span><span class="sxs-lookup"><span data-stu-id="a1398-244">http</span></span>|
|<span data-ttu-id="a1398-245">Java</span><span class="sxs-lookup"><span data-stu-id="a1398-245">Java</span></span>|<span data-ttu-id="a1398-246">java</span><span class="sxs-lookup"><span data-stu-id="a1398-246">java</span></span>|
|<span data-ttu-id="a1398-247">JavaScript</span><span class="sxs-lookup"><span data-stu-id="a1398-247">JavaScript</span></span>|<span data-ttu-id="a1398-248">javascript</span><span class="sxs-lookup"><span data-stu-id="a1398-248">javascript</span></span>|
|<span data-ttu-id="a1398-249">JSON</span><span class="sxs-lookup"><span data-stu-id="a1398-249">JSON</span></span>|<span data-ttu-id="a1398-250">json</span><span class="sxs-lookup"><span data-stu-id="a1398-250">json</span></span>|
|<span data-ttu-id="a1398-251">Znaczniki języka Markdown</span><span class="sxs-lookup"><span data-stu-id="a1398-251">Markdown</span></span>|<span data-ttu-id="a1398-252">md</span><span class="sxs-lookup"><span data-stu-id="a1398-252">md</span></span>|
|<span data-ttu-id="a1398-253">NodeJS</span><span class="sxs-lookup"><span data-stu-id="a1398-253">NodeJS</span></span>|<span data-ttu-id="a1398-254">nodejs</span><span class="sxs-lookup"><span data-stu-id="a1398-254">nodejs</span></span>|
|<span data-ttu-id="a1398-255">Objective-C</span><span class="sxs-lookup"><span data-stu-id="a1398-255">Objective-C</span></span>|<span data-ttu-id="a1398-256">objc</span><span class="sxs-lookup"><span data-stu-id="a1398-256">objc</span></span>|
|<span data-ttu-id="a1398-257">OData</span><span class="sxs-lookup"><span data-stu-id="a1398-257">OData</span></span>|<span data-ttu-id="a1398-258">odata</span><span class="sxs-lookup"><span data-stu-id="a1398-258">odata</span></span>|
|<span data-ttu-id="a1398-259">PHP</span><span class="sxs-lookup"><span data-stu-id="a1398-259">PHP</span></span>|<span data-ttu-id="a1398-260">PHP</span><span class="sxs-lookup"><span data-stu-id="a1398-260">php</span></span>|
|<span data-ttu-id="a1398-261">PowerApps Formula</span><span class="sxs-lookup"><span data-stu-id="a1398-261">Power Apps Formula</span></span>|<span data-ttu-id="a1398-262">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="a1398-262">powerappsfl</span></span>|
|<span data-ttu-id="a1398-263">PowerShell</span><span class="sxs-lookup"><span data-stu-id="a1398-263">PowerShell</span></span>|<span data-ttu-id="a1398-264">powershell</span><span class="sxs-lookup"><span data-stu-id="a1398-264">powershell</span></span>|
|<span data-ttu-id="a1398-265">Python</span><span class="sxs-lookup"><span data-stu-id="a1398-265">Python</span></span>|<span data-ttu-id="a1398-266">python</span><span class="sxs-lookup"><span data-stu-id="a1398-266">python</span></span>|
|<span data-ttu-id="a1398-267">Q#</span><span class="sxs-lookup"><span data-stu-id="a1398-267">Q#</span></span>|<span data-ttu-id="a1398-268">qsharp</span><span class="sxs-lookup"><span data-stu-id="a1398-268">qsharp</span></span>|
|<span data-ttu-id="a1398-269">R</span><span class="sxs-lookup"><span data-stu-id="a1398-269">R</span></span>|<span data-ttu-id="a1398-270">r</span><span class="sxs-lookup"><span data-stu-id="a1398-270">r</span></span>|
|<span data-ttu-id="a1398-271">Ruby</span><span class="sxs-lookup"><span data-stu-id="a1398-271">Ruby</span></span>|<span data-ttu-id="a1398-272">ruby</span><span class="sxs-lookup"><span data-stu-id="a1398-272">ruby</span></span>|
|<span data-ttu-id="a1398-273">SQL</span><span class="sxs-lookup"><span data-stu-id="a1398-273">SQL</span></span>|<span data-ttu-id="a1398-274">sql</span><span class="sxs-lookup"><span data-stu-id="a1398-274">sql</span></span>|
|<span data-ttu-id="a1398-275">Swift</span><span class="sxs-lookup"><span data-stu-id="a1398-275">Swift</span></span>|<span data-ttu-id="a1398-276">swift</span><span class="sxs-lookup"><span data-stu-id="a1398-276">swift</span></span>|
|<span data-ttu-id="a1398-277">TypeScript</span><span class="sxs-lookup"><span data-stu-id="a1398-277">TypeScript</span></span>|<span data-ttu-id="a1398-278">typescript</span><span class="sxs-lookup"><span data-stu-id="a1398-278">typescript</span></span>|
|<span data-ttu-id="a1398-279">VB</span><span class="sxs-lookup"><span data-stu-id="a1398-279">VB</span></span>|<span data-ttu-id="a1398-280">vb</span><span class="sxs-lookup"><span data-stu-id="a1398-280">vb</span></span>|
|<span data-ttu-id="a1398-281">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="a1398-281">VSTS CLI</span></span>|<span data-ttu-id="a1398-282">vstscli</span><span class="sxs-lookup"><span data-stu-id="a1398-282">vstscli</span></span>|
|<span data-ttu-id="a1398-283">XAML</span><span class="sxs-lookup"><span data-stu-id="a1398-283">XAML</span></span>|<span data-ttu-id="a1398-284">xaml</span><span class="sxs-lookup"><span data-stu-id="a1398-284">xaml</span></span>|
|<span data-ttu-id="a1398-285">XML</span><span class="sxs-lookup"><span data-stu-id="a1398-285">XML</span></span>|<span data-ttu-id="a1398-286">xml</span><span class="sxs-lookup"><span data-stu-id="a1398-286">xml</span></span>|

<span data-ttu-id="a1398-287">Nazwa `csharp-interactive` określa język C# oraz wskazuje na możliwość uruchamiania przykładów w przeglądarce.</span><span class="sxs-lookup"><span data-stu-id="a1398-287">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="a1398-288">Te fragmenty kodu są kompilowane i wykonywane w kontenerze platformy Docker, a wyniki wykonywania programu są wyświetlane w oknie przeglądarki użytkownika.</span><span class="sxs-lookup"><span data-stu-id="a1398-288">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="a1398-289">Przykład: C\#</span><span class="sxs-lookup"><span data-stu-id="a1398-289">Example: C\#</span></span>

<span data-ttu-id="a1398-290">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="a1398-290">__Markdown__</span></span>

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

<span data-ttu-id="a1398-291">__Renderowanie__</span><span class="sxs-lookup"><span data-stu-id="a1398-291">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="a1398-292">Przykład: SQL</span><span class="sxs-lookup"><span data-stu-id="a1398-292">Example: SQL</span></span>

<span data-ttu-id="a1398-293">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="a1398-293">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="a1398-294">__Renderowanie__</span><span class="sxs-lookup"><span data-stu-id="a1398-294">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="a1398-295">Niestandardowe rozszerzenia języka Markdown na platformie OPS</span><span class="sxs-lookup"><span data-stu-id="a1398-295">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="a1398-296">Platforma Open Publishing Services (OPS) umożliwia implementowanie parsera Markdig dla języka Markdown o wysokim stopniu zgodności z językiem GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="a1398-296">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="a1398-297">Parser Markdig dodaje pewne funkcje za pośrednictwem rozszerzeń języka Markdown.</span><span class="sxs-lookup"><span data-stu-id="a1398-297">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="a1398-298">Wybrane artykuły z pełnego podręcznika tworzenia platformy OPS jako takie zostały dołączone do tego przewodnika do celów informacyjnych.</span><span class="sxs-lookup"><span data-stu-id="a1398-298">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="a1398-299">(Przykład można znaleźć w częściach „Rozszerzenia parsera Markdig i języka Markdown” oraz „Fragmenty kodu” dostępnych w spisie treści).</span><span class="sxs-lookup"><span data-stu-id="a1398-299">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="a1398-300">W artykułach z witryny Docs rozwiązanie GFM jest używane na potrzeby większości elementów formatowania artykułów, takich jak akapity, linki, listy i nagłówki.</span><span class="sxs-lookup"><span data-stu-id="a1398-300">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="a1398-301">W celu skorzystania z bardziej zaawansowanego formatowania można w artykułach użyć funkcji parsera Markdig, takich jak:</span><span class="sxs-lookup"><span data-stu-id="a1398-301">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="a1398-302">Bloki uwag</span><span class="sxs-lookup"><span data-stu-id="a1398-302">Note blocks</span></span>
- <span data-ttu-id="a1398-303">Operacje dołączania</span><span class="sxs-lookup"><span data-stu-id="a1398-303">Includes</span></span>
- <span data-ttu-id="a1398-304">Selektory</span><span class="sxs-lookup"><span data-stu-id="a1398-304">Selectors</span></span>
- <span data-ttu-id="a1398-305">Osadzone filmy wideo</span><span class="sxs-lookup"><span data-stu-id="a1398-305">Embedded videos</span></span>
- <span data-ttu-id="a1398-306">Fragmenty/przykłady kodu</span><span class="sxs-lookup"><span data-stu-id="a1398-306">Code snippets/samples</span></span>

<span data-ttu-id="a1398-307">Kompletną listę można znaleźć w częściach „Rozszerzenia parsera Markdig i języka Markdown” oraz „Fragmenty kodu” dostępnych w spisie treści.</span><span class="sxs-lookup"><span data-stu-id="a1398-307">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="a1398-308">Bloki uwag</span><span class="sxs-lookup"><span data-stu-id="a1398-308">Note blocks</span></span>

<span data-ttu-id="a1398-309">Aby zwrócić uwagę czytelnika na określoną zawartość, można wybrać jeden z czterech typów bloków uwag:</span><span class="sxs-lookup"><span data-stu-id="a1398-309">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="a1398-310">UWAGA</span><span class="sxs-lookup"><span data-stu-id="a1398-310">NOTE</span></span>
- <span data-ttu-id="a1398-311">OSTRZEŻENIE</span><span class="sxs-lookup"><span data-stu-id="a1398-311">WARNING</span></span>
- <span data-ttu-id="a1398-312">PORADA</span><span class="sxs-lookup"><span data-stu-id="a1398-312">TIP</span></span>
- <span data-ttu-id="a1398-313">WAŻNE</span><span class="sxs-lookup"><span data-stu-id="a1398-313">IMPORTANT</span></span>

<span data-ttu-id="a1398-314">Ogólnie rzecz biorąc, bloków uwag należy używać oszczędnie, ponieważ mogą zaburzać czytelność artykułu.</span><span class="sxs-lookup"><span data-stu-id="a1398-314">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="a1398-315">Obsługują one również bloki kodu, obrazy, listy i linki, ale należy starać się, aby były proste i czytelne.</span><span class="sxs-lookup"><span data-stu-id="a1398-315">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="a1398-316">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="a1398-316">Examples:</span></span>

```markdown
> [!NOTE]
> This is a NOTE

> [!WARNING]
> This is a WARNING

> [!TIP]
> This is a TIP

> [!IMPORTANT]
> This is IMPORTANT
```

<span data-ttu-id="a1398-317">Zostaną one wyrenderowane następująco:</span><span class="sxs-lookup"><span data-stu-id="a1398-317">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="a1398-318">To jest UWAGA</span><span class="sxs-lookup"><span data-stu-id="a1398-318">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="a1398-319">To jest OSTRZEŻENIE</span><span class="sxs-lookup"><span data-stu-id="a1398-319">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="a1398-320">To jest PORADA</span><span class="sxs-lookup"><span data-stu-id="a1398-320">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1398-321">To jest WAŻNE</span><span class="sxs-lookup"><span data-stu-id="a1398-321">This is IMPORTANT</span></span>

### <a name="includes"></a><span data-ttu-id="a1398-322">Operacje dołączania</span><span class="sxs-lookup"><span data-stu-id="a1398-322">Includes</span></span>

<span data-ttu-id="a1398-323">Jeśli masz pliki tekstu lub obrazów do wielokrotnego użytku, które chcesz dołączyć do plików artykułu, możesz użyć odwołania do pliku dołączania za pomocą funkcji dołączania plików w parserze Markdig.</span><span class="sxs-lookup"><span data-stu-id="a1398-323">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="a1398-324">Ta funkcja nakazuje platformie OPS dołączenie pliku do pliku artykułu podczas kompilacji, co sprawia, że plik staje się częścią publikowanego artykułu.</span><span class="sxs-lookup"><span data-stu-id="a1398-324">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="a1398-325">Istnieją trzy typy operacji dołączania, które ułatwiają wielokrotne użycie zawartości:</span><span class="sxs-lookup"><span data-stu-id="a1398-325">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="a1398-326">Śródwierszowe: wielokrotne użycie typowego fragmentu tekstu jako śródwierszowego w innym zdaniu.</span><span class="sxs-lookup"><span data-stu-id="a1398-326">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="a1398-327">Blokowe: wielokrotne użycie całego pliku Markdown jako bloku zagnieżdżonego w sekcji artykułu.</span><span class="sxs-lookup"><span data-stu-id="a1398-327">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="a1398-328">Obraz: jest to standardowa operacja dołączania implementowana w witrynie Docs.</span><span class="sxs-lookup"><span data-stu-id="a1398-328">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="a1398-329">Śródwierszowe i blokowe operacje dołączania dotyczą prostego pliku Markdown (md).</span><span class="sxs-lookup"><span data-stu-id="a1398-329">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="a1398-330">Może on zawierać dowolny prawidłowy kod w języku Markdown.</span><span class="sxs-lookup"><span data-stu-id="a1398-330">It can contain any valid Markdown.</span></span> <span data-ttu-id="a1398-331">Wszystkie dołączane pliki Markdown należy umieścić we [wspólnym podkatalogu `/includes`](git-github-fundamentals.md#includes-subdirectory) w głównym katalogu repozytorium.</span><span class="sxs-lookup"><span data-stu-id="a1398-331">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="a1398-332">Podczas publikowania artykułu dołączany plik jest płynnie z nim integrowany.</span><span class="sxs-lookup"><span data-stu-id="a1398-332">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="a1398-333">Poniżej przedstawiono wymagania i uwagi dotyczące operacji dołączania:</span><span class="sxs-lookup"><span data-stu-id="a1398-333">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="a1398-334">Operacji dołączania należy używać, gdy ten sam tekst ma pojawiać się w wielu artykułach.</span><span class="sxs-lookup"><span data-stu-id="a1398-334">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="a1398-335">Blokowe operacje dołączania są używane w przypadku znaczących ilości zawartości — akapitu lub dwóch, procedury udostępnianej lub sekcji udostępnianej.</span><span class="sxs-lookup"><span data-stu-id="a1398-335">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="a1398-336">Nie należy ich używać dla części mniejszych niż zdanie.</span><span class="sxs-lookup"><span data-stu-id="a1398-336">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="a1398-337">Operacje dołączania nie będą renderowane w renderowanym widoku Twojego artykułu w usłudze GitHub, ponieważ korzystają z rozszerzeń parsera Markdig.</span><span class="sxs-lookup"><span data-stu-id="a1398-337">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="a1398-338">Będą one renderowane tylko po publikacji.</span><span class="sxs-lookup"><span data-stu-id="a1398-338">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="a1398-339">Upewnij się, że cały tekst w operacji dołączania został napisany w postaci kompletnych zdań lub fraz, które nie zależą od poprzedniego ani następującego tekstu w artykule odwołującym się do dołączenia.</span><span class="sxs-lookup"><span data-stu-id="a1398-339">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="a1398-340">Zignorowanie tej wskazówki spowoduje powstanie w artykule ciągu niemożliwego do przetłumaczenia, który zakłóci spójność zlokalizowanego tekstu.</span><span class="sxs-lookup"><span data-stu-id="a1398-340">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="a1398-341">Operacji dołączania nie należy osadzać w innych dołączeniach.</span><span class="sxs-lookup"><span data-stu-id="a1398-341">Don't embed includes within other includes.</span></span> <span data-ttu-id="a1398-342">Nie są one obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="a1398-342">They are not supported.</span></span>
- <span data-ttu-id="a1398-343">Umieść pliki multimedialne w folderze media, który jest specyficzny dla podkatalogu include — na przykład w folderze `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="a1398-343">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="a1398-344">Katalog główny względem katalogu multimediów nie powinien zawierać obrazów.</span><span class="sxs-lookup"><span data-stu-id="a1398-344">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="a1398-345">Jeśli dołączenie nie zawiera obrazów, odpowiadający mu katalog multimediów nie jest wymagany.</span><span class="sxs-lookup"><span data-stu-id="a1398-345">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="a1398-346">Podobnie jak w przypadku zwykłych artykułów nie należy udostępniać multimediów między dołączanymi plikami.</span><span class="sxs-lookup"><span data-stu-id="a1398-346">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="a1398-347">Użyj oddzielnego pliku z unikatową nazwą dla każdego dołączenia i artykułu.</span><span class="sxs-lookup"><span data-stu-id="a1398-347">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="a1398-348">Plik multimedialny należy przechowywać w folderze media skojarzonym z dołączeniem.</span><span class="sxs-lookup"><span data-stu-id="a1398-348">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="a1398-349">Nie należy używać dołączenia jako jedynej zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="a1398-349">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="a1398-350">Operacje dołączania mają stanowić uzupełnienie pozostałej zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="a1398-350">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="a1398-351">Przykład:</span><span class="sxs-lookup"><span data-stu-id="a1398-351">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="a1398-352">Selektory</span><span class="sxs-lookup"><span data-stu-id="a1398-352">Selectors</span></span>

<span data-ttu-id="a1398-353">Selektorów należy używać w tworzonych artykułach technicznych z wieloma wariantami tego samego artykułu w celu przedstawienia różnic między implementacjami w ramach różnych technologii lub platform.</span><span class="sxs-lookup"><span data-stu-id="a1398-353">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="a1398-354">Ma to przeważnie zastosowanie w przypadku mobilnej zawartości platformy dla deweloperów.</span><span class="sxs-lookup"><span data-stu-id="a1398-354">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="a1398-355">Obecnie w parserze Markdig istnieją dwa różne typy selektorów: selektor pojedynczy i selektor wielokrotny.</span><span class="sxs-lookup"><span data-stu-id="a1398-355">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="a1398-356">Ponieważ ten sam kod języka Markdown selektora znajduje się w każdym artykule w zaznaczeniu, zalecamy umieszczanie selektora artykułu w dołączeniu.</span><span class="sxs-lookup"><span data-stu-id="a1398-356">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="a1398-357">Następnie można się odwołać do tego dołączenia we wszystkich artykułach, które używają tego samego selektora.</span><span class="sxs-lookup"><span data-stu-id="a1398-357">Then you can reference that include in all your articles that use the same selector.</span></span>

<span data-ttu-id="a1398-358">Poniżej znajduje się przykładowy selektor:</span><span class="sxs-lookup"><span data-stu-id="a1398-358">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="a1398-359">Przykładowe selektory można znaleźć w [dokumentacji platformy Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="a1398-359">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-includes"></a><span data-ttu-id="a1398-360">Operacje dołączania kodu</span><span class="sxs-lookup"><span data-stu-id="a1398-360">Code includes</span></span>

<span data-ttu-id="a1398-361">Parser Markdig obsługuje zaawansowane dołączanie kodu do artykułu za pośrednictwem rozszerzenia fragmentu kodu.</span><span class="sxs-lookup"><span data-stu-id="a1398-361">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="a1398-362">Oferuje ono zaawansowane możliwości renderowania współpracujące z funkcjami GFM, takie jak wybór języka programowania i kolorowanie składni, oraz użyteczne funkcje, takie jak:</span><span class="sxs-lookup"><span data-stu-id="a1398-362">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="a1398-363">dołączanie scentralizowanych przykładów/fragmentów kodu z repozytorium zewnętrznego;</span><span class="sxs-lookup"><span data-stu-id="a1398-363">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="a1398-364">interfejs użytkownika z kartami przedstawiającymi wiele wersji przykładów kodu w różnych językach.</span><span class="sxs-lookup"><span data-stu-id="a1398-364">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="a1398-365">Problemy i ich rozwiązywanie</span><span class="sxs-lookup"><span data-stu-id="a1398-365">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="a1398-366">Tekst alternatywny</span><span class="sxs-lookup"><span data-stu-id="a1398-366">Alt text</span></span>

<span data-ttu-id="a1398-367">Nie można prawidłowo renderować tekstu alternatywnego, który zawiera znaki podkreślenia.</span><span class="sxs-lookup"><span data-stu-id="a1398-367">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="a1398-368">Na przykład zamiast używać tego:</span><span class="sxs-lookup"><span data-stu-id="a1398-368">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="a1398-369">Omiń podkreślenia w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="a1398-369">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="a1398-370">Apostrofy i cudzysłowy</span><span class="sxs-lookup"><span data-stu-id="a1398-370">Apostrophes and quotation marks</span></span>

<span data-ttu-id="a1398-371">W przypadku kopiowania z programu Word do edytora języka Markdown tekst może zawierać „eleganckie” (zawinięte) apostrofy lub cudzysłowy.</span><span class="sxs-lookup"><span data-stu-id="a1398-371">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="a1398-372">Należy je zakodować lub zmienić na podstawowe apostrofy lub znaki cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="a1398-372">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="a1398-373">W przeciwnym razie po opublikowaniu pliku otrzymasz coś takiego: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="a1398-373">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="a1398-374">Oto sposoby kodowania „eleganckich” wersji tych znaków interpunkcyjnych:</span><span class="sxs-lookup"><span data-stu-id="a1398-374">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="a1398-375">Lewy cudzysłów (otwierający): `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="a1398-375">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="a1398-376">Prawy cudzysłów (zamykający): `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="a1398-376">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="a1398-377">Prawy pojedynczy cudzysłów lub apostrof (zamykający): `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="a1398-377">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="a1398-378">Lewy pojedynczy cudzysłów (otwierający) (rzadko używany): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="a1398-378">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="a1398-379">Nawiasy kątowe</span><span class="sxs-lookup"><span data-stu-id="a1398-379">Angle brackets</span></span>

<span data-ttu-id="a1398-380">Często stosuje się nawiasy kątowe w celu oznaczenia symbolu zastępczego.</span><span class="sxs-lookup"><span data-stu-id="a1398-380">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="a1398-381">W przypadku użycia nawiasów kątowych w tekście (nie w kodzie) należy je zakodować.</span><span class="sxs-lookup"><span data-stu-id="a1398-381">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="a1398-382">W przeciwnym razie w języku Markdown nawiasy kątowe zostaną potraktowane jak tag HTML.</span><span class="sxs-lookup"><span data-stu-id="a1398-382">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="a1398-383">Na przykład `<script name>` należy zakodować jako `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="a1398-383">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="a1398-384">Zobacz też:</span><span class="sxs-lookup"><span data-stu-id="a1398-384">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="a1398-385">Zasoby dotyczące języka Markdown</span><span class="sxs-lookup"><span data-stu-id="a1398-385">Markdown resources</span></span>

- <span data-ttu-id="a1398-386">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Wprowadzenie do języka Markdown)</span><span class="sxs-lookup"><span data-stu-id="a1398-386">[Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax)</span></span>
- [<span data-ttu-id="a1398-387">Docs Markdown cheat-sheet (Ściągawka dotycząca języka Markdown w witrynie Docs)</span><span class="sxs-lookup"><span data-stu-id="a1398-387">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- <span data-ttu-id="a1398-388">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (Podstawy języka Markdown w serwisie GitHub)</span><span class="sxs-lookup"><span data-stu-id="a1398-388">[GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/)</span></span>
- [<span data-ttu-id="a1398-389">The Markdown Guide</span><span class="sxs-lookup"><span data-stu-id="a1398-389">The Markdown Guide</span></span>](https://www.markdownguide.org/)
