---
title: Dokumentacja języka Markdown dla platformy OPS i witryny docs.microsoft.com
description: Przewodnik platformy OPS dotyczący rozszerzeń Markdown i DocFX Flavored Markdown (DFM).
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
audience: internal,external
ms.openlocfilehash: e248eafb0247b200313ba198f2545eca947f5627
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805906"
---
# <a name="markdown-reference-for-ops"></a><span data-ttu-id="1cbd4-103">Dokumentacja języka Markdown dla platformy OPS</span><span class="sxs-lookup"><span data-stu-id="1cbd4-103">Markdown Reference for OPS</span></span>

<span data-ttu-id="1cbd4-104">Markdown to lekki język znaczników ze składnią formatowania zwykłego tekstu.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-104">Markdown is a lightweight markup language with plain text formatting syntax.</span></span> <span data-ttu-id="1cbd4-105">Platforma OPS obsługuje standardową składnię CommonMark dla języka Markdown oraz niektóre niestandardowe rozszerzenia języka Markdown zaprojektowane w celu zapewnienia bogatszej zawartości w witrynie docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-105">OPS supports the CommonMark standard for Markdown, plus some custom Markdown extensions designed to provide richer content on docs.microsoft.com.</span></span> <span data-ttu-id="1cbd4-106">Ten artykuł zawiera alfabetyczną dokumentację dotyczącą użycia języka Markdown na platformie OPS na potrzeby witryny docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-106">This article provides an alphabetical reference for using Markdown in OPS for docs.microsoft.com.</span></span>

