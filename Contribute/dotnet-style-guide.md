---
title: Szablon i ściągawka do artykułów dotyczących platformy .NET
description: Ten artykuł zawiera podręczny szablon, który ułatwia tworzenie artykułów dla repozytoriów dokumentów platformy .NET
ms.date: 11/07/2018
ms.openlocfilehash: 15f64ec86c475e2da2f6539c8f388d076389c4e0
ms.sourcegitcommit: 68d81b61ffa60aba16acfed023760449e16de91b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2018
ms.locfileid: "52299665"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a><span data-ttu-id="f20ca-103">Szablon metadanych i szablon języka Markdown dla dokumentów platformy .NET</span><span class="sxs-lookup"><span data-stu-id="f20ca-103">Metadata and Markdown template for .NET docs</span></span>

<span data-ttu-id="f20ca-104">Ten szablon z repozytorium dotnet/docs zawiera przykładową składnię języka Markdown oraz wskazówki dotyczące ustawiania metadanych.</span><span class="sxs-lookup"><span data-stu-id="f20ca-104">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span>

<span data-ttu-id="f20ca-105">Tworząc plik Markdown, skopiuj załączony szablon do nowego pliku, wypełnij metadane zgodnie z poniższym opisem i ustaw nagłówek H1 na tytuł artykułu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-105">When creating a Markdown file, you should copy the included template to a new file, fill out the metadata as specified below, and set the H1 heading above to the title of the article.</span></span>

## <a name="metadata"></a><span data-ttu-id="f20ca-106">Metadane</span><span class="sxs-lookup"><span data-stu-id="f20ca-106">Metadata</span></span>

