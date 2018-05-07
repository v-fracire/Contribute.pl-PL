---
title: Współtworzenie zawartości witryny docs.microsoft.com
description: Ten artykuł zawiera opis różnych sposobów współtworzenia zawartości witryny docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 01/17/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: bc6f9c314eda5f0d950da049374a7a157f16782a
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-contribute-to-docsmicrosoftcom"></a>Współtworzenie zawartości witryny docs.microsoft.com

Istnieje kilka sposobów uczestnictwa w ulepszaniu zawartości witryny [docs.microsoft.com](https://docs.microsoft.com):

- Możesz [tworzyć zagadnienia](#create-issues) polecające nowe artykuły lub poprawiające istniejące artykuły.
- Możesz [szybko edytować](#quick-edits) artykuły w edytorze GitHub online, by dokonywać niewielkich zmian.
- Możesz [przeglądać wersje robocze nowych artykułów](#review-new-articles), aby upewnić się, że charakteryzują się odpowiednią jakością i dokładnością techniczną.
- Możesz [tworzyć nowe artykuły](#create-new-articles) dotyczące tematów, które chcesz wzbogacić.
- Możesz [aktualizować](#update-samples) lub [tworzyć](#create-samples) przykłady w celu poprawy przykładowego kodu ilustrującego ważne pojęcia.

W tym artykule poznasz różne sposoby współtworzenia zawartości, sprawdzisz, jak wykonać każde z tych zadań, i znajdziesz łącza do dodatkowych informacji na temat każdego z nich.

Nasze repozytoria publiczne są hostowane w witrynie [GitHub](https://wwww.GitHub.com).  Aby uczestniczyć w tworzeniu naszych repozytoriów dokumentacji, należy utworzyć konto w witrynie GitHub.

Potrzebny będzie również edytor tekstowy, aby aktualizować dokumenty. Firma Microsoft zaleca program [Visual Studio Code](https://www.visualstudio.com/code). Musisz znać podstawy składni języka [Markdown](https://daringfireball.net/projects/markdown/syntax).

W przypadku dodawania lub modyfikowania przykładów potrzebne będzie środowisko programistyczne. Firma Microsoft zaleca program [Visual Studio](https://www.visualstudio.com) na komputerach PC i Mac lub program [Visual Studio Code](https://www.visualstudio.com/code) na wszystkich platformach.

## <a name="create-issues"></a>Tworzenie problemów

Jeśli w artykule będą jakieś nieścisłości lub coś zostanie pominięte, utwórz do tego artykułu problem. Najprostszym sposobem znalezienia prawidłowej lokalizacji jest kliknięcie przycisku „Edit” (Edytuj) w przeglądarce, co spowoduje przejście do źródła artykułu w odpowiednim publicznym repozytorium witryny GitHub. W tym miejscu można pobrać adres URL dla źródła tego artykułu, który widoczny jest w pasku adresu. Kliknij przycisk „Create Issue” (Utwórz problem), aby utworzyć nowy problem dla tego artykułu.

> [!NOTE]
> Jeśli znajdziesz problemy, które można rozwiązać za pomocą drobnych modyfikacji, np. błędy ortograficzne lub gramatyczne, możesz zaoszczędzić czas sobie i innym, [przesyłając poprawkę](#quick-edits) po edycji źródła za pomocą przeglądarki.

Większość repozytoriów publicznych firmy Microsoft zawiera szablony nowych problemów, które pomagają w podaniu informacji potrzebnych do rozwiązania problemu.

Nowy problem możesz również utworzyć, jeśli nie udaje Ci się znaleźć potrzebnych informacji. Procedura ta wygląda tak samo: należy utworzyć nowy problem w jednym z publicznych repozytoriów dokumentów. Poinformuj firmę Microsoft o tym, co było wyszukiwane, co miało być zrobione i dlaczego znalezione artykuły nie okazały się wystarczająco pomocne.

## <a name="review-new-articles"></a>Przeglądanie nowych artykułów

Jeśli pracujesz z nowym oprogramowaniem, np. wersją CTP lub beta, prawdopodobnie tworzymy dokumenty w tym samym czasie, gdy Ty analizujesz technologię. Dokumenty wewnątrzprocesowe znajdują się w repozytoriach publicznych firmy Microsoft. Jeśli masz jakieś komentarze, możesz pomóc nam je ulepszyć przed ich wydaniem.

Nowe artykuły są przeglądane publicznie za pomocą procesu [przepływu witryny GitHub](https://guides.github.com/introduction/flow/). Przejrzyj nasze repozytoria dokumentów i sprawdź otwarte żądania ściągnięcia (PR, pull request). Oczekujemy na komentarze i recenzje dotyczące otwartych żądań ściągnięcia. Pomoże nam to opublikować lepszą zawartość już dla pierwszej wersji i nie będziemy musieli czekać na opinie po publikacji wersji.

Firma Microsoft szuka sposobów na zwiększenie technicznej dokładności, klarowności opisów oraz poprawności gramatycznej.

## <a name="quick-edits"></a>Szybka edycja

Szybka edycja to sposób na wprowadzenie drobnych poprawek przy użyciu edytora opartego na przeglądarce. Jeśli znajdziesz niewielkie błędy ortograficzne lub gramatyczne lub źle nazwane interfejsy API, możesz pominąć tworzenie problemu, dokonując edycji i przesyłając żądanie ściągnięcia.

W dowolnym artykule kliknij przycisk „Edit” (Edytuj) (zazwyczaj w prawej górnej części strony), wprowadź poprawki i kliknij przycisk „Submit PR” (Prześlij żądanie ściągnięcia) u dołu strony. Firma Microsoft przejrzy żądanie ściągnięcia i scali je podczas codziennego przeglądu żądań ściągnięcia.

## <a name="create-new-articles"></a>Tworzenie nowych artykułów

Jeśli istnieją pojęcia, które Cię pasjonują i które chcesz wyjaśnić innym osobom, możesz utworzyć artykuły i przesłać żądanie ściągnięcia.

Tworzenie nowych artykułów jest czasochłonne i dlatego doceniamy czas i wkład pracy naszych użytkowników. Chcemy angażować się na wczesnym etapie procesu, aby zadbać o to, by użytkownicy od początku stosowali się do naszych wskazówek i stylu. Zalecamy następujące czynności:

1. [Utwórz problem](#create-issues), opisując, czego brakuje i jak można temu zaradzić.
1. Zamieść komentarz dotyczący problemu, informując firmę Microsoft, że chcesz się nim zająć, oraz zaproponuj konspekt i streszczenie artykułu.
1. Firma Microsoft odpowie, przesyłając sugestie. Mogą one obejmować linki do artykułów o podobnej tematyce, sugestie dotyczące przykładów lub sposób uporządkowania artykułu.
1. Po otrzymaniu zgody na konspekt artykułu, utwórz rozwidlenie repozytorium i rozpocznij pracę.
1. Na początku procesu otwórz żądanie ściągnięcia z ciągiem „[WIP]” na początku tytułu.
1. Jeden z głównych współautorów prześle Ci wstępną opinię.
1. Pisz dalej i @-mention zawiadom osobę, która przejrzała pierwszą wersję, gdy będzie potrzeba więcej informacji zwrotnych.
1. Usuń oznaczenie „[WIP]”, gdy nadejdzie czas na ostateczny przegląd.
1. Odpowiadanie na opinię
1. Główni współautorzy scalą Twoje żądnie ściągnięcia.

Istnieje kilka punktów z tej listy, które warto mówić szerzej. Ogólnie rzecz biorąc, korzystamy z procesu [przepływu witryny GitHub](https://guides.github.com/introduction/flow/), aby jak najszybciej przeglądać zawartość. Dzięki temu ustalimy, gdzie należy umieścić artykuł w spisie treści, jakie korzyści będą mieli czytelnicy z nowego artykułu oraz zakres przykładów, które zostaną utworzone. Możemy wcześnie wskazać konieczne zmiany, zanim poświęcisz znaczną ilość czasu na pisanie.

## <a name="update-samples"></a>Aktualizacja przykładów

Być może niektóre przykłady zostały pierwotnie napisane kilka wersji wcześniej za pomocą rozwiązań, które nie są już zalecane. Użytkownicy mogą pomóc firmie Microsoft w aktualizacji tych przykładów. Może się też okazać, że prosta zmiana nazwy zmiennej może zwiększyć czytelność wyjaśnienia.

Przykładowy kod wyświetlany z każdym artykułem stanowi część programów, które są kompilowane i często testowane w naszym systemie CI.

Aby wprowadzić drobne aktualizacje, należy znaleźć źródło w odpowiednim repozytorium, wprowadzić zmianę kodu w przeglądarce i przesłać żądanie ściągnięcia. Nasz system CI skompiluje zmiany i scalimy żądanie ściągnięcia po zakończeniu tej operacji.

W przypadku zmian o większym zakresie utwórz rozwidlenie repozytorium i wprowadź zmiany w ulubionym środowisku programistycznym. Pamiętaj, aby dodać trochę testów, aby mieć pewność, że zmiany przyniosą oczekiwany efekt. Prześlij żądanie ściągnięcia, a firma Microsoft je przeanalizuje.

W przypadku wszystkich zmian kodu postępuj zgodnie z istniejącymi konwencjami kodowania dla przykładowego kodu, który modyfikujesz. Nasze standardy kodowania repozytoriów przykładów będą takie same jak stosowane w odpowiednich zespołach produktu. Sprawdź poszczególne repozytoria pod kątem konkretnych wskazówek.

> [!NOTE]
> Sami pracujemy nad tym, by stosować się do tych wskazówek. Niektóre z przykładów powstały wcześniej niż nasze bieżące standardy i nie zostały jeszcze zaktualizowane. Dążymy do tego, by wszystkie działające przykładowe kody były wyświetlane z działających, przetestowanych przykładów.

## <a name="create-samples"></a>Tworzenie przykładów

Można również utworzyć nowe przykłady przedstawiające pojęcia i scenariusze. Każdy przykład musi być powiązany z artykułem, który wyjaśnia najważniejsze informacje z przykładu.

Jeśli nowy przykład uzupełnia istniejący artykuł, dodaj odwołanie do przykładu w tym artykule. Jeśli tak nie jest, wspólnie z nami [napisz artykuł](#create-new-articles), do którego zostanie dołączony przykład.

We wszystkich przypadkach nasz przykładowy kod jest zgodny z konwencjami kodowania, z których korzystają powiązane zespoły produktu. Jedynym wyjątkiem jest fakt, że częściej używamy jawnie wpisanych zmiennych zamiast zmiennych wpisanych niejawnie (zadeklarowanych za pomocą `var`) w celu zapewnienia klarowności, jeśli te deklaracje znajdują się w artykule.

Wykonaj przykładowy proces opisany we wcześniejszej sekcji dla [nowych artykułów](#create-new-articles), abyśmy mogli sprawdzić kod na wczesnym etapie procedury programistycznej.
