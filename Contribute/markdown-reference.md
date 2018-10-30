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
# <a name="markdown-reference-for-ops"></a>Dokumentacja języka Markdown dla platformy OPS

Markdown to lekki język znaczników ze składnią formatowania zwykłego tekstu. Platforma OPS obsługuje standardową składnię CommonMark dla języka Markdown oraz niektóre niestandardowe rozszerzenia języka Markdown zaprojektowane w celu zapewnienia bogatszej zawartości w witrynie docs.microsoft.com. Ten artykuł zawiera alfabetyczną dokumentację dotyczącą użycia języka Markdown na platformie OPS na potrzeby witryny docs.microsoft.com.

Aby tworzyć w języku Markdown, możesz użyć dowolnego edytora teksów. Jako edytora, który ułatwia wstawianie zarówno standardowej składni języka Markdown, jak i niestandardowych rozszerzeń platformy OPS, zalecamy użycie programu [VS Code](https://code.visualstudio.com/) z zainstalowanym pakietem [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack).

Platforma OPS wprowadziła standardy użycia parsera Markdig dla wszystkich nowych repozytoriów, a starsze repozytoria są migrowane do parsera Markdig. Renderowanie języka Markdown w parserze Markdig można przetestować w porównaniu z innymi aparatami w witrynie [https://babelmark.github.io/](https://babelmark.github.io/).

## <a name="alerts-note-tip-important-caution-warning"></a>Alerty (Uwaga, Porada, Ważne, Przestroga, Ostrzeżenie)

Alerty i rozszerzenie języka Markdown specyficzne dla platformy OPS służą do tworzenia cytatów blokowych, które są renderowane w witrynie docs.microsoft.com z użyciem kolorów i ikon wskazujących istotną zawartość. Obsługiwane są następujące typy alertów:

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

Te alerty w witrynie docs.microsoft.com wyglądają następująco:

> [!NOTE]
> Informacje, które użytkownik powinien zauważyć nawet w przypadku szybkiego przeglądania.

> [!TIP]
> Opcjonalne informacje, które pomogą użytkownikowi odnieść większy sukces.

> [!IMPORTANT]
> Kluczowe informacje wymagane dla sukcesu użytkownika.

> [!CAUTION]
> Potencjalnie negatywne konsekwencje akcji.

> [!WARNING]
> Niektóre niebezpieczne konsekwencje akcji.

## <a name="code-snippets"></a>Fragmenty kodu

W swoich plikach Markdown możesz osadzić fragmenty kodu:

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a>Nagłówki

Platforma OPS obsługuje sześć poziomów nagłówków języka Markdown:

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- Między ostatnim znakiem `#` i tekstem nagłówka musi być odstęp.
- Każdy plik Markdown musi mieć dokładnie jeden nagłówek H1.
- Nagłówek H1 musi być pierwszym elementem w pliku po bloku metadanych YML.
- Nagłówki H2 automatycznie pojawiają się w prawym menu nawigacyjnym opublikowanego pliku. Nagłówki niższego poziomu nie pojawiają się, więc używaj nagłówków H2 tak, aby pomóc czytelnikom w nawigacji po zawartości.
- Nagłówki języka HTML, takie jak `<h1>`, nie są zalecane i w niektórych przypadkach mogą powodować ostrzeżenia podczas kompilacji.
- Do poszczególnych nagłówków w pliku możesz tworzyć linki za pomocą [zakładek](#bookmark-links).

## <a name="html"></a>HTML

Chociaż język Markdown obsługuje śródwierszowy kod HTML, nie jest on zalecany przy publikowaniu za pośrednictwem platformy OPS i oprócz ograniczonej listy wartości będzie powodować błędy lub ostrzeżenia podczas kompilacji. <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a>Grafika

Składnia używana w celu dołączenia obrazu to:

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

Gdzie element `alt text` jest krótkim opisem obrazu, a element `<folder path>` jest ścieżką względną do obrazu. Alternatywny tekst jest wymagany na potrzeby czytników zawartości ekranu dla osób niedowidzących. Jest to również przydatne w przypadku wystąpienia usterki witryny, kiedy obraz nie może być renderowany.

Obrazy powinny być przechowywane w folderze `/media` w zestawie dokumentacji. Domyślnie dla obrazów są obsługiwane następujące typy plików:

- jpg
- png

Możesz dodać obsługę innych typów obrazów, dodając je jako zasoby do pliku docfx.json<!--add link to reference when available--> dla zestawu dokumentacji.

## <a name="links"></a>Linki

W większości przypadków platforma OPS używa standardowych linków języka Markdown do innych plików i stron. Typy linków zostały opisane w poniższych podsekcjach.

> [!TIP]
> Pakiet Docs Authoring Pack dla programu VS Code pomaga w poprawnym wstawianiu linków względnych i zakładek bez uciążliwego określania ścieżek.

> [!IMPORTANT]
> W linkach do witryn firmy Microsoft nie uwzględniaj kodów ustawień regionalnych, takich jak pl-pl. Zapisywanie na stałe kodów ustawień regionalnych uniemożliwia renderowanie zlokalizowanej zawartości, co jest niekorzystne dla użytkowników w innych lokalizacjach i powoduje znaczne koszty lokalizacyjne. Podczas kopiowania adresu URL z przeglądarki kod ustawień regionalnych jest uwzględniony domyślnie, więc musisz usunąć go ręcznie podczas tworzenia własnego linku. Na przykład użyj:
>
> `[Microsoft](https://www.microsoft.com)`
>
> Nie:
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a>Linki względne do plików w tym samym zestawie dokumentacji

Ścieżka względna jest ścieżką do pliku docelowego względem bieżącego pliku. Na platformie OPS ścieżki względnej można użyć w celu utworzenia linku do innego pliku w obrębie tego samego zestawu dokumentacji. Składnia dla ścieżki względnej wygląda następująco:

```markdown
[link text](../../folder/filename.md)
```

Gdzie element `../` oznacza jeden poziom wyżej w hierarchii.

- Ścieżka względna zostanie rozpoznana podczas kompilacji i zostanie usunięte rozszerzenie md.
- Elementu „../” możesz użyć w celu utworzenia linku do pliku w folderze nadrzędnym, ale plik musi znajdować się w tym samym zestawie dokumentacji. Elementu „../” nie możesz użyć w celu utworzenia linku do pliku w folderze innego zestawu dokumentacji.
- Platforma OPS obsługuje również specjalną postać ścieżki względnej, która rozpoczyna się od znaku „~” (np. ~/foo/bar.md). Składnia ta określa plik względny w stosunku do głównego folderu zestawu dokumentacji. Ten rodzaj ścieżki jest również walidowany i rozpoznawany podczas kompilacji.

> [!IMPORTANT]
> Uwzględnij rozszerzenie pliku w ścieżce względnej. Kompilacja weryfikuje istnienie pliku docelowego określonej ścieżki względnej. Jeśli ścieżka względna nie uwzględnia rozszerzenia pliku, najprawdopodobniej kompilacja zgłosi ostrzeżenie dotyczące niedziałającego linku. Na przykład użyj:
>
> `[link text](../../folder/filename.md)`
>
> Nie:
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a>Linki bezwzględne do innych plików na platformie OPS

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

Nie uwzględniaj rozszerzenia pliku (md). Prowadzi ono do pliku przeglądu systemu Linux spoza zestawu dokumentacji „articles” platformy Azure.

### <a name="links-to-external-sites"></a>Linki do zewnętrznych witryn

```markdown
[Microsoft](https://www.microsoft.com)
```

Link oparty na adresie URL do innej strony internetowej (musi zawierać ciąg https://).

### <a name="bookmark-links"></a>Linki zakładek

Link zakładki do nagłówka w innym pliku w tym samym repozytorium:

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

Link zakładki do nagłówka w bieżącym pliku:

```markdown
[Managed Disks](#managed-disks)
```

Użyj tagu #, po którym następują słowa nagłówka z usuniętą interpunkcją i spacjami zastąpionymi kreskami.

### <a name="explicit-anchor-links"></a>Jawne linki kotwiczące

Jawne linki kotwiczące używające tagu HTML `<a>` **nie są wymagane ani zalecane** poza stronami centrum i stronami docelowymi. Użyj zakładek jak opisano powyżej w ogólnych plikach markdown. Dla stron centrum i stron docelowych użyj następujących kotwic:

`## <a id="AnchorText"> </a>Header text` lub `## <a name="AnchorText"> </a>Header text`

Aby utworzyć link do jawnych kotwic, użyj następującej składni:

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a>Linki XREF (odsyłacze)

Aby utworzyć link do wygenerowanych automatycznie stron dokumentacji interfejsu API w bieżącym zestawie dokumentacji lub innych zestawach dokumentacji, użyj linków XREF z unikatowym identyfikatorem (UID).

> [!NOTE]
> Aby odwołać się do stron dokumentacji interfejsu API w innych zestawach dokumentacji, należy dodać konfigurację `xrefService` w pliku `docfx.json`.
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

Identyfikator UID składa się z w pełni kwalifikowanej nazwy klasy i nazwy elementu członkowskiego. Po dodaniu elementu * po identyfikatorze UID link reprezentuje stronę przeciążenia, a nie określony interfejs API. Na przykład użyj ciągu `List<T>.BinarySearch*`, aby utworzyć link do strony metody BinarySearch zamiast do określonego przeciążenia, takiego jak `List<T>.BinarySearch(T, IComparer<T>)`.

Można użyć jednej z następujących składni:

- Link automatyczny: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`

  Opcjonalny parametr zapytania `displayProperty` powoduje utworzenie tekstu z w pełni kwalifikowanym linkiem. Domyślnie tekst linku zawiera tylko nazwę składowej lub typu.

- Link języka Markdown: `[link text](xref:UID)`
  
  Jest używany, aby można było dostosować wyświetlany tekst linku.

Przykłady:

- `<xref:System.String>` jest renderowany jako „String”.
- `<xref:System.String?displayProperty=nameWithType>` jest renderowany jako „System.String”.
- `[String class](xref:System.String)` jest renderowany jako „String class”.

Aktualnie nie istnieje łatwy sposób znajdowania identyfikatorów UID. <!-- ? -->Najlepszym sposobem znalezienia identyfikatora UID dla interfejsu API jest wyświetlenie źródła strony interfejsu API, do której chcesz utworzyć link, a następnie znalezienie wartości ms.assetid. Wartości poszczególnych przeciążeń nie są wyświetlane w źródle. Prowadzimy prace nad tym, aby w przyszłości dysponować lepszym systemem.

Gdy identyfikator UID zawiera znaki specjalne \`, \# lub \*, wartość UID musi być zakodowana w języku HTML odpowiednio jako `%60`, `%23` i `%2A`. Czasami można zobaczyć zakodowane nawiasy, ale nie są one wymagane.

Przykłady:

- System.Threading.Tasks.Task\`1 staje się `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor staje się `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) staje się `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a>Listy (numerowana, punktowana, kontrolna)

### <a name="numbered-list"></a>Lista numerowana

W celu utworzenia listy numerowanej możesz użyć samych jedynek. Po opublikowaniu zostaną one wyrenderowane jako lista sekwencyjna. Aby poprawić czytelność źródła, możesz zwiększać numery pozycji na liście.

Nie używaj liter na listach, w tym na listach zagnieżdżonych. Nie są one renderowane poprawnie po opublikowaniu za pomocą platformy OPS. Listy zagnieżdżone używające numerów po opublikowaniu będą renderowane jako małe litery. Na przykład:

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

Renderowanie zostanie przeprowadzone w następujący sposób:

1. This is
1. a parent numbered list
   1. and this is
   1. a parent numbered list
1. (fin)

### <a name="bulleted-list"></a>Lista punktowana

Aby utworzyć listę punktowaną, użyj znaku `-`, a następnie spacji na początku każdego wiersza:

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

Renderowanie zostanie przeprowadzone w następujący sposób:

- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!

### <a name="checklist"></a>Lista kontrolna

Listy kontrolne są dostępne do użycia w witrynie docs.microsoft.com (wyłącznie) za pośrednictwem niestandardowego rozszerzenia Markdown:

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

Ten przykład jest renderowany w witrynie docs.microsoft.com następująco:

> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3

Użyj list kontrolnych na początku lub na końcu artykułu, aby podsumować zawartość „Czego się nauczysz” lub „Co już wiesz”. Nie dodawaj przypadkowych list kontrolnych w swoich artykułach.
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a>Akcja Następny krok

Aby dodać przycisk akcji Następny krok do stron w witrynie docs.microsoft.com (wyłącznie), można użyć rozszerzenia niestandardowego.

Składnia wygląda następująco:

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

Na przykład:

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

Renderowanie zostanie przeprowadzone w następujący sposób:

> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)

W akcji Następny krok możesz użyć dowolnego obsługiwanego linku, w tym linku języka Markdown do innej strony internetowej. W większości przypadków link akcji do przechodzenia dalej będzie linkiem względnym do innego pliku w tym samym zestawie dokumentacji.

## <a name="section-definition"></a>Definicja sekcji

<!-- more info about this would be helpful! --> Może być konieczne zdefiniowanie sekcji. Ta składnia jest używana najczęściej w przypadku tabel kodu.
Zobacz poniższy przykład:

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

Tekst poprzedzającego znacznika języka Markdown typu blockquote będzie renderowany w następujący sposób:
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a>Selektory

<!-- could be more clear! --> Selektora możesz użyć, jeśli chcesz połączyć różne strony w ramach tego samego artykułu. Czytelnicy mogą potem przełączać się między tymi stronami.

> [!NOTE]
> To rozszerzenie działa inaczej w przypadku witryn docs.microsoft.com i MSDN. <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a>Pojedynczy selektor

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

... będzie renderowany w następujący sposób:

> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a>Selektor wielokrotny

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

... będzie renderowany w następujący sposób:

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

## <a name="tables"></a>Tabele

Najprostszym sposobem utworzenia tabeli w języku Markdown jest użycie kresek pionowych i wierszy. Aby utworzyć standardową tabelę z nagłówkiem, po pierwszym wierszu wstaw z wiersz w kreskami:

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

Renderowanie zostanie przeprowadzone w następujący sposób:

|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!||

Można również utworzyć tabelę bez nagłówka. Aby na przykład utworzyć listę z wieloma kolumnami:

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

Renderowanie zostanie przeprowadzone w następujący sposób:

|   |   |
| - | - |
| This | table |
| has no | header |

Kolumny można wyrównać za pomocą dwukropków:

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

Renderuje się następująco:

|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|

> [!TIP]
> Rozszerzenie Docs Authoring dla programu VS Code ułatwia dodawanie podstawowych tabeli języka Markdown!
>
> Możesz również użyć [generatora tabeli w trybie online](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a>mx-tdBreakAll

> [!IMPORTANT]
> To działa tylko w witrynie docs.microsoft.com.

Jeśli tworzysz tabelę w języku Markdown, tabela może być rozszerzana w stronę prawego paska nawigacji, co uniemożliwia odczytywanie tabeli. Ten problem można rozwiązać, zezwalając funkcji renderowania dokumentów na dzielenie tabeli. Wystarczy zawinąć tabelę przy użyciu niestandardowej klasy `[!div class="mx-tdBreakAll"]`.

Poniżej znajduje się przykładowy kod Markdown dla tabeli z trzema wierszami, która zostanie zawinięta przy użyciu elementu `div` z nazwą klasy `mx-tdBreakAll`.

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

Będzie ona renderowana w następujący sposób:

> [!div class="mx-tdBreakAll"]
> |Nazwa|Składnia|Obowiązkowe w przypadku instalacji dyskretnej?|Opis|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Tak|Uruchamia instalatora niewyświetlającego interfejsu użytkownika ani monitów.|
> |NoRestart|/norestart|Nie|Pomija wszelkie próby ponownego uruchomienia. Domyślnie przed ponownym uruchomieniem interfejs użytkownika wyświetli monit.|
> |Help|/help|Nie|Udostępnia pomoc i skróconą dokumentację. Wyświetla informacje na temat poprawnego użycia polecenia konfiguracji, w tym listę wszystkich opcji i zachowań.|

### <a name="mx-tdcol2breakall"></a>mx-tdCol2BreakAll

> [!IMPORTANT]
> To działa tylko w witrynie docs.microsoft.com.

Od czasu do czasu w drugiej kolumnie tabeli mogą pojawiać się bardzo długie wyrazy. Aby upewnić się, że są one dobrze rozdzielone, można zastosować klasę `mx-tdCol2BreakAll` za pomocą składni otoki `div`, jak pokazano wcześniej.

### <a name="html-tables"></a>Tabele HTML

Tabele HTML nie są zalecane w przypadku witryny docs.microsoft.com. W źródle nie są czytelne dla ludzi, co jest kluczową regułą języka Markdown.

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a>Wideo

### <a name="embedding-videos-into-a-markdown-page"></a>Osadzanie wideo na stronie języka Markdown

Obecnie platforma OPS obsługuje wideo opublikowane w jednej z trzech lokalizacji:

- YouTube
- Channel9
- Własny system firmy Microsoft „One Player”

Użytkownik może osadzić film wideo przy użyciu poniższej składni. Film będzie renderowany przez platformę OPS.

```markdown
> [!VIDEO <embedded_video_link>]
```

Przykład:

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

... będzie renderowany jako:

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

I zostanie wyświetlony w następujący sposób na opublikowanych stronach:

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> Adres URL wideo CH9 powinien rozpoczynać się od `https` i kończyć na `/player`. W przeciwnym razie nastąpi osadzenie całej strony, a nie tylko filmu.

### <a name="uploading-new-videos"></a>Przekazywanie nowych wideo

Każde nowe wideo powinno zostać przekazane przy użyciu następującego procesu:

1. Dołącz do grupy **docs_video_users** w witrynie IDWEB.
1. Przejdź do strony https://aka.ms/VideoUploadRequest i wypełnij szczegóły dotyczące Twojego wideo. Potrzebne będą następujące dane (pamiętaj, że żaden z tych elementów nie będzie widoczny publicznie):
    1. Tytuł wideo.
    1. Lista produktów/usług, z którymi Twoje wideo jest związane.
    1. Strona docelowa lub (w przypadku braku strony) zestaw dokumentacji, gdzie Twoje wideo będzie hostowane.
    1. Link do pliku MP4 dla Twojego wideo (jeśli nie masz lokalizacji do umieszczenia tego pliku, możesz to zrobić tymczasowo w tym miejscu: `\\scratch2\scratch\apex`). Pliki MP4 powinny mieć rozdzielczość 720p lub wyższą.
    1. Opis wideo.
1. Prześlij (zapisz) ten element.
1. Wideo zostanie przekazane w ciągu dwóch dni roboczych. Link potrzebny do osadzenia zostanie umieszczony w elemencie roboczym, który zostanie rozwiązany i przypisany *z powrotem do Ciebie*.
1. Po pobraniu linku do wideo zamknij element roboczy.
1. Następnie link do wideo może zostać dodany do Twojego wpisu przy użyciu tej składni:

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
