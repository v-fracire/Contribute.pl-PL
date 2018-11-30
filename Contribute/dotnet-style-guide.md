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
# <a name="metadata-and-markdown-template-for-net-docs"></a>Szablon metadanych i szablon języka Markdown dla dokumentów platformy .NET

Ten szablon z repozytorium dotnet/docs zawiera przykładową składnię języka Markdown oraz wskazówki dotyczące ustawiania metadanych.

Tworząc plik Markdown, skopiuj załączony szablon do nowego pliku, wypełnij metadane zgodnie z poniższym opisem i ustaw nagłówek H1 na tytuł artykułu.

## <a name="metadata"></a>Metadane

Poniższy przykład zawiera wymagany blok metadanych:

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- Miedzy dwukropkiem (:) a wartością elementu metadanych **musi** znajdować się spacja.
- Obecność dwukropków w wartości (na przykład w tytule) zakłóca działanie analizatora metadanych. W takim przypadku należy ująć tytuł w podwójny cudzysłów (na przykład `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: ta wartość pojawia się w wynikach wyszukiwania. Tytuł nie powinien być taki sam jak tytuł w nagłówku H1. Ponadto może on zawierać maksymalnie 60 znaków.
- **description**: podsumowanie zawartości artykułu. Ta wartość zwykle pojawia się na stronie z wynikami wyszukiwania, ale nie jest używana do klasyfikacji wyszukiwania. Liczba znaków (łącznie ze spacjami) powinna mieścić się w przedziale od 115 do 145.
- **author**: pole autora powinno zawierać **nazwę użytkownika w usłudze GitHub**.
- **ms.date**: data ostatniej ważnej aktualizacji. Tę wartość należy aktualizować w przypadku artykułów, które zostały zmodyfikowane podczas przeglądania. Drobniejsze poprawki, na przykład literówki, nie wymagają aktualizacji.

Do poszczególnych artykułów są dołączone inne metadane, ale większość wartości metadanych zwykle stosuje się na poziomie folderu za pośrednictwem pliku **docfx.json**.

## <a name="basic-markdown-gfm-and-special-characters"></a>Podstawowa składnia Markdown, elementy GFM i znaki specjalne

Podstawowe informacje o językach Markdown i GitHub Flavored Markdown (GFM) oraz rozszerzeniach specyficznych dla platformy OPS można znaleźć w ogólnym artykule dotyczącym [języka Markdown](how-to-write-use-markdown.md) oraz w [dokumentacji języka Markdown](markdown-reference.md).

Formatowanie w języku Markdown wymaga użycia znaków specjalnych, takich jak \*, \` i \#. Jeśli chcesz dodać do zawartości jeden z tych znaków, musisz wykonać jedną z tych czynności:

- Zastosuj znak ucieczki — umieść ukośnik odwrotny przed znakiem specjalnym (na przykład dodaj ciąg `\*`, aby uzyskać znak \*).
- Użyj [kodu encji HTML](http://www.ascii.cl/htmlcodes.htm) dla danego znaku (na przykład dodaj ciąg `&#42;`, aby uzyskać znak &#42;).

## <a name="file-names"></a>Nazwy plików

W przypadku nazw plików obowiązują następujące reguły:

* Można używać tylko małych liter, cyfr i łączników.
* Bez spacji i znaków interpunkcyjnych. Wyrazy i liczby w nazwie pliku powinny być oddzielane łącznikami.
* Należy używać czasowników oznaczających określoną akcję, np. „develop”, „buy”, „build”, „troubleshoot”. Bez wyrazów zakończonych na „-ing”.
* Bez krótkich wyrazów, takich jak „a”, „and”, „the”, „in”, „or” itp.
* Nazwa musi być podana w języku znaczników Markdown i mieć rozszerzenie pliku MD.
* Nazwy plików powinny być względnie krótkie. Stanowią one część adresów URL artykułów.

## <a name="headings"></a>Nagłówki

Wielkość liter powinna być taka jak w zdaniu. Pierwszy wyraz nagłówka musi w każdym przypadku zaczynać się od wielkiej litery.

## <a name="text-styling"></a>Styl tekstu

*Kursywa* Należy ją stosować w przypadku plików, folderów, ścieżek (długie ciągi należy rozdzielić na dodatkowe wiersze) i nowych terminów.

**Pogrubienie** Należy je stosować w przypadku elementów interfejsu użytkownika.

`Code` Ten element należy stosować w przypadku kodu wbudowanego, słów kluczowych języka, nazw pakietów NuGet, poleceń używanych w wierszu polecenia, nazw tabeli i kolumn w bazie danych oraz adresów URL, które nie są przeznaczone do klikania.

## <a name="links"></a>Linki

Informacje dotyczące kotwic, linków wewnętrznych, linków prowadzących do innych dokumentów, klauzuli dołączeń w kodzie oraz linków zewnętrznych można znaleźć w ogólnym artykule [Links](how-to-write-links.md) (Linki).

Zespół, który zajmuje się dokumentacją platformy .NET stosuje następujące konwencje:

- W większości przypadków używamy linków względnych. Unikamy używania elementu `~/`, ponieważ linki względne są rozpoznawane w źródle w usłudze GitHub. Jednak w przypadku linków do plików znajdujących się w repozytorium zależnym ścieżka jest podawana za pomocą znaku `~/`. Pliki z repozytorium zależnego znajdują się w innej lokalizacji w usłudze GitHub, dlatego linki względne nie zostaną poprawnie rozpoznane, niezależnie od tego, jak zostały napisane.
- Dodanie specyfikacji języków C# i Visual Basic do dokumentacji platformy .NET odbywa się przez dołączenie źródła z repozytoriów języka. Źródła elementów markdown są zarządzane w repozytoriach [csharplang](https://github.com/dotnet/csharplang) i [vblang](https://github.com/dotnet/vblang).

Linki do specyfikacji muszą prowadzić do katalogów źródłowych, które zawierają te specyfikacje. W przypadku języka C# jest to **~/_csharplang/spec**, a w przypadku języka VB jest to **~/_vblang/spec**, jak w poniższym przykładzie:

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a>Linki do interfejsów API

System kompilacji jest wyposażony w rozszerzenia, które umożliwiają tworzenie połączeń z interfejsami API platformy .NET bez używania linków zewnętrznych. Można użyć jednej z następujących składni:

1. Link automatyczny: `<xref:UID>` lub `<xref:UID?displayProperty=nameWithType>`

   Parametr zapytania `displayProperty` prowadzi do utworzenia tekstu z w pełni kwalifikowanym linkiem. Domyślnie tekst linku zawiera tylko nazwę elementu członkowskiego lub typu.

2. Link języka Markdown: `[link text](xref:UID)`

   Jest używany, aby można było dostosować wyświetlany tekst linku.

Przykłady:

- `<xref:System.String>` jest renderowany jako [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` jest renderowany jako [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` jest renderowany jako [klasa String](https://docs.microsoft.com/dotnet/api/system.string)

Aby uzyskać więcej informacji na temat używania tej notacji, zobacz artykuł [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference) (Używanie odsyłacza).

Niektóre identyfikatory UID zawierają znaki specjalne \`, \# lub \*. W takich przypadkach wartość UID musi być zakodowana w języku HTML odpowiednio jako `%60`, `%23` i `%2A`. Czasami można zobaczyć zakodowane nawiasy, ale nie są one wymagane.

Przykłady:

- System.Threading.Tasks.Task\`1 staje się `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor staje się `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) staje się `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

Na stronie `https://xref.docs.microsoft.com/autocomplete` można znaleźć identyfikatory UID typów, listę przeciążeń składowych lub konkretną przeciążoną składową. Ciąg zapytania `?text=*\<type-member-name>*` identyfikuje typ lub składową, której identyfikatory UID chcesz wyświetlić. Na przykład element `https://xref.docs.microsoft.com/autocomplete?text=string.format` pobiera przeciążenia metody [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format). Narzędzie szuka udostępnionego parametru zapytania `text` w każdej części identyfikatora UID. Na przykład można wyszukiwać nazwę składowej (ToString), część nazwy składowej (ToStri), typ i nazwę składowej (Double.ToString) itp.

Po dodaniu elementu \* (lub `%2A`) po identyfikatorze UID link reprezentuje stronę przeciążenia, a nie określony interfejs API. Możesz z tego skorzystać na przykład, gdy chcesz połączyć stronę [List\<T>.BinarySearch](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) w sposób ogólny, zamiast określonego przeciążenia, takiego jak [List\<T >.BinarySearch(T, IComparer\<T >)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_). Możesz też użyć elementu \*, aby utworzyć link do strony nieprzeciążonej składowej. Dzięki temu nie musisz dołączać listy parametrów w identyfikatorze UID.

Aby utworzyć link do określonego przeciążenia metody, musisz dołączyć w pełni kwalifikowane nazwy typów wszystkich parametrów metody. Na przykład element \<xref:System.DateTime.ToString> tworzy link do bezparametrowej metody [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString), a element \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> tworzy link do metody [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).

Aby utworzyć link do typu ogólnego, takiego jak [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), użyj znaku \` (`%60`), po którym podaj liczbę parametrów typu ogólnego. Na przykład element `<xref:System.Nullable%601>` tworzy link do typu [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), a element `<xref:System.Func%602>` tworzy link do delegata [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

## <a name="code"></a>Kod

Najlepsza metoda dodania kodu polega na dodaniu fragmentów z działającego przykładu. Utwórz własny przykład, wykonując instrukcje podane w artykule dotyczącym [współtworzenia platformy .NET](dotnet-contribute-process.md#contributing-to-samples). Podstawowe reguły dołączania kodu można znaleźć w ogólnych wskazówkach dotyczących [kodu](how-to-write-use-markdown.md#code-includes).

Kod możesz dołączyć za pomocą następującej składni:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*opcjonalne*, ale *zalecane*)
  * Język fragmentu kodu, którego dotyczy odwołanie. Listę obsługiwanych wartości można znaleźć w części [Obsługiwane języki](#supported-languages).

* `<name>` (*opcjonalnie*)
  * Nazwa fragmentu kodu. Nie ma żadnego wpływu na wyjściowy kod HTML, ale dzięki niej można zwiększyć czytelność źródła języka Markdown.

* `<pathToFile>` (*obowiązkowa*)
  * Ścieżka względna w systemie plików wskazująca plik fragmentu kodu, do którego ma zostać utworzone odwołanie. Może to okazać się skomplikowane ze względu na różne repozytoria, które należą do zestawu dokumentacji platformy .NET. Przykłady z platformą .NET znajdują się w repozytorium dotnet/samples. Wszystkie ścieżki do fragmentów kodu zaczynają się od ciągu `~/samples`. Pozostała część określa ścieżkę do źródła od katalogu głównego repozytorium.

* `<queryoption>` (*opcjonalnie*)
  * Używane w celu określenia sposobu pobierania kodu z pliku:
    * `#`:  `#{tagname}` (nazwa tagu) *lub* `#L{startlinenumber}-L{endlinenumber}` (zakres wierszy).
    Odradzamy używanie numerów wierszy ze względu na ich wrażliwość. Preferowana metoda odwoływania się do fragmentów kodu polega na używaniu nazw tagów. Nazwy te powinny być opisowe. Wiele fragmentów kodu zostało zmigrowanych ze starszej platformy, a przykładowe nazwy tagów to `Snippet1`, `Snippet2` itd. Takie podejście znacznie utrudnia utrzymanie kodu.
    * `range`: `?range=1,3-5` Zakres wierszy. Ten przykład obejmuje wiersze, 1, 3, 4 i 5.

Zalecamy korzystanie z nazw tagów, gdy tylko jest to możliwe. Nazwa tagu ma format `Snippettagname` i odpowiada nazwie regionu lub komentarzowi zawartemu w kodzie źródłowym. W poniższym przykładzie pokazano, jak odwołać się do nazwy tagu `BasicThrow`:

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

Ścieżka względna do źródła w repozytorium **dotnet/samples** występuje po ścieżce `~/samples`.

[Ten plik źródłowy](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) pozwala zapoznać się ze strukturą tagów fragmentów kodu. Aby uzyskać szczegółowe informacje na temat reprezentacji nazwy tagu plikach źródłowych fragmentu kodu według języka, zobacz [wytyczne rozwiązania DocFX](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

Poniższy przykład przedstawia dołączenie kodu we wszystkich trzech językach platformy .NET:

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

Dołączenie fragmentów kodu z pełnych programów gwarantuje, że cały kod jest przetwarzany w systemie ciągłej integracji (CI). Jeśli jednak chcesz zademonstrować błędy kompilacji lub błędy w czasie wykonywania, możesz użyć bloków kodu wbudowanego.

## <a name="images"></a>Grafika

### <a name="static-image-or-animated-gif"></a>Obraz statyczny lub animowany obraz GIF

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a>Połączony obraz

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a>Wideo

Aktualnie możesz osadzać filmy wideo z witryn Channel 9 i YouTube, korzystając z następującej składni:

### <a name="channel-9"></a>Channel9

```markdown
> [!VIDEO <channel9_video_link>]
```

Aby pobrać poprawny adres URL filmu wideo, wybierz kartę **Osadzanie** widoczną pod klatką wideo i skopiuj adres URL z elementu `<iframe>`. Na przykład:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Aby pobrać poprawny adres URL filmu wideo, kliknij prawym przyciskiem myszy film wideo, wybierz polecenie **Skopiuj kod osadzania** i skopiuj adres URL z elementu `<iframe>`.

```markdown
> [!VIDEO <youtube_video_link>]
```

Na przykład:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>Rozszerzenia docs.microsoft

Witryna docs.microsoft udostępnia kilka dodatkowych rozszerzeń języka GitHub Flavored Markdown.

### <a name="checked-lists"></a>Listy ze znacznikami wyboru

W przypadku list dostępny jest styl niestandardowy. Można renderować listy z zielonymi znacznikami wyboru.

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

Renderowanie zostanie przeprowadzone w następujący sposób:

> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application

Przykładowe listy ze znacznikami wyboru można znaleźć w [dokumentacji platformy .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Przyciski

Linki do przycisków:

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

Renderowanie zostanie przeprowadzone w następujący sposób:

> [!div class="button"]
[button links](dotnet-contribute.md)

Przykładowe przyciski można znaleźć w [dokumentacji programu Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="step-by-steps"></a>Przewodniki krok po kroku

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

Przykładowe przewodniki krok po kroku można znaleźć w [przewodniku po języku C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
