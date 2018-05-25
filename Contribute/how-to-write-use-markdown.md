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
ms.openlocfilehash: 041398361aef90c44bdf3a0dad4aaa2d40a38289
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a>Jak używać języka Markdown do tworzenia zawartości witryny Docs

Artykuły w witrynie docs.microsoft.com są pisane w prostym języku znaczników o nazwie [Markdown](https://daringfireball.net/projects/markdown/), który jest łatwy do czytania i do nauczenia się. Z tego względu stał się on szybko branżowym standardem.

Ponieważ zawartość witryny Docs jest przechowywana w serwisie GitHub, może korzystać z nadzbioru znaczników Markdown o nazwie [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), który oferuje dodatkowe funkcje spełniające typowe potrzeby związane z formatowaniem. Ponadto platforma Open Publishing Services (OPS) implementuje parser języka Markdown o nazwie Markdig. Parser Markdig jest w wysokim stopniu zgodny z językiem GitHub Flavored Markdown (GFM), dodając funkcjonalność włączania funkcji specyficznych dla dokumentów.

* Parser Markdig jest szybkim, wydajnym, zgodnym ze składnią CommonMark, rozszerzalnym procesorem języka Markdown dla platformy .NET.
* https://github.com/lunet-io/markdig
* Lepsze wsparcie społeczności
* Lepsza obsługa standardów

## <a name="markdown-basics"></a>Podstawy języka Markdown

### <a name="headings"></a>Nagłówki

Aby utworzyć nagłówek, użyj znaku skrótu (#) w następujący sposób:

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a>Tekst pogrubiony i kursywa

Aby sformatować tekst jako **pogrubiony**, umieść go między podwójnymi gwiazdkami:

```markdown
    This text is **bold**.
```

Aby sformatować tekst jako *kursywę*, umieść go między pojedynczymi gwiazdkami:

```markdown
    This text is *italic*.
```

Aby sformatować tekst jako ***pogrubiony i kursywę***, umieść go między potrójnymi gwiazdkami:

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a>Listy

#### <a name="unordered-list"></a>Listy nieuporządkowane

Aby sformatować listę nieuporządkowaną/punktowaną, można użyć gwiazdek lub myślników. Na przykład poniższy kod w języku Markdown:

```markdown
- List item 1
- List item 2
- List item 3
```

zostanie wyświetlony jako:

- Element listy 1
- Element listy 2
- Element listy 3

Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy. Na przykład poniższy kod w języku Markdown:

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

zostanie wyświetlony jako:

- Element listy 1
  - Element listy A
  - Element listy B
- Element listy 2

#### <a name="ordered-list"></a>Lista uporządkowana

Aby sformatować listę uporządkowaną/zawierającą kroki w kolejności ich wykonywania, należy użyć odpowiednich numerów. Na przykład poniższy kod w języku Markdown:

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

zostanie wyświetlony jako:

1. Pierwsza instrukcja
2. Druga instrukcja
3. Trzecia instrukcja

Aby zagnieździć listę wewnątrz innej listy, należy utworzyć wcięcie podrzędnych elementów listy. Na przykład poniższy kod w języku Markdown:

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

zostanie wyświetlony jako:

1. Pierwsza instrukcja
    1. Instrukcja podrzędna
    2. Instrukcja podrzędna
2. Druga instrukcja

### <a name="tables"></a>tabelami

Tabele nie są częścią podstawowej specyfikacji języka Markdown, ale są obsługiwane przez język GFM. Tabele możesz tworzyć przy użyciu znaków kreski pionowej (|) i łącznika (-). Łączniki tworzą nagłówki poszczególnych kolumn, a kreski pionowe rozdzielają kolumny. Aby tabela była poprawnie renderowana, dodaj przed nią pusty wiersz.

Na przykład poniższy kod w języku Markdown:

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

zostanie wyświetlony jako:

| Zabawa                  | z                 | tabelami          |
| :------------------- | -------------------: |:---------------:|
| kolumna wyrównana do lewej  | kolumna wyrównana do prawej | kolumna wyśrodkowana |
| 100 USD                 | 100 USD                 | 100 USD            |
| 10 USD                  | 10 USD                  | 10 USD             |
| 1 USD                   | 1 USD                   | 1 USD              |

Więcej informacji na temat tworzenia tabel można znaleźć w następujących zasobach:

- [Funkcja zawijania tabel](#table-wrapping) parsera Markdig, która może ułatwić formatowanie szerokich tabel
- Artykuł [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/) (Organizowanie informacji przy użyciu tabel) w serwisie GitHub
- Aplikacja internetowa [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)
- [Markdown Cheatsheet, autor: Adam Pritchard](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables) (Ściągawka dotycząca języka Markdown)
- [Markdown Extra, autor: Michel Fortin](https://michelf.ca/projects/php-markdown/extra/#table)
- [Konwertowanie tabel HTML na znaczniki języka Markdown](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a>Linki

Składnia języka Markdown dla linku śródwierszowego składa się z części `[link text]`, czyli tekstu do uwzględnienia w hiperlinku, oraz następującej po niej części `(file-name.md)`, czyli adresu URL lub nazwy pliku dołączanego przy użyciu linku:

 `[link text](file-name.md)`

Więcej informacji na temat łączenia zawierają następujące zasoby:

- [Przewodnik po składni języka Markdown](https://daringfireball.net/projects/markdown/syntax#link) (szczegóły dotyczące obsługi podstawowego łączenia w języku Markdown).
- Sekcja [Linki](how-to-write-links.md) tego przewodnika (szczegóły dodatkowej składni łączenia oferowanej przez parser Markdig).

### <a name="code-snippets"></a>Fragmenty kodu

Język Markdown obsługuje umieszczanie fragmentów kodu jako śródwierszowych w zdaniu oraz jako oddzielnego, „ogrodzonego” bloku między zdaniami. Szczegóły znajdziesz w następujących zasobach:

- [Natywna obsługa bloków kodu w języku Markdown](https://daringfireball.net/projects/markdown/syntax#precode)
- [Obsługa ogradzania kodu i wyróżniania składni w rozwiązaniu GFM](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Ogrodzone bloki kodu to prosty sposób włączania wyróżniania składni wybranych fragmentów kodu. Ogólny format ogrodzonych bloków kodu to:

    ```alias
    ...
    your code goes in here
    ...
    ```

Alias po trzech początkowych znakach „`” definiuje wyróżnianie składni do użycia. Poniżej przedstawiono listę języków programowania najczęściej używanych w zawartości witryny Docs oraz odpowiadających im etykiet:

Te języki obsługują przyjazne nazwy i w większości obsługują wyróżnianie składni.

|Nazwa|Etykieta języka Markdown|
|-----|-------|
|Konsola .NET|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|azcopy|
|Interfejs wiersza polecenia platformy Azure|azurecli|
|Azure PowerShell|azurepowershell|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|CSHTML|cshtml|
|DAX|dax|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Znaczniki języka Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|PHP|
|PowerApps Formula|powerappsfl|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

#### <a name="example-c"></a>Przykład: C\#

__Markdown__

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

__Renderowanie__

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

#### <a name="example-sql"></a>Przykład: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Renderowanie__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a>Niestandardowe rozszerzenia języka Markdown na platformie OPS

> [!NOTE]
> Platforma Open Publishing Services (OPS) umożliwia implementowanie parsera Markdig dla języka Markdown o wysokim stopniu zgodności z językiem GitHub Flavored Markdown (GFM). Parser Markdig dodaje pewne funkcje za pośrednictwem rozszerzeń języka Markdown. Wybrane artykuły z pełnego podręcznika tworzenia platformy OPS jako takie zostały dołączone do tego przewodnika do celów informacyjnych. (Przykład można znaleźć w częściach „Rozszerzenia parsera Markdig i języka Markdown” oraz „Fragmenty kodu” dostępnych w spisie treści).

W artykułach z witryny Docs rozwiązanie GFM jest używane na potrzeby większości elementów formatowania artykułów, takich jak akapity, linki, listy i nagłówki. W celu skorzystania z bardziej zaawansowanego formatowania można w artykułach użyć funkcji parsera Markdig, takich jak:

- Bloki uwag
- Operacje dołączania
- Selektory
- Osadzone filmy wideo
- Fragmenty/przykłady kodu

Kompletną listę można znaleźć w częściach „Rozszerzenia parsera Markdig i języka Markdown” oraz „Fragmenty kodu” dostępnych w spisie treści.

### <a name="note-blocks"></a>Bloki uwag

Aby zwrócić uwagę czytelnika na określoną zawartość, można wybrać jeden z czterech typów bloków uwag:

- UWAGA
- OSTRZEŻENIE
- PORADA
- WAŻNE

Ogólnie rzecz biorąc, bloków uwag należy używać oszczędnie, ponieważ mogą zaburzać czytelność artykułu. Obsługują one również bloki kodu, obrazy, listy i linki, ale należy starać się, aby były proste i czytelne.

### <a name="includes"></a>Operacje dołączania

Jeśli masz pliki tekstu lub obrazów do wielokrotnego użytku, które chcesz dołączyć do plików artykułu, możesz użyć odwołania do pliku dołączania za pomocą funkcji dołączania plików w parserze Markdig. Ta funkcja nakazuje platformie OPS dołączenie pliku do pliku artykułu podczas kompilacji, co sprawia, że plik staje się częścią publikowanego artykułu. Istnieją trzy typy operacji dołączania, które ułatwiają wielokrotne użycie zawartości:

- Śródwierszowe: wielokrotne użycie typowego fragmentu tekstu jako śródwierszowego w innym zdaniu.
- Blokowe: wielokrotne użycie całego pliku Markdown jako bloku zagnieżdżonego w sekcji artykułu.
- Obraz: jest to standardowa operacja dołączania implementowana w witrynie Docs.

Śródwierszowe i blokowe operacje dołączania dotyczą prostego pliku Markdown (md). Może on zawierać dowolny prawidłowy kod w języku Markdown. Wszystkie dołączane pliki Markdown należy umieścić we [wspólnym podkatalogu `/includes`](git-github-fundamentals.md#includes-subdirectory) w głównym katalogu repozytorium. Podczas publikowania artykułu dołączany plik jest płynnie z nim integrowany.

Poniżej przedstawiono wymagania i uwagi dotyczące operacji dołączania:

- Operacji dołączania należy używać, gdy ten sam tekst ma pojawiać się w wielu artykułach.
- Blokowe operacje dołączania są używane w przypadku znaczących ilości zawartości — akapitu lub dwóch, procedury udostępnianej lub sekcji udostępnianej. Nie należy ich używać dla części mniejszych niż zdanie.
- Operacje dołączania nie będą renderowane w renderowanym widoku Twojego artykułu w usłudze GitHub, ponieważ korzystają z rozszerzeń parsera Markdig. Będą one renderowane tylko po publikacji.
- Upewnij się, że cały tekst w operacji dołączania został napisany w postaci kompletnych zdań lub fraz, które nie zależą od poprzedniego ani następującego tekstu w artykule odwołującym się do dołączenia. Zignorowanie tej wskazówki spowoduje powstanie w artykule ciągu niemożliwego do przetłumaczenia, który zakłóci spójność zlokalizowanego tekstu.
- Operacji dołączania nie należy osadzać w innych dołączeniach. Nie są one obsługiwane.
- Umieść pliki multimedialne w folderze media, który jest specyficzny dla podkatalogu include — na przykład w folderze `<repo>`/includes/media. Katalog główny względem katalogu multimediów nie powinien zawierać obrazów. Jeśli dołączenie nie zawiera obrazów, odpowiadający mu katalog multimediów nie jest wymagany.
- Podobnie jak w przypadku zwykłych artykułów nie należy udostępniać multimediów między dołączanymi plikami. Użyj oddzielnego pliku z unikatową nazwą dla każdego dołączenia i artykułu. Plik multimedialny należy przechowywać w folderze media skojarzonym z dołączeniem.
- Nie należy używać dołączenia jako jedynej zawartości artykułu.  Operacje dołączania mają stanowić uzupełnienie pozostałej zawartości artykułu.

### <a name="selectors"></a>Selektory

Selektorów należy używać w tworzonych artykułach technicznych z wieloma wariantami tego samego artykułu w celu przedstawienia różnic między implementacjami w ramach różnych technologii lub platform. Ma to przeważnie zastosowanie w przypadku mobilnej zawartości platformy dla deweloperów. Obecnie w parserze Markdig istnieją dwa różne typy selektorów: selektor pojedynczy i selektor wielokrotny.

Ponieważ ten sam kod języka Markdown selektora znajduje się w każdym artykule w zaznaczeniu, zalecamy umieszczanie selektora artykułu w dołączeniu. Następnie można się odwołać do tego dołączenia we wszystkich artykułach, które używają tego samego selektora.

### <a name="code-snippets"></a>Fragmenty kodu

Parser Markdig obsługuje zaawansowane dołączanie kodu do artykułu za pośrednictwem rozszerzenia fragmentu kodu. Oferuje ono zaawansowane możliwości renderowania współpracujące z funkcjami GFM, takie jak wybór języka programowania i kolorowanie składni, oraz użyteczne funkcje, takie jak:

- dołączanie scentralizowanych przykładów/fragmentów kodu z repozytorium zewnętrznego;
- interfejs użytkownika z kartami przedstawiającymi wiele wersji przykładów kodu w różnych językach.

## <a name="gotchas-and-troubleshooting"></a>Problemy i ich rozwiązywanie

### <a name="alt-text"></a>Tekst alternatywny

Nie można prawidłowo renderować tekstu alternatywnego, który zawiera znaki podkreślenia. Na przykład zamiast używać tego:

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Omiń podkreślenia w następujący sposób:

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Apostrofy i cudzysłowy

W przypadku kopiowania z programu Word do edytora języka Markdown tekst może zawierać „eleganckie” (zawinięte) apostrofy lub cudzysłowy. Należy je zakodować lub zmienić na podstawowe apostrofy lub znaki cudzysłowu. W przeciwnym razie po opublikowaniu pliku otrzymasz coś takiego: Itâ€™s

Oto sposoby kodowania „eleganckich” wersji tych znaków interpunkcyjnych:

- Lewy cudzysłów (otwierający): `&#8220;`
- Prawy cudzysłów (zamykający): `&#8221;`
- Prawy pojedynczy cudzysłów lub apostrof (zamykający): `&#8217;`
- Lewy pojedynczy cudzysłów (otwierający) (rzadko używany): `&#8216;`

### <a name="angle-brackets"></a>Nawiasy kątowe

Jeśli w tekście (nie kodzie) pliku używasz nawiasów kątowych — na przykład w celu oznaczenia symbolu zastępczego — zakoduj je ręcznie. W przeciwnym razie w języku Markdown nawiasy kątowe zostaną potraktowane jak tag HTML.

Na przykład `<script name>` należy zakodować jako `&lt;script name&gt;`

## <a name="see-also"></a>Zobacz też

### <a name="markdown-resources"></a>Zasoby dotyczące języka Markdown

- [Introduction to Markdown](https://daringfireball.net/projects/markdown/syntax) (Wprowadzenie do języka Markdown)
- [Docs Markdown cheat-sheet (Ściągawka dotycząca języka Markdown w witrynie Docs)](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [GitHub's Markdown Basics](https://help.github.com/articles/markdown-basics/) (Podstawy języka Markdown w serwisie GitHub)