<span data-ttu-id="f20ca-107">Poniższy przykład zawiera wymagany blok metadanych:</span><span class="sxs-lookup"><span data-stu-id="f20ca-107">The required metadata block is in the following sample metadata block:</span></span>

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- <span data-ttu-id="f20ca-108">Miedzy dwukropkiem (:) a wartością elementu metadanych **musi** znajdować się spacja.</span><span class="sxs-lookup"><span data-stu-id="f20ca-108">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="f20ca-109">Obecność dwukropków w wartości (na przykład w tytule) zakłóca działanie analizatora metadanych.</span><span class="sxs-lookup"><span data-stu-id="f20ca-109">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="f20ca-110">W takim przypadku należy ująć tytuł w podwójny cudzysłów (na przykład `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="f20ca-110">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="f20ca-111">**title**: ta wartość pojawia się w wynikach wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="f20ca-111">**title**: Appears in search engine results.</span></span> <span data-ttu-id="f20ca-112">Tytuł nie powinien być taki sam jak tytuł w nagłówku H1. Ponadto może on zawierać maksymalnie 60 znaków.</span><span class="sxs-lookup"><span data-stu-id="f20ca-112">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="f20ca-113">**description**: podsumowanie zawartości artykułu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-113">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="f20ca-114">Ta wartość zwykle pojawia się na stronie z wynikami wyszukiwania, ale nie jest używana do klasyfikacji wyszukiwania.</span><span class="sxs-lookup"><span data-stu-id="f20ca-114">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="f20ca-115">Liczba znaków (łącznie ze spacjami) powinna mieścić się w przedziale od 115 do 145.</span><span class="sxs-lookup"><span data-stu-id="f20ca-115">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="f20ca-116">**author**: pole autora powinno zawierać **nazwę użytkownika w usłudze GitHub**.</span><span class="sxs-lookup"><span data-stu-id="f20ca-116">**author**: The author field should contain the **GitHub username** of the author.</span></span>
- <span data-ttu-id="f20ca-117">**ms.date**: data ostatniej ważnej aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="f20ca-117">**ms.date**: The date of the last significant update.</span></span> <span data-ttu-id="f20ca-118">Tę wartość należy aktualizować w przypadku artykułów, które zostały zmodyfikowane podczas przeglądania.</span><span class="sxs-lookup"><span data-stu-id="f20ca-118">Update this on existing articles if you reviewed and updated the entire article.</span></span> <span data-ttu-id="f20ca-119">Drobniejsze poprawki, na przykład literówki, nie wymagają aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="f20ca-119">Small fixes, such as typos or similar do not warrant an update.</span></span>

<span data-ttu-id="f20ca-120">Do poszczególnych artykułów są dołączone inne metadane, ale większość wartości metadanych zwykle stosuje się na poziomie folderu za pośrednictwem pliku **docfx.json**.</span><span class="sxs-lookup"><span data-stu-id="f20ca-120">Other metadata is attached to each article, but we typically apply most metadata values at the folder level, specified in **docfx.json**.</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="f20ca-121">Podstawowa składnia Markdown, elementy GFM i znaki specjalne</span><span class="sxs-lookup"><span data-stu-id="f20ca-121">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="f20ca-122">Podstawowe informacje o językach Markdown i GitHub Flavored Markdown (GFM) oraz rozszerzeniach specyficznych dla platformy OPS można znaleźć w ogólnym artykule dotyczącym [języka Markdown](how-to-write-use-markdown.md) oraz w [dokumentacji języka Markdown](markdown-reference.md).</span><span class="sxs-lookup"><span data-stu-id="f20ca-122">You can learn the basics of Markdown, GitHub Flavored Markdown (GFM), and OPS specific extensions in the general articles on [Markdown](how-to-write-use-markdown.md) and [Markdown reference](markdown-reference.md).</span></span>

<span data-ttu-id="f20ca-123">Formatowanie w języku Markdown wymaga użycia znaków specjalnych, takich jak \*, \` i \#.</span><span class="sxs-lookup"><span data-stu-id="f20ca-123">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="f20ca-124">Jeśli chcesz dodać do zawartości jeden z tych znaków, musisz wykonać jedną z tych czynności:</span><span class="sxs-lookup"><span data-stu-id="f20ca-124">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="f20ca-125">Zastosuj znak ucieczki — umieść ukośnik odwrotny przed znakiem specjalnym (na przykład dodaj ciąg `\*`, aby uzyskać znak \*).</span><span class="sxs-lookup"><span data-stu-id="f20ca-125">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="f20ca-126">Użyj [kodu encji HTML](http://www.ascii.cl/htmlcodes.htm) dla danego znaku (na przykład dodaj ciąg `&#42;`, aby uzyskać znak &#42;).</span><span class="sxs-lookup"><span data-stu-id="f20ca-126">Use the [HTML entity code](http://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-names"></a><span data-ttu-id="f20ca-127">Nazwy plików</span><span class="sxs-lookup"><span data-stu-id="f20ca-127">File names</span></span>

<span data-ttu-id="f20ca-128">W przypadku nazw plików obowiązują następujące reguły:</span><span class="sxs-lookup"><span data-stu-id="f20ca-128">File names use the following rules:</span></span>

* <span data-ttu-id="f20ca-129">Można używać tylko małych liter, cyfr i łączników.</span><span class="sxs-lookup"><span data-stu-id="f20ca-129">Contain only lowercase letters, numbers, and hyphens.</span></span>
* <span data-ttu-id="f20ca-130">Bez spacji i znaków interpunkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="f20ca-130">No spaces or punctuation characters.</span></span> <span data-ttu-id="f20ca-131">Wyrazy i liczby w nazwie pliku powinny być oddzielane łącznikami.</span><span class="sxs-lookup"><span data-stu-id="f20ca-131">Use the hyphens to separate words and numbers in the file name.</span></span>
* <span data-ttu-id="f20ca-132">Należy używać czasowników oznaczających określoną akcję, np. „develop”, „buy”, „build”, „troubleshoot”.</span><span class="sxs-lookup"><span data-stu-id="f20ca-132">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="f20ca-133">Bez wyrazów zakończonych na „-ing”.</span><span class="sxs-lookup"><span data-stu-id="f20ca-133">No -ing words.</span></span>
* <span data-ttu-id="f20ca-134">Bez krótkich wyrazów, takich jak „a”, „and”, „the”, „in”, „or” itp.</span><span class="sxs-lookup"><span data-stu-id="f20ca-134">No small words - don't include a, and, the, in, or, etc.</span></span>
* <span data-ttu-id="f20ca-135">Nazwa musi być podana w języku znaczników Markdown i mieć rozszerzenie pliku MD.</span><span class="sxs-lookup"><span data-stu-id="f20ca-135">Must be in Markdown and use the .md file extension.</span></span>
* <span data-ttu-id="f20ca-136">Nazwy plików powinny być względnie krótkie.</span><span class="sxs-lookup"><span data-stu-id="f20ca-136">Keep file names reasonably short.</span></span> <span data-ttu-id="f20ca-137">Stanowią one część adresów URL artykułów.</span><span class="sxs-lookup"><span data-stu-id="f20ca-137">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="f20ca-138">Nagłówki</span><span class="sxs-lookup"><span data-stu-id="f20ca-138">Headings</span></span>

<span data-ttu-id="f20ca-139">Wielkość liter powinna być taka jak w zdaniu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-139">Use sentence-style capitalization.</span></span> <span data-ttu-id="f20ca-140">Pierwszy wyraz nagłówka musi w każdym przypadku zaczynać się od wielkiej litery.</span><span class="sxs-lookup"><span data-stu-id="f20ca-140">Always capitalize the first word of a heading.</span></span>

## <a name="text-styling"></a><span data-ttu-id="f20ca-141">Styl tekstu</span><span class="sxs-lookup"><span data-stu-id="f20ca-141">Text styling</span></span>

<span data-ttu-id="f20ca-142">*Kursywa* Należy ją stosować w przypadku plików, folderów, ścieżek (długie ciągi należy rozdzielić na dodatkowe wiersze) i nowych terminów.</span><span class="sxs-lookup"><span data-stu-id="f20ca-142">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="f20ca-143">**Pogrubienie** Należy je stosować w przypadku elementów interfejsu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="f20ca-143">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="f20ca-144">`Code` Ten element należy stosować w przypadku kodu wbudowanego, słów kluczowych języka, nazw pakietów NuGet, poleceń używanych w wierszu polecenia, nazw tabeli i kolumn w bazie danych oraz adresów URL, które nie są przeznaczone do klikania.</span><span class="sxs-lookup"><span data-stu-id="f20ca-144">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="f20ca-145">Linki</span><span class="sxs-lookup"><span data-stu-id="f20ca-145">Links</span></span>

<span data-ttu-id="f20ca-146">Informacje dotyczące kotwic, linków wewnętrznych, linków prowadzących do innych dokumentów, klauzuli dołączeń w kodzie oraz linków zewnętrznych można znaleźć w ogólnym artykule [Links](how-to-write-links.md) (Linki).</span><span class="sxs-lookup"><span data-stu-id="f20ca-146">See the general article on [Links](how-to-write-links.md) for information about anchors, internal links, links to other documents, code includes, and external links.</span></span>

<span data-ttu-id="f20ca-147">Zespół, który zajmuje się dokumentacją platformy .NET stosuje następujące konwencje:</span><span class="sxs-lookup"><span data-stu-id="f20ca-147">The .NET docs team uses the following conventions:</span></span>

- <span data-ttu-id="f20ca-148">W większości przypadków używamy linków względnych. Unikamy używania elementu `~/`, ponieważ linki względne są rozpoznawane w źródle w usłudze GitHub.</span><span class="sxs-lookup"><span data-stu-id="f20ca-148">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="f20ca-149">Jednak w przypadku linków do plików znajdujących się w repozytorium zależnym ścieżka jest podawana za pomocą znaku `~/`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-149">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="f20ca-150">Pliki z repozytorium zależnego znajdują się w innej lokalizacji w usłudze GitHub, dlatego linki względne nie zostaną poprawnie rozpoznane, niezależnie od tego, jak zostały napisane.</span><span class="sxs-lookup"><span data-stu-id="f20ca-150">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>
- <span data-ttu-id="f20ca-151">Dodanie specyfikacji języków C# i Visual Basic do dokumentacji platformy .NET odbywa się przez dołączenie źródła z repozytoriów języka.</span><span class="sxs-lookup"><span data-stu-id="f20ca-151">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="f20ca-152">Źródła elementów markdown są zarządzane w repozytoriach [csharplang](https://github.com/dotnet/csharplang) i [vblang](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="f20ca-152">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [vblang](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="f20ca-153">Linki do specyfikacji muszą prowadzić do katalogów źródłowych, które zawierają te specyfikacje.</span><span class="sxs-lookup"><span data-stu-id="f20ca-153">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="f20ca-154">W przypadku języka C# jest to **~/_csharplang/spec**, a w przypadku języka VB jest to **~/_vblang/spec**, jak w poniższym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="f20ca-154">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**, as in the following example:</span></span>

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a><span data-ttu-id="f20ca-155">Linki do interfejsów API</span><span class="sxs-lookup"><span data-stu-id="f20ca-155">Links to APIs</span></span>

<span data-ttu-id="f20ca-156">System kompilacji jest wyposażony w rozszerzenia, które umożliwiają tworzenie połączeń z interfejsami API platformy .NET bez używania linków zewnętrznych.</span><span class="sxs-lookup"><span data-stu-id="f20ca-156">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span> <span data-ttu-id="f20ca-157">Można użyć jednej z następujących składni:</span><span class="sxs-lookup"><span data-stu-id="f20ca-157">You use one of the following syntax:</span></span>

1. <span data-ttu-id="f20ca-158">Link automatyczny: `<xref:UID>` lub `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="f20ca-158">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="f20ca-159">Parametr zapytania `displayProperty` prowadzi do utworzenia tekstu z w pełni kwalifikowanym linkiem.</span><span class="sxs-lookup"><span data-stu-id="f20ca-159">The `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="f20ca-160">Domyślnie tekst linku zawiera tylko nazwę elementu członkowskiego lub typu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-160">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="f20ca-161">Link języka Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="f20ca-161">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="f20ca-162">Jest używany, aby można było dostosować wyświetlany tekst linku.</span><span class="sxs-lookup"><span data-stu-id="f20ca-162">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="f20ca-163">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="f20ca-163">Examples:</span></span>

- <span data-ttu-id="f20ca-164">`<xref:System.String>` jest renderowany jako [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="f20ca-164">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="f20ca-165">`<xref:System.String?displayProperty=nameWithType>` jest renderowany jako [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="f20ca-165">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="f20ca-166">`[String class](xref:System.String)` jest renderowany jako [klasa String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="f20ca-166">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="f20ca-167">Aby uzyskać więcej informacji na temat używania tej notacji, zobacz artykuł [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference) (Używanie odsyłacza).</span><span class="sxs-lookup"><span data-stu-id="f20ca-167">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="f20ca-168">Niektóre identyfikatory UID zawierają znaki specjalne \`, \# lub \*. W takich przypadkach wartość UID musi być zakodowana w języku HTML odpowiednio jako `%60`, `%23` i `%2A`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-168">Some UIDs contain the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="f20ca-169">Czasami można zobaczyć zakodowane nawiasy, ale nie są one wymagane.</span><span class="sxs-lookup"><span data-stu-id="f20ca-169">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="f20ca-170">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="f20ca-170">Examples:</span></span>

- <span data-ttu-id="f20ca-171">System.Threading.Tasks.Task\`1 staje się `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="f20ca-171">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="f20ca-172">System.Exception.\#ctor staje się `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="f20ca-172">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="f20ca-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) staje się `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="f20ca-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<span data-ttu-id="f20ca-174">Na stronie `https://xref.docs.microsoft.com/autocomplete` można znaleźć identyfikatory UID typów, listę przeciążeń składowych lub konkretną przeciążoną składową.</span><span class="sxs-lookup"><span data-stu-id="f20ca-174">You can find the UIDs of types, a member overload list, or a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="f20ca-175">Ciąg zapytania `?text=*\<type-member-name>*` identyfikuje typ lub składową, której identyfikatory UID chcesz wyświetlić.</span><span class="sxs-lookup"><span data-stu-id="f20ca-175">The query string `?text=*\<type-member-name>*` identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="f20ca-176">Na przykład element `https://xref.docs.microsoft.com/autocomplete?text=string.format` pobiera przeciążenia metody [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="f20ca-176">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span> <span data-ttu-id="f20ca-177">Narzędzie szuka udostępnionego parametru zapytania `text` w każdej części identyfikatora UID.</span><span class="sxs-lookup"><span data-stu-id="f20ca-177">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="f20ca-178">Na przykład można wyszukiwać nazwę składowej (ToString), część nazwy składowej (ToStri), typ i nazwę składowej (Double.ToString) itp.</span><span class="sxs-lookup"><span data-stu-id="f20ca-178">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="f20ca-179">Po dodaniu elementu \* (lub `%2A`) po identyfikatorze UID link reprezentuje stronę przeciążenia, a nie określony interfejs API.</span><span class="sxs-lookup"><span data-stu-id="f20ca-179">If you add a \* (or `%2A`) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="f20ca-180">Możesz z tego skorzystać na przykład, gdy chcesz połączyć stronę [List\<T>.BinarySearch](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) w sposób ogólny, zamiast określonego przeciążenia, takiego jak [List\<T >.BinarySearch(T, IComparer\<T >)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="f20ca-180">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="f20ca-181">Możesz też użyć elementu \*, aby utworzyć link do strony nieprzeciążonej składowej. Dzięki temu nie musisz dołączać listy parametrów w identyfikatorze UID.</span><span class="sxs-lookup"><span data-stu-id="f20ca-181">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="f20ca-182">Aby utworzyć link do określonego przeciążenia metody, musisz dołączyć w pełni kwalifikowane nazwy typów wszystkich parametrów metody.</span><span class="sxs-lookup"><span data-stu-id="f20ca-182">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="f20ca-183">Na przykład element \<xref:System.DateTime.ToString> tworzy link do bezparametrowej metody [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), a element \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> tworzy link do metody [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="f20ca-183">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span>

<span data-ttu-id="f20ca-184">Aby utworzyć link do typu ogólnego, takiego jak [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), użyj znaku \` (`%60`), po którym podaj liczbę parametrów typu ogólnego.</span><span class="sxs-lookup"><span data-stu-id="f20ca-184">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (`%60`) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="f20ca-185">Na przykład element `<xref:System.Nullable%601>` tworzy link do typu [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), a element `<xref:System.Func%602>` tworzy link do delegata [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="f20ca-185">For example, `<xref:System.Nullable%601>` links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while `<xref:System.Func%602>` links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

## <a name="code"></a><span data-ttu-id="f20ca-186">Kod</span><span class="sxs-lookup"><span data-stu-id="f20ca-186">Code</span></span>

<span data-ttu-id="f20ca-187">Najlepsza metoda dodania kodu polega na dodaniu fragmentów z działającego przykładu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-187">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="f20ca-188">Utwórz własny przykład, wykonując instrukcje podane w artykule dotyczącym [współtworzenia platformy .NET](dotnet-contribute-process.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="f20ca-188">Create your sample following the instructions in the [contributing to .NET](dotnet-contribute-process.md#contributing-to-samples) article.</span></span> <span data-ttu-id="f20ca-189">Podstawowe reguły dołączania kodu można znaleźć w ogólnych wskazówkach dotyczących [kodu](how-to-write-use-markdown.md#code-includes).</span><span class="sxs-lookup"><span data-stu-id="f20ca-189">The basic rules for including code are located in the general guidance on [code](how-to-write-use-markdown.md#code-includes).</span></span>

<span data-ttu-id="f20ca-190">Kod możesz dołączyć za pomocą następującej składni:</span><span class="sxs-lookup"><span data-stu-id="f20ca-190">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* <span data-ttu-id="f20ca-191">`-<language>` (*opcjonalne*, ale *zalecane*)</span><span class="sxs-lookup"><span data-stu-id="f20ca-191">`-<language>` (*optional* but *recommended*)</span></span>
  * <span data-ttu-id="f20ca-192">Język fragmentu kodu, którego dotyczy odwołanie.</span><span class="sxs-lookup"><span data-stu-id="f20ca-192">Language of the code snippet being referenced.</span></span> <span data-ttu-id="f20ca-193">Listę obsługiwanych wartości można znaleźć w części [Obsługiwane języki](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="f20ca-193">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

* <span data-ttu-id="f20ca-194">`<name>` (*opcjonalnie*)</span><span class="sxs-lookup"><span data-stu-id="f20ca-194">`<name>` (*optional*)</span></span>
  * <span data-ttu-id="f20ca-195">Nazwa fragmentu kodu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-195">Name for the code snippet.</span></span> <span data-ttu-id="f20ca-196">Nie ma żadnego wpływu na wyjściowy kod HTML, ale dzięki niej można zwiększyć czytelność źródła języka Markdown.</span><span class="sxs-lookup"><span data-stu-id="f20ca-196">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

* <span data-ttu-id="f20ca-197">`<pathToFile>` (*obowiązkowa*)</span><span class="sxs-lookup"><span data-stu-id="f20ca-197">`<pathToFile>` (*mandatory*)</span></span>
  * <span data-ttu-id="f20ca-198">Ścieżka względna w systemie plików wskazująca plik fragmentu kodu, do którego ma zostać utworzone odwołanie.</span><span class="sxs-lookup"><span data-stu-id="f20ca-198">Relative path in the file system that indicates the code snippet file to reference.</span></span> <span data-ttu-id="f20ca-199">Może to okazać się skomplikowane ze względu na różne repozytoria, które należą do zestawu dokumentacji platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="f20ca-199">This can be complicated by the different repos that make up the .NET doc set.</span></span> <span data-ttu-id="f20ca-200">Przykłady z platformą .NET znajdują się w repozytorium dotnet/samples.</span><span class="sxs-lookup"><span data-stu-id="f20ca-200">The .NET samples are in the dotnet/samples repo.</span></span> <span data-ttu-id="f20ca-201">Wszystkie ścieżki do fragmentów kodu zaczynają się od ciągu `~/samples`. Pozostała część określa ścieżkę do źródła od katalogu głównego repozytorium.</span><span class="sxs-lookup"><span data-stu-id="f20ca-201">All snippet paths would start with `~/samples`, the rest of the path being the path to the source from the root of that repo.</span></span>

* <span data-ttu-id="f20ca-202">`<queryoption>` (*opcjonalnie*)</span><span class="sxs-lookup"><span data-stu-id="f20ca-202">`<queryoption>` (*optional*)</span></span>
  * <span data-ttu-id="f20ca-203">Używane w celu określenia sposobu pobierania kodu z pliku:</span><span class="sxs-lookup"><span data-stu-id="f20ca-203">Used to specify how the code should be retrieved from the file:</span></span>
    * <span data-ttu-id="f20ca-204">`#`:  `#{tagname}` (nazwa tagu) *lub* `#L{startlinenumber}-L{endlinenumber}` (zakres wierszy).</span><span class="sxs-lookup"><span data-stu-id="f20ca-204">`#`:  `#{tagname}` (tag name) *or* `#L{startlinenumber}-L{endlinenumber}` (line range).</span></span>
    <span data-ttu-id="f20ca-205">Odradzamy używanie numerów wierszy ze względu na ich wrażliwość.</span><span class="sxs-lookup"><span data-stu-id="f20ca-205">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="f20ca-206">Preferowana metoda odwoływania się do fragmentów kodu polega na używaniu nazw tagów.</span><span class="sxs-lookup"><span data-stu-id="f20ca-206">Tag name is the preferred way of referencing code snippets.</span></span> <span data-ttu-id="f20ca-207">Nazwy te powinny być opisowe.</span><span class="sxs-lookup"><span data-stu-id="f20ca-207">Use meaningful tag names.</span></span> <span data-ttu-id="f20ca-208">Wiele fragmentów kodu zostało zmigrowanych ze starszej platformy, a przykładowe nazwy tagów to `Snippet1`, `Snippet2` itd. Takie podejście znacznie utrudnia utrzymanie kodu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-208">(Many snippets were migrated from a previous platform and the tags have names such as `Snippet1`, `Snippet2` etc. That practice is much harder to maintain.)</span></span>
    * <span data-ttu-id="f20ca-209">`range`: `?range=1,3-5` Zakres wierszy.</span><span class="sxs-lookup"><span data-stu-id="f20ca-209">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="f20ca-210">Ten przykład obejmuje wiersze, 1, 3, 4 i 5.</span><span class="sxs-lookup"><span data-stu-id="f20ca-210">This example includes lines 1, 3, 4, and 5.</span></span>

<span data-ttu-id="f20ca-211">Zalecamy korzystanie z nazw tagów, gdy tylko jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="f20ca-211">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="f20ca-212">Nazwa tagu ma format `Snippettagname` i odpowiada nazwie regionu lub komentarzowi zawartemu w kodzie źródłowym.</span><span class="sxs-lookup"><span data-stu-id="f20ca-212">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="f20ca-213">W poniższym przykładzie pokazano, jak odwołać się do nazwy tagu `BasicThrow`:</span><span class="sxs-lookup"><span data-stu-id="f20ca-213">The following example shows how to refer to the tag name `BasicThrow`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

<span data-ttu-id="f20ca-214">Ścieżka względna do źródła w repozytorium **dotnet/samples** występuje po ścieżce `~/samples`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-214">The relative path to the source in the **dotnet/samples** repo follows the `~/samples` path.</span></span>

<span data-ttu-id="f20ca-215">[Ten plik źródłowy](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) pozwala zapoznać się ze strukturą tagów fragmentów kodu.</span><span class="sxs-lookup"><span data-stu-id="f20ca-215">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span></span> <span data-ttu-id="f20ca-216">Aby uzyskać szczegółowe informacje na temat reprezentacji nazwy tagu plikach źródłowych fragmentu kodu według języka, zobacz [wytyczne rozwiązania DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="f20ca-216">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="f20ca-217">Poniższy przykład przedstawia dołączenie kodu we wszystkich trzech językach platformy .NET:</span><span class="sxs-lookup"><span data-stu-id="f20ca-217">The following example shows code included in all three .NET languages:</span></span>

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

<span data-ttu-id="f20ca-218">Dołączenie fragmentów kodu z pełnych programów gwarantuje, że cały kod jest przetwarzany w systemie ciągłej integracji (CI).</span><span class="sxs-lookup"><span data-stu-id="f20ca-218">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="f20ca-219">Jeśli jednak chcesz zademonstrować błędy kompilacji lub błędy w czasie wykonywania, możesz użyć bloków kodu wbudowanego.</span><span class="sxs-lookup"><span data-stu-id="f20ca-219">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

## <a name="images"></a><span data-ttu-id="f20ca-220">Grafika</span><span class="sxs-lookup"><span data-stu-id="f20ca-220">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="f20ca-221">Obraz statyczny lub animowany obraz GIF</span><span class="sxs-lookup"><span data-stu-id="f20ca-221">Static image or animated GIF</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a><span data-ttu-id="f20ca-222">Połączony obraz</span><span class="sxs-lookup"><span data-stu-id="f20ca-222">Linked image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a><span data-ttu-id="f20ca-223">Wideo</span><span class="sxs-lookup"><span data-stu-id="f20ca-223">Videos</span></span>

<span data-ttu-id="f20ca-224">Aktualnie możesz osadzać filmy wideo z witryn Channel 9 i YouTube, korzystając z następującej składni:</span><span class="sxs-lookup"><span data-stu-id="f20ca-224">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="f20ca-225">Channel9</span><span class="sxs-lookup"><span data-stu-id="f20ca-225">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="f20ca-226">Aby pobrać poprawny adres URL filmu wideo, wybierz kartę **Osadzanie** widoczną pod klatką wideo i skopiuj adres URL z elementu `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-226">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="f20ca-227">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="f20ca-227">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="f20ca-228">YouTube</span><span class="sxs-lookup"><span data-stu-id="f20ca-228">YouTube</span></span>

<span data-ttu-id="f20ca-229">Aby pobrać poprawny adres URL filmu wideo, kliknij prawym przyciskiem myszy film wideo, wybierz polecenie **Skopiuj kod osadzania** i skopiuj adres URL z elementu `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="f20ca-229">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="f20ca-230">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="f20ca-230">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="f20ca-231">Rozszerzenia docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="f20ca-231">docs.microsoft extensions</span></span>

<span data-ttu-id="f20ca-232">Witryna docs.microsoft udostępnia kilka dodatkowych rozszerzeń języka GitHub Flavored Markdown.</span><span class="sxs-lookup"><span data-stu-id="f20ca-232">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="checked-lists"></a><span data-ttu-id="f20ca-233">Listy ze znacznikami wyboru</span><span class="sxs-lookup"><span data-stu-id="f20ca-233">Checked lists</span></span>

<span data-ttu-id="f20ca-234">W przypadku list dostępny jest styl niestandardowy.</span><span class="sxs-lookup"><span data-stu-id="f20ca-234">A custom style is available for lists.</span></span> <span data-ttu-id="f20ca-235">Można renderować listy z zielonymi znacznikami wyboru.</span><span class="sxs-lookup"><span data-stu-id="f20ca-235">You can render lists with green check marks.</span></span>

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

<span data-ttu-id="f20ca-236">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f20ca-236">This renders as:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="f20ca-237">How to create a .NET Core app</span><span class="sxs-lookup"><span data-stu-id="f20ca-237">How to create a .NET Core app</span></span>
> * <span data-ttu-id="f20ca-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span><span class="sxs-lookup"><span data-stu-id="f20ca-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="f20ca-239">How to edit your MyApp.csproj to add dependencies</span><span class="sxs-lookup"><span data-stu-id="f20ca-239">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="f20ca-240">How to add a class and an XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="f20ca-240">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="f20ca-241">How to build and run the application</span><span class="sxs-lookup"><span data-stu-id="f20ca-241">How to build and run the application</span></span>

<span data-ttu-id="f20ca-242">Przykładowe listy ze znacznikami wyboru można znaleźć w [dokumentacji platformy .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="f20ca-242">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="f20ca-243">Przyciski</span><span class="sxs-lookup"><span data-stu-id="f20ca-243">Buttons</span></span>

<span data-ttu-id="f20ca-244">Linki do przycisków:</span><span class="sxs-lookup"><span data-stu-id="f20ca-244">Button links:</span></span>

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

<span data-ttu-id="f20ca-245">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="f20ca-245">This renders as:</span></span>

> [!div class="button"]
[<span data-ttu-id="f20ca-246">button links</span><span class="sxs-lookup"><span data-stu-id="f20ca-246">button links</span></span>](dotnet-contribute.md)

<span data-ttu-id="f20ca-247">Przykładowe przyciski można znaleźć w [dokumentacji programu Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f20ca-247">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="f20ca-248">Przewodniki krok po kroku</span><span class="sxs-lookup"><span data-stu-id="f20ca-248">Step-by-steps</span></span>

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

<span data-ttu-id="f20ca-249">Przykładowe przewodniki krok po kroku można znaleźć w [przewodniku po języku C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="f20ca-249">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