<span data-ttu-id="1cbd4-107">Aby tworzyć w języku Markdown, możesz użyć dowolnego edytora teksów.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-107">You can use any text editor to author Markdown.</span></span> <span data-ttu-id="1cbd4-108">Jako edytora, który ułatwia wstawianie zarówno standardowej składni języka Markdown, jak i niestandardowych rozszerzeń platformy OPS, zalecamy użycie programu [VS Code](https://code.visualstudio.com/) z zainstalowanym pakietem [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-108">For an editor that facilitates inserting both standard Markdown syntax and custom OPS extensions, we recommend [VS Code](https://code.visualstudio.com/) with the [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) installed.</span></span>

<span data-ttu-id="1cbd4-109">Platforma OPS wprowadziła standardy użycia parsera Markdig dla wszystkich nowych repozytoriów, a starsze repozytoria są migrowane do parsera Markdig.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-109">OPS has standardized on Markdig for all new repos, and older repos are migrating to Markdig.</span></span> <span data-ttu-id="1cbd4-110">Renderowanie języka Markdown w parserze Markdig można przetestować w porównaniu z innymi aparatami w witrynie [https://babelmark.github.io/](https://babelmark.github.io/).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-110">You can test the rendering of Markdown in Markdig vs. other engines at [https://babelmark.github.io/](https://babelmark.github.io/).</span></span>

## <a name="alerts-note-tip-important-caution-warning"></a><span data-ttu-id="1cbd4-111">Alerty (Uwaga, Porada, Ważne, Przestroga, Ostrzeżenie)</span><span class="sxs-lookup"><span data-stu-id="1cbd4-111">Alerts (Note, Tip, Important, Caution, Warning)</span></span>

<span data-ttu-id="1cbd4-112">Alerty i rozszerzenie języka Markdown specyficzne dla platformy OPS służą do tworzenia cytatów blokowych, które są renderowane w witrynie docs.microsoft.com z użyciem kolorów i ikon wskazujących istotną zawartość.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-112">Alerts an OPS-specific Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="1cbd4-113">Obsługiwane są następujące typy alertów:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-113">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="1cbd4-114">Te alerty w witrynie docs.microsoft.com wyglądają następująco:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-114">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="1cbd4-115">Informacje, które użytkownik powinien zauważyć nawet w przypadku szybkiego przeglądania.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-115">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="1cbd4-116">Opcjonalne informacje, które pomogą użytkownikowi odnieść większy sukces.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-116">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cbd4-117">Kluczowe informacje wymagane dla sukcesu użytkownika.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-117">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="1cbd4-118">Potencjalnie negatywne konsekwencje akcji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-118">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="1cbd4-119">Niektóre niebezpieczne konsekwencje akcji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-119">Dangerous certain consequences of an action.</span></span>

## <a name="code-snippets"></a><span data-ttu-id="1cbd4-120">Fragmenty kodu</span><span class="sxs-lookup"><span data-stu-id="1cbd4-120">Code snippets</span></span>

<span data-ttu-id="1cbd4-121">W swoich plikach Markdown możesz osadzić fragmenty kodu:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-121">You can embed code snippets in your Markdown files:</span></span>

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a><span data-ttu-id="1cbd4-122">Nagłówki</span><span class="sxs-lookup"><span data-stu-id="1cbd4-122">Headings</span></span>

<span data-ttu-id="1cbd4-123">Platforma OPS obsługuje sześć poziomów nagłówków języka Markdown:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-123">OPS supports six levels of Markdown headings:</span></span>

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- <span data-ttu-id="1cbd4-124">Między ostatnim znakiem `#` i tekstem nagłówka musi być odstęp.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-124">There must be a space between the last `#` and heading text.</span></span>
- <span data-ttu-id="1cbd4-125">Każdy plik Markdown musi mieć dokładnie jeden nagłówek H1.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-125">Each Markdown file must have one and only one H1.</span></span>
- <span data-ttu-id="1cbd4-126">Nagłówek H1 musi być pierwszym elementem w pliku po bloku metadanych YML.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-126">The H1 must be the first content in the file after the YML metadata block.</span></span>
- <span data-ttu-id="1cbd4-127">Nagłówki H2 automatycznie pojawiają się w prawym menu nawigacyjnym opublikowanego pliku.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-127">H2s automatically appear in the right-hand navigating menu of the published file.</span></span> <span data-ttu-id="1cbd4-128">Nagłówki niższego poziomu nie pojawiają się, więc używaj nagłówków H2 tak, aby pomóc czytelnikom w nawigacji po zawartości.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-128">Lower-level headings do not, so use H2s strategically to help readers navigate your content.</span></span>
- <span data-ttu-id="1cbd4-129">Nagłówki języka HTML, takie jak `<h1>`, nie są zalecane i w niektórych przypadkach mogą powodować ostrzeżenia podczas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-129">HMTL headings, such as `<h1>`, are not recommended and in some cases will cause build warnings.</span></span>
- <span data-ttu-id="1cbd4-130">Do poszczególnych nagłówków w pliku możesz tworzyć linki za pomocą [zakładek](#bookmark-links).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-130">You can link to individual headings in a file via [bookmarks](#bookmark-links).</span></span>

## <a name="html"></a><span data-ttu-id="1cbd4-131">HTML</span><span class="sxs-lookup"><span data-stu-id="1cbd4-131">HTML</span></span>

<span data-ttu-id="1cbd4-132">Chociaż język Markdown obsługuje śródwierszowy kod HTML, nie jest on zalecany przy publikowaniu za pośrednictwem platformy OPS i oprócz ograniczonej listy wartości będzie powodować błędy lub ostrzeżenia podczas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-132">Although Markdown supports inline HTML, HTML is not recommended for publishing via OPS, and except for a limited list of values will cause build errors or warnings.</span></span> <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a><span data-ttu-id="1cbd4-133">Grafika</span><span class="sxs-lookup"><span data-stu-id="1cbd4-133">Images</span></span>

<span data-ttu-id="1cbd4-134">Składnia używana w celu dołączenia obrazu to:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-134">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

<span data-ttu-id="1cbd4-135">Gdzie element `alt text` jest krótkim opisem obrazu, a element `<folder path>` jest ścieżką względną do obrazu.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-135">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="1cbd4-136">Alternatywny tekst jest wymagany na potrzeby czytników zawartości ekranu dla osób niedowidzących.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-136">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="1cbd4-137">Jest to również przydatne w przypadku wystąpienia usterki witryny, kiedy obraz nie może być renderowany.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-137">It is also useful if there is a site bug where the image cannot render.</span></span>

<span data-ttu-id="1cbd4-138">Obrazy powinny być przechowywane w folderze `/media` w zestawie dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-138">Images should be stored in a `/media` folder within your doc set.</span></span> <span data-ttu-id="1cbd4-139">Domyślnie dla obrazów są obsługiwane następujące typy plików:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-139">The following file types are supported by default for images:</span></span>

- <span data-ttu-id="1cbd4-140">jpg</span><span class="sxs-lookup"><span data-stu-id="1cbd4-140">.jpg</span></span>
- <span data-ttu-id="1cbd4-141">png</span><span class="sxs-lookup"><span data-stu-id="1cbd4-141">.png</span></span>

<span data-ttu-id="1cbd4-142">Możesz dodać obsługę innych typów obrazów, dodając je jako zasoby do pliku docfx.json<!--add link to reference when available--> dla zestawu dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-142">You can add support for other image types by adding them as resources to the docfx.json file<!--add link to reference when available--> for your doc set.</span></span>

## <a name="links"></a><span data-ttu-id="1cbd4-143">Linki</span><span class="sxs-lookup"><span data-stu-id="1cbd4-143">Links</span></span>

<span data-ttu-id="1cbd4-144">W większości przypadków platforma OPS używa standardowych linków języka Markdown do innych plików i stron.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-144">In most cases, OPS uses standard Markdown links to other files and pages.</span></span> <span data-ttu-id="1cbd4-145">Typy linków zostały opisane w poniższych podsekcjach.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-145">The types of links are described in subsections below.</span></span>

> [!TIP]
> <span data-ttu-id="1cbd4-146">Pakiet Docs Authoring Pack dla programu VS Code pomaga w poprawnym wstawianiu linków względnych i zakładek bez uciążliwego określania ścieżek.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-146">The Docs Authoring Pack for VS Code can help insert relative links and bookmarks correctly without the tedium of figuring out the paths!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cbd4-147">W linkach do witryn firmy Microsoft nie uwzględniaj kodów ustawień regionalnych, takich jak pl-pl.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-147">Do not include locale codes, such as en-us, in your links to Microsoft sites.</span></span> <span data-ttu-id="1cbd4-148">Zapisywanie na stałe kodów ustawień regionalnych uniemożliwia renderowanie zlokalizowanej zawartości, co jest niekorzystne dla użytkowników w innych lokalizacjach i powoduje znaczne koszty lokalizacyjne.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-148">Hard-coded locale codes prevent localized content from rendering, which is a bad customer experience for users in other locales and incurs significant localization costs.</span></span> <span data-ttu-id="1cbd4-149">Podczas kopiowania adresu URL z przeglądarki kod ustawień regionalnych jest uwzględniony domyślnie, więc musisz usunąć go ręcznie podczas tworzenia własnego linku.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-149">When you copy a URL from a browser, the locale code is included by default, so you need to manually delete in when you create your link.</span></span> <span data-ttu-id="1cbd4-150">Na przykład użyj:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-150">For example, use:</span></span>
>
> `[Microsoft](https://www.microsoft.com)`
>
> <span data-ttu-id="1cbd4-151">Nie:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-151">Not:</span></span>
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a><span data-ttu-id="1cbd4-152">Linki względne do plików w tym samym zestawie dokumentacji</span><span class="sxs-lookup"><span data-stu-id="1cbd4-152">Relative links to files in the same doc set</span></span>

<span data-ttu-id="1cbd4-153">Ścieżka względna jest ścieżką do pliku docelowego względem bieżącego pliku.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-153">A relative path is the path to the target file relative to the current file.</span></span> <span data-ttu-id="1cbd4-154">Na platformie OPS ścieżki względnej można użyć w celu utworzenia linku do innego pliku w obrębie tego samego zestawu dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-154">In OPS, you can use a relative path to link to another file within the same doc set.</span></span> <span data-ttu-id="1cbd4-155">Składnia dla ścieżki względnej wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-155">The syntax for a relative path is as follows:</span></span>

```markdown
[link text](../../folder/filename.md)
```

<span data-ttu-id="1cbd4-156">Gdzie element `../` oznacza jeden poziom wyżej w hierarchii.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-156">Where `../` indicates one level above in the hierarchy.</span></span>

- <span data-ttu-id="1cbd4-157">Ścieżka względna zostanie rozpoznana podczas kompilacji i zostanie usunięte rozszerzenie md.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-157">The relative path will be resolved during the build, including removal of the .md extension.</span></span>
- <span data-ttu-id="1cbd4-158">Elementu „../” możesz użyć w celu utworzenia linku do pliku w folderze nadrzędnym, ale plik musi znajdować się w tym samym zestawie dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-158">You can use "../" to link to a file in the parent folder, but that file has to be in the same doc set.</span></span> <span data-ttu-id="1cbd4-159">Elementu „../” nie możesz użyć w celu utworzenia linku do pliku w folderze innego zestawu dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-159">You cannot use "../" to link to a file in another doc set folder.</span></span>
- <span data-ttu-id="1cbd4-160">Platforma OPS obsługuje również specjalną postać ścieżki względnej, która rozpoczyna się od znaku „~” (np. ~/foo/bar.md).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-160">OPS also supports a special form of relative path that starts with "~" (for example, ~/foo/bar.md).</span></span> <span data-ttu-id="1cbd4-161">Składnia ta określa plik względny w stosunku do głównego folderu zestawu dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-161">This syntax indicates a file relative to the root folder of a doc set.</span></span> <span data-ttu-id="1cbd4-162">Ten rodzaj ścieżki jest również walidowany i rozpoznawany podczas kompilacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-162">This kind of path is also validated and resolved during the build.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cbd4-163">Uwzględnij rozszerzenie pliku w ścieżce względnej.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-163">Include the file extension in the relative path.</span></span> <span data-ttu-id="1cbd4-164">Kompilacja weryfikuje istnienie pliku docelowego określonej ścieżki względnej.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-164">Build validates the existence of the target file of that relative path.</span></span> <span data-ttu-id="1cbd4-165">Jeśli ścieżka względna nie uwzględnia rozszerzenia pliku, najprawdopodobniej kompilacja zgłosi ostrzeżenie dotyczące niedziałającego linku.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-165">If relative path does not include file extension, it is likely build will report a warning of broken link.</span></span> <span data-ttu-id="1cbd4-166">Na przykład użyj:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-166">For example, use:</span></span>
>
> `[link text](../../folder/filename.md)`
>
> <span data-ttu-id="1cbd4-167">Nie:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-167">Not:</span></span>
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a><span data-ttu-id="1cbd4-168">Linki bezwzględne do innych plików na platformie OPS</span><span class="sxs-lookup"><span data-stu-id="1cbd4-168">Absolute links to other files in OPS</span></span>

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

<span data-ttu-id="1cbd4-169">Nie uwzględniaj rozszerzenia pliku (md).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-169">Do not include the file extension (.md).</span></span> <span data-ttu-id="1cbd4-170">Prowadzi ono do pliku przeglądu systemu Linux spoza zestawu dokumentacji „articles” platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-170">This links to the Linux overview file from outside the Azure "articles" doc set.</span></span>

### <a name="links-to-external-sites"></a><span data-ttu-id="1cbd4-171">Linki do zewnętrznych witryn</span><span class="sxs-lookup"><span data-stu-id="1cbd4-171">Links to external sites</span></span>

```markdown
[Microsoft](https://www.microsoft.com)
```

<span data-ttu-id="1cbd4-172">Link oparty na adresie URL do innej strony internetowej (musi zawierać ciąg https://).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-172">URL-based link to another web page (must include https://).</span></span>

### <a name="bookmark-links"></a><span data-ttu-id="1cbd4-173">Linki zakładek</span><span class="sxs-lookup"><span data-stu-id="1cbd4-173">Bookmark links</span></span>

<span data-ttu-id="1cbd4-174">Link zakładki do nagłówka w innym pliku w tym samym repozytorium:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-174">Bookmark link to a heading in another file in the same repo:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<span data-ttu-id="1cbd4-175">Link zakładki do nagłówka w bieżącym pliku:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-175">Bookmark link to a heading in the current file:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<span data-ttu-id="1cbd4-176">Użyj tagu #, po którym następują słowa nagłówka z usuniętą interpunkcją i spacjami zastąpionymi kreskami.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-176">Use a hash tag followed by the words of the heading with punctuation removed and spaces replaced with dashes.</span></span>

### <a name="explicit-anchor-links"></a><span data-ttu-id="1cbd4-177">Jawne linki kotwiczące</span><span class="sxs-lookup"><span data-stu-id="1cbd4-177">Explicit anchor links</span></span>

<span data-ttu-id="1cbd4-178">Jawne linki kotwiczące używające tagu HTML `<a>` **nie są wymagane ani zalecane** poza stronami centrum i stronami docelowymi.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-178">Explicit anchor links using the `<a>` HTML tag are **not required or recommended** except in hub and landing pages.</span></span> <span data-ttu-id="1cbd4-179">Użyj zakładek jak opisano powyżej w ogólnych plikach markdown.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-179">Use bookmarks as described above in general Markdown files.</span></span> <span data-ttu-id="1cbd4-180">Dla stron centrum i stron docelowych użyj następujących kotwic:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-180">For hub and landing pages, use anchors as follows:</span></span>

<span data-ttu-id="1cbd4-181">`## <a id="AnchorText"> </a>Header text` lub `## <a name="AnchorText"> </a>Header text`</span><span class="sxs-lookup"><span data-stu-id="1cbd4-181">`## <a id="AnchorText"> </a>Header text` or `## <a name="AnchorText"> </a>Header text`</span></span>

<span data-ttu-id="1cbd4-182">Aby utworzyć link do jawnych kotwic, użyj następującej składni:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-182">To link to explicit anchors, use the following syntax:</span></span>

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a><span data-ttu-id="1cbd4-183">Linki XREF (odsyłacze)</span><span class="sxs-lookup"><span data-stu-id="1cbd4-183">XREF (cross reference) links</span></span>

<span data-ttu-id="1cbd4-184">Aby utworzyć link do wygenerowanych automatycznie stron dokumentacji interfejsu API w bieżącym zestawie dokumentacji lub innych zestawach dokumentacji, użyj linków XREF z unikatowym identyfikatorem (UID).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-184">To link to auto-generated API references pages in the current doc set or other doc sets, use XREF links with the unique ID (UID).</span></span>

> [!NOTE]
> <span data-ttu-id="1cbd4-185">Aby odwołać się do stron dokumentacji interfejsu API w innych zestawach dokumentacji, należy dodać konfigurację `xrefService` w pliku `docfx.json`.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-185">To reference API reference pages in other docsets, you need to add `xrefService` configuration in `docfx.json` file.</span></span>
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

<span data-ttu-id="1cbd4-186">Identyfikator UID składa się z w pełni kwalifikowanej nazwy klasy i nazwy elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-186">The UID equates to the fully qualified class and member name.</span></span> <span data-ttu-id="1cbd4-187">Po dodaniu elementu \* po identyfikatorze UID link reprezentuje stronę przeciążenia, a nie określony interfejs API.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-187">If you add a \* after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="1cbd4-188">Na przykład użyj ciągu `List<T>.BinarySearch*`, aby utworzyć link do strony metody BinarySearch zamiast do określonego przeciążenia, takiego jak `List<T>.BinarySearch(T, IComparer<T>)`.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-188">For example, use `List<T>.BinarySearch*` to link to the BinarySearch Method page instead of linking to a specific overload such as `List<T>.BinarySearch(T, IComparer<T>)`.</span></span>

<span data-ttu-id="1cbd4-189">Można użyć jednej z następujących składni:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-189">You can use one of the following syntaxes:</span></span>

- <span data-ttu-id="1cbd4-190">Link automatyczny: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="1cbd4-190">Auto-link: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span></span>

  <span data-ttu-id="1cbd4-191">Opcjonalny parametr zapytania `displayProperty` powoduje utworzenie tekstu z w pełni kwalifikowanym linkiem.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-191">The optional `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="1cbd4-192">Domyślnie tekst linku zawiera tylko nazwę składowej lub typu.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-192">By default, link text shows only the member or type name.</span></span>

- <span data-ttu-id="1cbd4-193">Link języka Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="1cbd4-193">Markdown link: `[link text](xref:UID)`</span></span>
  
  <span data-ttu-id="1cbd4-194">Jest używany, aby można było dostosować wyświetlany tekst linku.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-194">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="1cbd4-195">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-195">Examples:</span></span>

- <span data-ttu-id="1cbd4-196">`<xref:System.String>` jest renderowany jako „String”.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-196">`<xref:System.String>` renders as "String".</span></span>
- <span data-ttu-id="1cbd4-197">`<xref:System.String?displayProperty=nameWithType>` jest renderowany jako „System.String”.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-197">`<xref:System.String?displayProperty=nameWithType>` renders as "System.String".</span></span>
- <span data-ttu-id="1cbd4-198">`[String class](xref:System.String)` jest renderowany jako „String class”.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-198">`[String class](xref:System.String)` renders as "String class".</span></span>

<span data-ttu-id="1cbd4-199">Aktualnie nie istnieje łatwy sposób znajdowania identyfikatorów UID.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-199">Right now, there is no easy way to find the UIDs.</span></span> <span data-ttu-id="1cbd4-200"><!-- ? -->Najlepszym sposobem znalezienia identyfikatora UID dla interfejsu API jest wyświetlenie źródła strony interfejsu API, do której chcesz utworzyć link, a następnie znalezienie wartości ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-200"><!-- ? -->The best way to find the UID for an API is to view the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="1cbd4-201">Wartości poszczególnych przeciążeń nie są wyświetlane w źródle.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-201">Individual overload values are not shown in the source.</span></span> <span data-ttu-id="1cbd4-202">Prowadzimy prace nad tym, aby w przyszłości dysponować lepszym systemem.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-202">We're working on having a better system in the future.</span></span>

<span data-ttu-id="1cbd4-203">Gdy identyfikator UID zawiera znaki specjalne \`, \# lub \*, wartość UID musi być zakodowana w języku HTML odpowiednio jako `%60`, `%23` i `%2A`.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-203">When the UID contains the special characters \`, \#, or \*, the UID value needs to be HTML encoded as `%60`, `%23`, and `%2A`, respectively.</span></span> <span data-ttu-id="1cbd4-204">Czasami można zobaczyć zakodowane nawiasy, ale nie są one wymagane.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-204">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="1cbd4-205">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-205">Examples:</span></span>

- <span data-ttu-id="1cbd4-206">System.Threading.Tasks.Task\`1 staje się `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="1cbd4-206">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="1cbd4-207">System.Exception.\#ctor staje się `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="1cbd4-207">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="1cbd4-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) staje się `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="1cbd4-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a><span data-ttu-id="1cbd4-209">Listy (numerowana, punktowana, kontrolna)</span><span class="sxs-lookup"><span data-stu-id="1cbd4-209">Lists (Numbered, Bulleted, Checklist)</span></span>

### <a name="numbered-list"></a><span data-ttu-id="1cbd4-210">Lista numerowana</span><span class="sxs-lookup"><span data-stu-id="1cbd4-210">Numbered list</span></span>

<span data-ttu-id="1cbd4-211">W celu utworzenia listy numerowanej możesz użyć samych jedynek. Po opublikowaniu zostaną one wyrenderowane jako lista sekwencyjna.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-211">To create a numbered list, you can use all 1s, which are rendered as a sequential list when published.</span></span> <span data-ttu-id="1cbd4-212">Aby poprawić czytelność źródła, możesz zwiększać numery pozycji na liście.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-212">For increased source readability, you can increment your lists.</span></span>

<span data-ttu-id="1cbd4-213">Nie używaj liter na listach, w tym na listach zagnieżdżonych.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-213">Do not use letters in lists, including nested lists.</span></span> <span data-ttu-id="1cbd4-214">Nie są one renderowane poprawnie po opublikowaniu za pomocą platformy OPS.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-214">They do not render correctly when published via OPS.</span></span> <span data-ttu-id="1cbd4-215">Listy zagnieżdżone używające numerów po opublikowaniu będą renderowane jako małe litery.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-215">Nested lists using numbers will render as lowercase letters when published.</span></span> <span data-ttu-id="1cbd4-216">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-216">For example:</span></span>

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

<span data-ttu-id="1cbd4-217">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-217">This renders as follows:</span></span>

1. <span data-ttu-id="1cbd4-218">This is</span><span class="sxs-lookup"><span data-stu-id="1cbd4-218">This is</span></span>
1. <span data-ttu-id="1cbd4-219">a parent numbered list</span><span class="sxs-lookup"><span data-stu-id="1cbd4-219">a parent numbered list</span></span>
   1. <span data-ttu-id="1cbd4-220">and this is</span><span class="sxs-lookup"><span data-stu-id="1cbd4-220">and this is</span></span>
   1. <span data-ttu-id="1cbd4-221">a parent numbered list</span><span class="sxs-lookup"><span data-stu-id="1cbd4-221">a nested numbered list</span></span>
1. <span data-ttu-id="1cbd4-222">(fin)</span><span class="sxs-lookup"><span data-stu-id="1cbd4-222">(fin)</span></span>

### <a name="bulleted-list"></a><span data-ttu-id="1cbd4-223">Lista punktowana</span><span class="sxs-lookup"><span data-stu-id="1cbd4-223">Bulleted list</span></span>

<span data-ttu-id="1cbd4-224">Aby utworzyć listę punktowaną, użyj znaku `-`, a następnie spacji na początku każdego wiersza:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-224">To create a bulleted list, use `-` followed by a space at the beginning of each line:</span></span>

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

<span data-ttu-id="1cbd4-225">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-225">This renders as follows:</span></span>

- <span data-ttu-id="1cbd4-226">This is</span><span class="sxs-lookup"><span data-stu-id="1cbd4-226">This is</span></span>
- <span data-ttu-id="1cbd4-227">a parent bulleted list</span><span class="sxs-lookup"><span data-stu-id="1cbd4-227">a parent bulleted list</span></span>
  - <span data-ttu-id="1cbd4-228">and this is</span><span class="sxs-lookup"><span data-stu-id="1cbd4-228">and this is</span></span>
  - <span data-ttu-id="1cbd4-229">a nested bulleted list</span><span class="sxs-lookup"><span data-stu-id="1cbd4-229">a nested bulleted list</span></span>
- <span data-ttu-id="1cbd4-230">All done!</span><span class="sxs-lookup"><span data-stu-id="1cbd4-230">All done!</span></span>

### <a name="checklist"></a><span data-ttu-id="1cbd4-231">Lista kontrolna</span><span class="sxs-lookup"><span data-stu-id="1cbd4-231">Checklist</span></span>

<span data-ttu-id="1cbd4-232">Listy kontrolne są dostępne do użycia w witrynie docs.microsoft.com (wyłącznie) za pośrednictwem niestandardowego rozszerzenia Markdown:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-232">Checklists are available for use on docs.microsoft.com (only) via a custom Markdown extension:</span></span>

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

<span data-ttu-id="1cbd4-233">Ten przykład jest renderowany w witrynie docs.microsoft.com następująco:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-233">This example renders on docs.microsoft.com like this:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="1cbd4-234">List item 1</span><span class="sxs-lookup"><span data-stu-id="1cbd4-234">List item 1</span></span>
> * <span data-ttu-id="1cbd4-235">List item 2</span><span class="sxs-lookup"><span data-stu-id="1cbd4-235">List item 2</span></span>
> * <span data-ttu-id="1cbd4-236">List item 3</span><span class="sxs-lookup"><span data-stu-id="1cbd4-236">List item 3</span></span>

<span data-ttu-id="1cbd4-237">Użyj list kontrolnych na początku lub na końcu artykułu, aby podsumować zawartość „Czego się nauczysz” lub „Co już wiesz”.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-237">Use checklits at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content.</span></span> <span data-ttu-id="1cbd4-238">Nie dodawaj przypadkowych list kontrolnych w swoich artykułach.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-238">Do not add random checklists throughout your articles.</span></span>
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a><span data-ttu-id="1cbd4-239">Akcja Następny krok</span><span class="sxs-lookup"><span data-stu-id="1cbd4-239">Next step action</span></span>

<span data-ttu-id="1cbd4-240">Aby dodać przycisk akcji Następny krok do stron w witrynie docs.microsoft.com (wyłącznie), można użyć rozszerzenia niestandardowego.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-240">You can use a custom extension to add a next step action button to pages on docs.microsoft.com (only).</span></span>

<span data-ttu-id="1cbd4-241">Składnia wygląda następująco:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-241">The syntax is as follows:</span></span>

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

<span data-ttu-id="1cbd4-242">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-242">For example:</span></span>

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

<span data-ttu-id="1cbd4-243">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-243">This renders as follows:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1cbd4-244">Learn about basic style</span><span class="sxs-lookup"><span data-stu-id="1cbd4-244">Learn about basic style</span></span>](style-quick-start.md)

<span data-ttu-id="1cbd4-245">W akcji Następny krok możesz użyć dowolnego obsługiwanego linku, w tym linku języka Markdown do innej strony internetowej.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-245">You can use any supported link in a next step action, including a Markdown link to another web page.</span></span> <span data-ttu-id="1cbd4-246">W większości przypadków link akcji do przechodzenia dalej będzie linkiem względnym do innego pliku w tym samym zestawie dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-246">In most cases, the next action link will be a relative link to another file in the same doc set.</span></span>

## <a name="section-definition"></a><span data-ttu-id="1cbd4-247">Definicja sekcji</span><span class="sxs-lookup"><span data-stu-id="1cbd4-247">Section definition</span></span>

<span data-ttu-id="1cbd4-248"><!-- more info about this would be helpful! --> Może być konieczne zdefiniowanie sekcji.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-248"><!-- more info about this would be helpful! --> You might need to define a section.</span></span> <span data-ttu-id="1cbd4-249">Ta składnia jest używana najczęściej w przypadku tabel kodu.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-249">This syntax is mostly used for code tables.</span></span>
<span data-ttu-id="1cbd4-250">Zobacz poniższy przykład:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-250">See the following example:</span></span>

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

<span data-ttu-id="1cbd4-251">Tekst poprzedzającego znacznika języka Markdown typu blockquote będzie renderowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-251">The preceding blockquote Markdown text will be rendered as:</span></span>
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a><span data-ttu-id="1cbd4-252">Selektory</span><span class="sxs-lookup"><span data-stu-id="1cbd4-252">Selectors</span></span>

<span data-ttu-id="1cbd4-253"><!-- could be more clear! --> Selektora możesz użyć, jeśli chcesz połączyć różne strony w ramach tego samego artykułu.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-253"><!-- could be more clear! --> You can use a selector when you want to connect different pages for the same article.</span></span> <span data-ttu-id="1cbd4-254">Czytelnicy mogą potem przełączać się między tymi stronami.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-254">Readers can then switch between those pages.</span></span>

> [!NOTE]
> <span data-ttu-id="1cbd4-255">To rozszerzenie działa inaczej w przypadku witryn docs.microsoft.com i MSDN.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-255">This extension works differently between docs.microsoft.com and MSDN.</span></span> <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a><span data-ttu-id="1cbd4-256">Pojedynczy selektor</span><span class="sxs-lookup"><span data-stu-id="1cbd4-256">Single selector</span></span>

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

<span data-ttu-id="1cbd4-257">... będzie renderowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-257">... will be rendered like this:</span></span>

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a><span data-ttu-id="1cbd4-266">Selektor wielokrotny</span><span class="sxs-lookup"><span data-stu-id="1cbd4-266">Multi-selector</span></span>

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

<span data-ttu-id="1cbd4-267">... będzie renderowany w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-267">... will be rendered like this:</span></span>

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)

<!-- uncomment and link when Cory's topic is live
## Tabbed content

Tabs are a Markdown extension for docs.microsoft.com that allow us to present different versions of content, such as procedural steps to accomplish the same task on different platforms, in a tabbed format.

Because the syntax and requirements for tabbed content are fairly complex, they are documented separately in Tabbed Content.
-->

## <a name="tables"></a><span data-ttu-id="1cbd4-278">Tabele</span><span class="sxs-lookup"><span data-stu-id="1cbd4-278">Tables</span></span>

<span data-ttu-id="1cbd4-279">Najprostszym sposobem utworzenia tabeli w języku Markdown jest użycie kresek pionowych i wierszy.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-279">The simplest way to create a table in Markdown is to use pipes and lines.</span></span> <span data-ttu-id="1cbd4-280">Aby utworzyć standardową tabelę z nagłówkiem, po pierwszym wierszu wstaw z wiersz w kreskami:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-280">To create a standard table with a header, follow the first line with dashed line:</span></span>

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

<span data-ttu-id="1cbd4-281">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-281">This renders as follows:</span></span>

|<span data-ttu-id="1cbd4-282">This is</span><span class="sxs-lookup"><span data-stu-id="1cbd4-282">This is</span></span>   |<span data-ttu-id="1cbd4-283">a simple</span><span class="sxs-lookup"><span data-stu-id="1cbd4-283">a simple</span></span>   |<span data-ttu-id="1cbd4-284">table header</span><span class="sxs-lookup"><span data-stu-id="1cbd4-284">table header</span></span>|
|----------|-----------|------------|
|<span data-ttu-id="1cbd4-285">table</span><span class="sxs-lookup"><span data-stu-id="1cbd4-285">table</span></span>     |<span data-ttu-id="1cbd4-286">data</span><span class="sxs-lookup"><span data-stu-id="1cbd4-286">data</span></span>       |<span data-ttu-id="1cbd4-287">here</span><span class="sxs-lookup"><span data-stu-id="1cbd4-287">here</span></span>        |
|<span data-ttu-id="1cbd4-288">it doesn't</span><span class="sxs-lookup"><span data-stu-id="1cbd4-288">it doesn't</span></span>|<span data-ttu-id="1cbd4-289">actually</span><span class="sxs-lookup"><span data-stu-id="1cbd4-289">actually</span></span>   |<span data-ttu-id="1cbd4-290">have to line up nicely!</span><span class="sxs-lookup"><span data-stu-id="1cbd4-290">have to line up nicely!</span></span>||

<span data-ttu-id="1cbd4-291">Można również utworzyć tabelę bez nagłówka.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-291">You can also create a table without a header.</span></span> <span data-ttu-id="1cbd4-292">Aby na przykład utworzyć listę z wieloma kolumnami:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-292">For example, to create a multiple-column list:</span></span>

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

<span data-ttu-id="1cbd4-293">Renderowanie zostanie przeprowadzone w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-293">This renders like this:</span></span>

|   |   |
| - | - |
| <span data-ttu-id="1cbd4-294">This</span><span class="sxs-lookup"><span data-stu-id="1cbd4-294">This</span></span> | <span data-ttu-id="1cbd4-295">table</span><span class="sxs-lookup"><span data-stu-id="1cbd4-295">table</span></span> |
| <span data-ttu-id="1cbd4-296">has no</span><span class="sxs-lookup"><span data-stu-id="1cbd4-296">has no</span></span> | <span data-ttu-id="1cbd4-297">header</span><span class="sxs-lookup"><span data-stu-id="1cbd4-297">header</span></span> |

<span data-ttu-id="1cbd4-298">Kolumny można wyrównać za pomocą dwukropków:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-298">You can align the columns by using colons:</span></span>

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

<span data-ttu-id="1cbd4-299">Renderuje się następująco:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-299">Renders as follows:</span></span>

|                  |
|------------------|
|    <span data-ttu-id="1cbd4-300">right aligned:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-300">right aligned:</span></span>|
|<span data-ttu-id="1cbd4-301">:left aligned</span><span class="sxs-lookup"><span data-stu-id="1cbd4-301">:left aligned</span></span>     |
|<span data-ttu-id="1cbd4-302">:centered        :</span><span class="sxs-lookup"><span data-stu-id="1cbd4-302">:centered        :</span></span>|

> [!TIP]
> Rozszerzenie Docs Authoring dla programu VS Code ułatwia dodawanie podstawowych tabeli języka Markdown!
>
> Możesz również użyć [generatora tabeli w trybie online](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a><span data-ttu-id="1cbd4-305">mx-tdBreakAll</span><span class="sxs-lookup"><span data-stu-id="1cbd4-305">mx-tdBreakAll</span></span>

> [!IMPORTANT]
> To działa tylko w witrynie docs.microsoft.com.

<span data-ttu-id="1cbd4-307">Jeśli tworzysz tabelę w języku Markdown, tabela może być rozszerzana w stronę prawego paska nawigacji, co uniemożliwia odczytywanie tabeli.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-307">If you create a table in Markdown, the table might expand to the right navigation and become unreadable.</span></span> <span data-ttu-id="1cbd4-308">Ten problem można rozwiązać, zezwalając funkcji renderowania dokumentów na dzielenie tabeli.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-308">You can solve that by allowing Docs rendering to break the table when needed.</span></span> <span data-ttu-id="1cbd4-309">Wystarczy zawinąć tabelę przy użyciu niestandardowej klasy `[!div class="mx-tdBreakAll"]`.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-309">Just wrap up the table with the custom class `[!div class="mx-tdBreakAll"]`.</span></span>

<span data-ttu-id="1cbd4-310">Poniżej znajduje się przykładowy kod Markdown dla tabeli z trzema wierszami, która zostanie zawinięta przy użyciu elementu `div` z nazwą klasy `mx-tdBreakAll`.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-310">Here is a Markdown sample of a table with three rows that will be wrapped by a `div` with the class name `mx-tdBreakAll`.</span></span>

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

<span data-ttu-id="1cbd4-311">Będzie ona renderowana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-311">It will be rendered like this:</span></span>

> [!div class="mx-tdBreakAll"]
> |<span data-ttu-id="1cbd4-312">Nazwa</span><span class="sxs-lookup"><span data-stu-id="1cbd4-312">Name</span></span>|<span data-ttu-id="1cbd4-313">Składnia</span><span class="sxs-lookup"><span data-stu-id="1cbd4-313">Syntax</span></span>|<span data-ttu-id="1cbd4-314">Obowiązkowe w przypadku instalacji dyskretnej?</span><span class="sxs-lookup"><span data-stu-id="1cbd4-314">Mandatory for silent installation?</span></span>|<span data-ttu-id="1cbd4-315">Opis</span><span class="sxs-lookup"><span data-stu-id="1cbd4-315">Description</span></span>|
> |-------------|----------|---------|---------|
> |<span data-ttu-id="1cbd4-316">Quiet</span><span class="sxs-lookup"><span data-stu-id="1cbd4-316">Quiet</span></span>|<span data-ttu-id="1cbd4-317">/quiet</span><span class="sxs-lookup"><span data-stu-id="1cbd4-317">/quiet</span></span>|<span data-ttu-id="1cbd4-318">Tak</span><span class="sxs-lookup"><span data-stu-id="1cbd4-318">Yes</span></span>|<span data-ttu-id="1cbd4-319">Uruchamia instalatora niewyświetlającego interfejsu użytkownika ani monitów.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-319">Runs the installer, displaying no UI and no prompts.</span></span>|
> |<span data-ttu-id="1cbd4-320">NoRestart</span><span class="sxs-lookup"><span data-stu-id="1cbd4-320">NoRestart</span></span>|<span data-ttu-id="1cbd4-321">/norestart</span><span class="sxs-lookup"><span data-stu-id="1cbd4-321">/norestart</span></span>|<span data-ttu-id="1cbd4-322">Nie</span><span class="sxs-lookup"><span data-stu-id="1cbd4-322">No</span></span>|<span data-ttu-id="1cbd4-323">Pomija wszelkie próby ponownego uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-323">Suppresses any attempts to restart.</span></span> <span data-ttu-id="1cbd4-324">Domyślnie przed ponownym uruchomieniem interfejs użytkownika wyświetli monit.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-324">By default, the UI will prompt before restart.</span></span>|
> |<span data-ttu-id="1cbd4-325">Help</span><span class="sxs-lookup"><span data-stu-id="1cbd4-325">Help</span></span>|<span data-ttu-id="1cbd4-326">/help</span><span class="sxs-lookup"><span data-stu-id="1cbd4-326">/help</span></span>|<span data-ttu-id="1cbd4-327">Nie</span><span class="sxs-lookup"><span data-stu-id="1cbd4-327">No</span></span>|<span data-ttu-id="1cbd4-328">Udostępnia pomoc i skróconą dokumentację.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-328">Provides help and quick reference.</span></span> <span data-ttu-id="1cbd4-329">Wyświetla informacje na temat poprawnego użycia polecenia konfiguracji, w tym listę wszystkich opcji i zachowań.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-329">Displays the correct use of the setup command, including a list of all options and behaviors.</span></span>|

### <a name="mx-tdcol2breakall"></a><span data-ttu-id="1cbd4-330">mx-tdCol2BreakAll</span><span class="sxs-lookup"><span data-stu-id="1cbd4-330">mx-tdCol2BreakAll</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1cbd4-331">To działa tylko w witrynie docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-331">This only works on the docs.microsoft.com site.</span></span>

<span data-ttu-id="1cbd4-332">Od czasu do czasu w drugiej kolumnie tabeli mogą pojawiać się bardzo długie wyrazy.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-332">From time to time, you might have very long words in the second column of a table.</span></span> <span data-ttu-id="1cbd4-333">Aby upewnić się, że są one dobrze rozdzielone, można zastosować klasę `mx-tdCol2BreakAll` za pomocą składni otoki `div`, jak pokazano wcześniej.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-333">To ensure they are broken apart nicely, you can apply the class `mx-tdCol2BreakAll` by using the `div` wrapper syntax as shown earlier.</span></span>

### <a name="html-tables"></a><span data-ttu-id="1cbd4-334">Tabele HTML</span><span class="sxs-lookup"><span data-stu-id="1cbd4-334">HTML Tables</span></span>

<span data-ttu-id="1cbd4-335">Tabele HTML nie są zalecane w przypadku witryny docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-335">HTML tables are not recommended for docs.microsoft.com.</span></span> <span data-ttu-id="1cbd4-336">W źródle nie są czytelne dla ludzi, co jest kluczową regułą języka Markdown.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-336">They are not human readable in the source - which is a key principle of Markdown.</span></span>

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a><span data-ttu-id="1cbd4-337">Wideo</span><span class="sxs-lookup"><span data-stu-id="1cbd4-337">Videos</span></span>

### <a name="embedding-videos-into-a-markdown-page"></a><span data-ttu-id="1cbd4-338">Osadzanie wideo na stronie języka Markdown</span><span class="sxs-lookup"><span data-stu-id="1cbd4-338">Embedding videos into a Markdown page</span></span>

<span data-ttu-id="1cbd4-339">Obecnie platforma OPS obsługuje wideo opublikowane w jednej z trzech lokalizacji:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-339">Currently, OPS can support videos published to one of three locations:</span></span>

- <span data-ttu-id="1cbd4-340">YouTube</span><span class="sxs-lookup"><span data-stu-id="1cbd4-340">YouTube</span></span>
- <span data-ttu-id="1cbd4-341">Channel9</span><span class="sxs-lookup"><span data-stu-id="1cbd4-341">Channel 9</span></span>
- <span data-ttu-id="1cbd4-342">Własny system firmy Microsoft „One Player”</span><span class="sxs-lookup"><span data-stu-id="1cbd4-342">Microsoft's own 'One Player' system</span></span>

<span data-ttu-id="1cbd4-343">Użytkownik może osadzić film wideo przy użyciu poniższej składni. Film będzie renderowany przez platformę OPS.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-343">You can embed a video with the following syntax, and OPS will render it.</span></span>

```markdown
> [!VIDEO <embedded_video_link>]
```

<span data-ttu-id="1cbd4-344">Przykład:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-344">Example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

<span data-ttu-id="1cbd4-345">... będzie renderowany jako:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-345">... will be rendered as:</span></span>

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

<span data-ttu-id="1cbd4-346">I zostanie wyświetlony w następujący sposób na opublikowanych stronach:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-346">And it will be displayed like this on published pages:</span></span>

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> <span data-ttu-id="1cbd4-347">Adres URL wideo CH9 powinien rozpoczynać się od `https` i kończyć na `/player`.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-347">The CH9 video URL should start with `https` and end with `/player`.</span></span> <span data-ttu-id="1cbd4-348">W przeciwnym razie nastąpi osadzenie całej strony, a nie tylko filmu.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-348">Otherwise, it will embed the whole page instead of the video only.</span></span>

### <a name="uploading-new-videos"></a><span data-ttu-id="1cbd4-349">Przekazywanie nowych wideo</span><span class="sxs-lookup"><span data-stu-id="1cbd4-349">Uploading new videos</span></span>

<span data-ttu-id="1cbd4-350">Każde nowe wideo powinno zostać przekazane przy użyciu następującego procesu:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-350">Any new videos should be uploaded using the following process:</span></span>

1. <span data-ttu-id="1cbd4-351">Dołącz do grupy **docs_video_users** w witrynie IDWEB.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-351">Join the **docs_video_users** group on IDWEB.</span></span>
1. <span data-ttu-id="1cbd4-352">Przejdź do strony https://aka.ms/VideoUploadRequest i wypełnij szczegóły dotyczące Twojego wideo.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-352">Go to https://aka.ms/VideoUploadRequest and fill in the details for your video.</span></span> <span data-ttu-id="1cbd4-353">Potrzebne będą następujące dane (pamiętaj, że żaden z tych elementów nie będzie widoczny publicznie):</span><span class="sxs-lookup"><span data-stu-id="1cbd4-353">You will need (note that none of these items will be visible to the public):</span></span>
    1. <span data-ttu-id="1cbd4-354">Tytuł wideo.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-354">A title for your video.</span></span>
    1. <span data-ttu-id="1cbd4-355">Lista produktów/usług, z którymi Twoje wideo jest związane.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-355">A list of products/services that your video is related to.</span></span>
    1. <span data-ttu-id="1cbd4-356">Strona docelowa lub (w przypadku braku strony) zestaw dokumentacji, gdzie Twoje wideo będzie hostowane.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-356">The target page or (if you don’t have the page yet) doc set that your video will be hosted on.</span></span>
    1. <span data-ttu-id="1cbd4-357">Link do pliku MP4 dla Twojego wideo (jeśli nie masz lokalizacji do umieszczenia tego pliku, możesz to zrobić tymczasowo w tym miejscu: `\\scratch2\scratch\apex`).</span><span class="sxs-lookup"><span data-stu-id="1cbd4-357">A link to the MP4 file for your video (if you don’t have a location to put the file, you can put it here temporarily:   `\\scratch2\scratch\apex`).</span></span> <span data-ttu-id="1cbd4-358">Pliki MP4 powinny mieć rozdzielczość 720p lub wyższą.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-358">MP4 files should be 720p or higher.</span></span>
    1. <span data-ttu-id="1cbd4-359">Opis wideo.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-359">A description of the video.</span></span>
1. <span data-ttu-id="1cbd4-360">Prześlij (zapisz) ten element.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-360">Submit (save) that item.</span></span>
1. <span data-ttu-id="1cbd4-361">Wideo zostanie przekazane w ciągu dwóch dni roboczych.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-361">Within two business days, the video will get uploaded.</span></span> <span data-ttu-id="1cbd4-362">Link potrzebny do osadzenia zostanie umieszczony w elemencie roboczym, który zostanie rozwiązany i przypisany *z powrotem do Ciebie*.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-362">The link you need for embedding will be placed into the work item, and it will be resolved *back to you*.</span></span>
1. <span data-ttu-id="1cbd4-363">Po pobraniu linku do wideo zamknij element roboczy.</span><span class="sxs-lookup"><span data-stu-id="1cbd4-363">Once you have grabbed the video link, close the work item.</span></span>
1. <span data-ttu-id="1cbd4-364">Następnie link do wideo może zostać dodany do Twojego wpisu przy użyciu tej składni:</span><span class="sxs-lookup"><span data-stu-id="1cbd4-364">The video link can then be added to your post, using this syntax:</span></span>

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
