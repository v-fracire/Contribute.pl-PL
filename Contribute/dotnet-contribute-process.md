---
title: Proces współtworzenia dla repozytoriów dokumentów platformy .NET
description: Ten artykuł zawiera krótkie wprowadzenie do współtworzenia repozytoriów dokumentów platformy .NET. Poznasz używane repozytoria, procesy organizacji zawartości oraz zasady zarządzania przykładami kodu i innymi zasobami.
ms.date: 11/07/2018
ms.openlocfilehash: b83a3080f1abd4df8caaa9d10859760006216e86
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609767"
---
# <a name="process-for-contributing-to-net-docs"></a>Proces współtworzenia dokumentów platformy .NET

Doceniamy wkład społeczności w dokumenty. Poniższa lista przedstawia pewne wskazówki, o których należy pamiętać podczas współtworzenia dokumentacji platformy .NET:

- **NIE ZASKAKUJ NAS** dużymi żądaniami ściągnięcia. Zamiast tego zgłoś problem i rozpocznij dyskusję, abyśmy uzgodnili kierunek zanim zainwestujesz dużo czasu.
- **PRZESTRZEGAJ** tych instrukcji oraz wytycznych dotyczących [stron czasowników i tonu](dotnet-voice-tone.md).
- **UŻYWAJ** pliku [szablonu](dotnet-style-guide.md) jako punktu początkowego w swojej pracy.
- **UTWÓRZ** oddzielną gałąź swojego rozwidlenia zanim zaczniesz pracę przy artykułach.
- **POSTĘPUJ** zgodnie z [przepływem pracy usługi GitHub Flow](https://guides.github.com/introduction/flow/).
- **PISZ** bloga i tweety (lub coś innego) o swoim wkładzie, i rób to często!

Stosowanie tych wytycznych zapewni Ci i nam lepszą płaszczyznę współpracy.

## <a name="make-a-contribution-to-net-docs"></a>Współtworzenie dokumentów platformy .NET

**Krok 1.** Pomiń ten krok w przypadku małych zmian. Jeśli interesuje Cię pisanie nowej zawartości lub gruntowna korekta istniejącej zawartości, otwórz [problem](https://github.com/dotnet/docs/issues), opisując, co chcesz zrobić.

Zawartość w folderze **docs** jest podzielona na sekcje, które zostały odzwierciedlone w spisie treści. Określ, gdzie w spisie treści będzie się znajdował temat. Uzyskaj opinie na temat swojej propozycji.

-lub-

Możesz też wybierać spośród istniejących problemów, dla których współtworzenie w ramach społeczności jest mile widziane. [Projekty dla współautorów społeczności platformy .NET](https://github.com/dotnet/docs/projects/35) zawierają wiele problemów dostępnych dla współautorów należących do społeczności. W zależności od zainteresowań i poziomu zaangażowania możesz wybierać spośród problemów w następujących kategoriach:

- **Konserwacja**. Ta kategoria obejmuje dosyć prosty wkład, taki jak naprawianie uszkodzonych lub niepoprawnych linków, dodawanie brakujących przykładów kodu lub rozwiązywanie ograniczonych problemów z zawartością. W niektórych przypadkach te problemy mogą dotyczyć bardzo wielu plików. W takim przypadku powiadom nas, nad czym chcesz pracować, zanim zaczniesz. Dodaj komentarz do problemu, aby poinformować nas, że nad nim pracujesz.

- **Aktualizacje zawartości**. Biorąc pod uwagę ogrom zbioru dokumentów, zawartość łatwo staje się przestarzała i wymaga poprawy. Ponadto z różnych przyczyn niektóre treści zostały zduplikowane, a nawet występują trzykrotnie. Aktualizowanie zawartości wymaga upewnienia się, że poszczególne tematy są aktualne lub poprawiają treść w obszarze funkcji w celu wyeliminowania duplikacji i zapewnienia, że cała unikatowa zawartość jest zachowana w mniejszym zbiorze dokumentacji.

- **Tworzenie nowych treści**. Jeśli interesuje Cię tworzenie własnego tematu, następujące problemy zawierają listę tematów, o których wiemy, że chcemy je dodać do naszego zestawu dokumentów. Poinformuj nas jednak, zanim zaczniesz pracować nad tematem. Jeśli interesuje Cię napisanie tematu, który nie został tu wymieniony, otwórz problem.

Możesz też obejrzeć naszą listę [otwartych problemów](https://github.com/dotnet/docs/issues) i zgłosić się na ochotnika do pracy przy tych, które Cię interesują. Do oznaczania problemów określonych jako czekające na wkład społeczności używamy etykiety [do wzięcia](https://github.com/dotnet/docs/labels/up-for-grabs). Zazwyczaj wymagają one minimalnego kontekstu i doskonale nadają się na pierwsze problemy. Zachęcamy doświadczonych współautorów w naszej społeczności do przyjrzenia się wszelkim interesującym problemom. Jeśli jakiś znajdziesz, dodaj komentarz, aby zapytać, czy jest otwarty.

Gdy wybierzesz zadanie, nad którym będziesz pracować, postępuj zgodnie z przewodnikiem [Rozpoczynanie pracy](get-started-setup-github.md), aby utworzyć konto w serwisie GitHub i skonfigurować swoje środowisko.

**Krok 2.** W miarę potrzeb utwórz rozwidlenie repozytoriów `/dotnet/docs`, `dotnet/samples`, `dotnet/dotnet-api-docs`, `dotnet/roslyn-api-docs` lub `dotnet/ml-api-docs` i utwórz gałąź dla swoich zmian.

W przypadku małych zmian zapoznaj się z instrukcjami edytowania w usłudze GitHub na [stronie głównej](index.md#quick-edits-to-existing-documents) przewodnika współautora.

**Krok 3.** Wprowadzaj zmiany w tej nowej gałęzi.

Jeśli jest to nowy temat, jako punktu początkowego możesz użyć tego [pliku szablonu](dotnet-style-guide.md). Zawiera on wytyczne dotyczące pisania, jak również objaśnia metadane wymagane dla każdego artykułu, takie jak informacje o autorze.

W kroku 1 przejdź do folderu odpowiadającego lokalizacji w spisie treści określonej dla Twojego artykułu. Ten folder zawiera pliki Markdown dla wszystkich artykułów w tej sekcji. W razie potrzeby utwórz nowy folder na pliki dla Twojej zawartości. Główny artykuł w tej sekcji nosi nazwę *index.md*. W przypadku obrazów i innych zasobów statycznych utwórz podfolder o nazwie **media** wewnątrz folderu zawierającego Twój artykuł, jeśli jeszcze nie istnieje. Wewnątrz folderu **media** utwórz podfolder mający nazwę artykułu (z wyjątkiem pliku indeksu). Przykład kodu powinien znajdować się w repozytorium `dotnet/samples` zgodnie z opisem w sekcji dotyczącej [przykładów](#contributing-to-samples).

Należy pamiętać o przestrzeganiu składni Markdown. Typowe przykłady można znaleźć w [ściągawce dla szablonów i języka markdown](dotnet-style-guide.md).

## <a name="example-structure"></a>Struktura przykładu

    docs
      /about
      /core
        /porting
          porting-overview.md
          /media
            /porting-overview
                portability_report.png

**Krok 4.** Prześlij żądanie ściągnięcia ze swojej gałęzi do gałęzi głównej.

> [!IMPORTANT]
> Funkcjonalność [automatyzacji komentarza](how-to-write-workflows-major.md#review-and-sign-off) jest teraz niedostępna w każdym z repozytoriów dokumentów platformy .NET. Członkowie zespołu dokumentacji platformy .NET sprawdzą i scalą Twoje żądanie ściągnięcia.

Każde żądanie ściągnięcia zazwyczaj powinno dotyczyć jednego rozwiązania problemu naraz. Żądanie ściągnięcia może modyfikować jeden lub więcej plików. Jeśli wprowadzasz wiele poprawek do różnych plików, zalecane są różne żądania ściągnięcia. Jeśli tworzysz przykłady oraz aktualizujesz znaczniki markdown, musisz utworzyć oddzielne żądania ściągnięcia dla przykładów.

Jeśli Twoje żądanie ściągnięcia naprawi istniejący problem, dodaj słowo kluczowe `Fixes #Issue_Number` do komunikatu zatwierdzenia lub opisu żądania ściągnięcia. Dzięki temu problem zostanie automatycznie zamknięty po scaleniu żądania ściągnięcia. Aby uzyskać więcej informacji, zobacz [Zamykanie problemów za pomocą komunikatów zatwierdzania](https://help.github.com/articles/closing-issues-via-commit-messages/).

Zespół platformy .NET sprawdzi Twoje żądanie ściągnięcia i da Ci znać, czy do jego zatwierdzenia są konieczne jakiekolwiek inne aktualizacje/zmiany.

**Krok 5.** Wprowadź wszelkie niezbędne aktualizacje do swojej gałęzi w sposób omówiony z zespołem.

Osoby odpowiedzialne za obsługę scalą Twoje żądanie ściągnięcia z gałęzią główną, gdy opinia zostanie zastosowana i Twoja zmiana zostanie zatwierdzona.

Regularnie wypychamy wszystkie zatwierdzenia z gałęzi głównej do gałęzi opublikowanej. Gdy to zrobimy, zobaczysz swój wkład upubliczniony pod adresem https://docs.microsoft.com/dotnet/. W dni robocze zazwyczaj publikujemy codziennie. Czynności konserwacyjne mogą opóźnić publikowanie o kilka dni.

## <a name="contributing-to-samples"></a>Współtworzenie przykładów

Repozytorium [dotnet/samples](https://github.com/dotnet/samples) zawiera wszystkie przykłady kodu, które są częścią dowolnego tematu w ramach dokumentacji platformy .NET. Istnieje kilka różnych projektów uporządkowanych w podfolderach. Te podfoldery są uporządkowane w sposób podobny do uporządkowania dokumentów dla platformy .NET.

Wprowadzamy następujące rozróżnienie dla kodu istniejącego w naszym repozytorium:

- Przykłady: czytelnicy mogą pobrać i uruchomić przykłady. Wszystkie przykłady powinny być kompletnymi aplikacjami lub bibliotekami. Gdy przykład tworzy bibliotekę, powinien on zawierać testy jednostkowe lub aplikację, która umożliwi czytelnikom uruchomienie kodu. W przykładach często używana jest więcej niż jedna technologia, funkcja lub zestaw narzędzi. Plik readme.md dla każdego przykładu będzie odwoływał się do artykułu, co pozwoli przeczytać więcej na temat koncepcji objętej każdym przykładem.
- Fragmenty kodu: ilustrują mniejszą koncepcję lub zadanie. Można je skompilować, ale nie mają one być kompletnymi aplikacjami. Powinny się one poprawnie uruchomić, ale nie są przykładowymi aplikacjami dla typowego scenariusza. Zamiast tego są zaprojektowane tak, aby były jak najmniejsze w celu zilustrowania pojedynczej koncepcji lub funkcji. Nie powinny zajmować więcej niż jednego ekranu kodu.

Cały kod znajduje się w repozytorium [dotnet/samples](https://github.com/dotnet/samples). Pracujemy nad modelem, w którym struktura naszego folderu przykładów będzie pasować do struktury naszego folderu dokumentów. Do standardów, których przestrzegamy, należą:

- Folder *snippets* najwyższego poziomu zawiera fragmenty kodu dla małych, konkretnych przykładów.
- Przykłady dla dokumentacji interfejsu API znajdują się w folderze zgodnym z tym wzorcem: *snippets/\<język>/api/\<przestrzeń nazw>/\<nazwa interfejsu api>*.
- Inne foldery najwyższego poziomu są zgodne z folderami najwyższego poziomu w repozytorium *docs*. Na przykład w repozytorium docs jest folder *machine-learning/tutorials*, a przykłady dotyczące samouczków uczenia maszynowego są w folderze *samples/machine-learning/tutorials*.

Ponadto wszystkie przykłady w folderach *core* i *standard* powinny się skompilować i uruchomić na wszystkich platformach obsługiwanych przez platformę .NET Core. Nasz system kompilacji ciągłej integracji wymusi to. Folder najwyższego poziomu *framework* zawiera przykłady, które są kompilowane i weryfikowane tylko w systemie Windows.

Przykładowe projekty powinny umożliwiać kompilację i uruchomienie na najszerszym możliwym zestawie platform dla danego przykładu. W praktyce oznacza to kompilowanie aplikacji konsoli opartych na platformie .NET Core, gdzie to możliwe. Przykłady, które są specyficzne dla środowiska internetowego lub interfejsu użytkownika, powinny w razie potrzeby dodawać te narzędzia. Przykłady obejmują aplikacje internetowe, aplikacje mobilne, aplikacje WPF lub WinForms itd.

Pracujemy nad przygotowaniem systemu ciągłej integracji dla całego kodu. Gdy wprowadzasz jakiekolwiek aktualizacje do poprawek, upewnij się, że każda aktualizacja jest częścią projektu z możliwością kompilacji. Idealnie byłoby, gdyby do przykładów zostały również dodane poprawności.

Każdy kompletny przykład, który tworzysz, powinien zawierać plik *readme.md*. Ten plik powinien zawierać krótki opis przykładu (jeden lub dwa akapity). Plik *readme.md* powinien informować czytelników o tym, czego się dowiedzą, analizując ten przykład. Plik *readme.md* powinien też zawierać link do opublikowanego dokumentu w [witrynie dokumentacji platformy .NET](https://docs.microsoft.com/dotnet/welcome). Aby ustalić, gdzie dany plik w repozytorium jest zamapowany na daną witrynę, zastąp fragment `/docs` w ścieżce repozytorium fragmentem `http://docs.microsoft.com/dotnet`.

Twój temat będzie też zawierał linki do przykładu. Link powinien prowadzić bezpośrednio do folderu przykładu w usłudze GitHub.

### <a name="writing-a-new-snippet-or-sample"></a>Pisanie nowego fragmentu kodu lub przykładu

1. Twój przykład **musi być częścią projektu z możliwością kompilacji**. Gdzie to możliwe, projekty powinny dać się skompilować na wszystkich platformach obsługiwanych przez platformę .NET Core. Wyjątkiem są przykłady pokazujące specyficzną dla platformy funkcję lub narzędzie.

2. Twój przykład powinien być zgodny ze [stylem kodowania corefx](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md) w celu zachowania spójności.

    - Ponadto preferujemy stosowanie metod `static` zamiast metod wystąpień podczas prezentowania czegoś, co nie wymaga tworzenia wystąpień nowego obiektu.

3. Twój przykład powinien zawierać **odpowiednią obsługę wyjątków**. Powinien obsługiwać wszystkie wyjątki, które mogą być zgłaszane w kontekście tego przykładu. Przykładowo kod wywołujący metodę [Console.ReadLine](https://docs.microsoft.com/dotnet/api/system.console.readline) w celu pobrania danych wejściowych użytkownika powinien używać odpowiedniej obsługi wyjątków, gdy ciąg wejściowy jest przekazywany jako argument do metody. Analogicznie jeśli Twój przykład oczekuje niepowodzenia wywołania metody, wynikowy wyjątek musi zostać obsłużony. Zawsze należy obsługiwać konkretne wyjątki zgłaszane przez metodę, a nie wyjątki klasy bazowej, takie jak [Exception](https://docs.microsoft.com/dotnet/api/system.exception) lub [SystemException](https://docs.microsoft.com/dotnet/api/system.systemexception).

4. Jeśli Twój przykład tworzy autonomiczny pakiet, musisz dołączyć środowiska uruchomieniowe używane przez nasz system kompilacji ciągłej integracji oprócz wszelkich środowisk uruchomieniowych używanych przez Twój przykład:
    - `win7-x64`
    - `win8-x64`
    - `win81-x64`
    - `ubuntu.16.04-x64`

Wkrótce będziemy mieli gotowy system ciągłej integracji umożliwiający kompilację tych projektów.

Aby utworzyć przykład:

1. Zgłoś [problem](https://github.com/dotnet/docs/issues) lub dodaj komentarz dotyczący istniejącego problemu, nad którym pracujesz.
2. Napisz temat, który objaśnia koncepcje przedstawiane w Twoim przykładzie (na przykład: `docs/standard/linq/where-clause.md`).
3. Napisz swój przykład (na przykład: `WhereClause-Sample1.cs`).
4. Za pomocą głównego punktu wejścia utwórz plik Program.cs, który wywołuje Twoje przykłady. Jeśli już istnieje, dodaj wywołanie to Twojego przykładu:
    ```csharp
    public class Program
    {
        public void Main(string[] args)
        {
            WhereClause1.QuerySyntaxExample();

            // Add the method syntax as an example.
            WhereClause1.MethodSyntaxExample();
        }
    }
    ```
Dowolny fragment kodu platformy .NET Core lub przykład kompilujesz za pomocą interfejsu wiersza polecenia platformy .NET Core, który można zainstalować za pomocą [zestawu .NET Core SDK](https://www.microsoft.com/net/download). Aby skompilować i uruchomić Twój przykład:

1. Przejdź do folderu przykładu i skompiluj go, aby sprawdzić, czy nie ma w nim błędów:

    ```console
    dotnet build
    ```
2. Uruchom swój przykład:

    ```console
    dotnet run
    ```

3. Dodaj plik readme.md do głównego katalogu Twojego przykładu. 

   Powinien on zawierać krótki opis kodu i kierować czytelników do artykułu, który odwołuje się do przykładu.

Oprócz wyraźnie zaznaczonych, wszystkie przykłady są kompilowane z wiersza polecenia na dowolnej platformie obsługiwanej przez platformę .NET Core. Istnieje kilka przykładów specyficznych dla platformy Visual Studio i wymagających programu Visual Studio 2017 lub nowszego. Ponadto niektóre przykłady pokazują funkcje specyficzne dla platformy i będą wymagać konkretnej platformy. Inne przykłady i fragmenty kodu wymagają platformy .NET Framework i będą działać na platformach systemu Windows oraz będą potrzebować dodatku Developer Pack dla docelowej wersji platformy Framework.

## <a name="the-c-interactive-experience"></a>Interaktywna platforma języka C#

Wszystkie przykłady przedstawione w artykule używają [tagu języka](how-to-write-use-markdown.md#code-snippets) do wskazania języka źródłowego. Krótkie przykłady kodu w języku C# mogą używać tagu języka `csharp-interactive` do określenia przykładu w języku C# uruchomionego w przeglądarce. (Przykłady kodu w tekście używają tagu `csharp-interactive`, a dla fragmentów kodu dołączonych ze źródła należy użyć tagu `code-csharp-interactive`). Te przykłady kodu pokazują w artykule okno kodu i okno wyjściowe. Okno wyjściowe pokazuje wszelkie dane wyjściowe po wykonaniu interaktywnego kodu, gdy użytkownik uruchomił przykład.

Interaktywna platforma języka C# zmienia sposób pracy z przykładami. Goście mogą uruchomić przykład, aby zobaczyć wyniki. Wiele czynników pomaga ustalić, czy przykład lub odpowiadający mu tekst ma zawierać informacje o danych wyjściowych.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Kiedy wyświetlić oczekiwane dane wyjściowe bez uruchamiania przykładu

- Artykuły przeznaczone dla początkujących powinny udostępniać dane wyjściowe, aby czytelnicy mogli porównać dane wyjściowe swojej pracy z oczekiwaną odpowiedzią.
- Dane wyjściowe powinny być prezentowane dla przykładów, w których dane wyjściowe są integralną częścią tematu. Na przykład artykuły na temat sformatowanego tekstu powinny pokazywać format tekstu bez uruchamiania przykładu.
- Gdy zarówno przykład, jak i oczekiwane dane wyjściowe są krótkie, rozważ pokazanie danych wyjściowych. Zaoszczędzi to trochę czasu.
- Artykuły objaśniające, jak bieżąca kultura lub kultura niezmienna wpływają na dane wyjściowe, powinny objaśniać oczekiwane dane wyjściowe. Interaktywna pętla REPL (Read Evaluate Print Loop) działa na hostach opartych na systemie Linux. Domyślna kultura i kultura niezmienna tworzą inne dane wyjściowe dla różnych systemów operacyjnych i maszyn. Artykuł powinien objaśniać dane wyjściowe w systemach Windows, Linux i Mac.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Kiedy wykluczać oczekiwane dane wyjściowe z przykładu

- Artykuły, gdzie przykład generuje większe dane wyjściowe, nie powinny zawierać ich w komentarzach. Przesłania to kod, gdy przykład zostanie uruchomiony.
- Artykuły, gdzie przykład jest ilustracją tematu, ale dane wyjściowe nie są konieczne do jego zrozumienia. Na przykład kod uruchamiający zapytanie LINQ w celu wyjaśnienia składni zapytania, a następnie wyświetlający każdy element z kolekcji wyjściowej.

> [!NOTE]
> Możesz zauważyć, że niektóre tematy nie do końca przestrzegają wszystkich podanych tutaj wytycznych. Pracujemy nad osiągnięciem spójności w ramach witryny. Sprawdź listę [otwartych problemów](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3A%22%3Abookmark_tabs%3A+Information+Architecture%22), które obecnie śledzimy, szukając tego określonego celu.

## <a name="contributor-license-agreement"></a>Umowa licencyjna współautora

Zanim Twoje żądanie ściągnięcia zostanie scalone, musisz podpisać [Umowę licencyjną współautora platformy .NET Foundation (CLA)](https://cla.dotnetfoundation.org). Jest to jednorazowe wymaganie dla projektów na platformie .NET Foundation. Więcej na temat [umów licencyjnych współautora (CLA)](http://en.wikipedia.org/wiki/Contributor_License_Agreement) możesz przeczytać w Wikipedii.

Umowa: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

Nie musisz z góry podpisywać umowy. Możesz sklonować, rozwidlić i przekazać swoje żądanie ściągnięcia w zwykły sposób. Gdy Twoje żądanie ściągnięcia jest tworzone, jest ono klasyfikowane przez bota CLA. Jeśli zmiana jest mała (na przykład udało Ci się poprawić literówkę), wówczas żądanie ściągnięcia dostaje oznaczenie `cla-not-required`. W przeciwnym razie jest ono klasyfikowane jako `cla-required`. Po podpisaniu umowy CLA bieżące i wszystkie przyszłe żądania ściągnięcia będą oznaczone jako `cla-signed`.
