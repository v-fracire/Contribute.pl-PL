---
title: Docs Authoring Pack for VS Code
description: W tym artykule opisano pakiet rozszerzenia programu VS Code ułatwiający tworzenie dokumentów w formacie Markdown dla witryny docs.microsoft.com.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.openlocfilehash: b9fedce0a73c5c4212ffd0893c745fab56677c8c
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308921"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs Authoring Pack for VS Code

Docs Authoring Pack to kolekcja rozszerzeń programu VS Code, które wspomagają tworzenie dokumentów w formacie Markdown dla witryny docs.microsoft.com. Pakiet jest [dostępny w witrynie VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) i zawiera następujące rozszerzenia:

- [markdownlint:](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) popularny linter języka Markdown autorstwa Davida Ansona, który pomaga w korzystaniu z najlepszych rozwiązań języka Markdown.
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): działający całkowicie w trybie offline moduł sprawdzania pisowni autorstwa firmy Street Side Software.
- [Docs Preview](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): korzysta z kaskadowych arkuszy stylów CSS witryny docs.microsoft.com w celu dokładniejszego podglądu elementów Markdown, w tym elementów niestandardowych Markdown.
- [Docs Markdown:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) zapewnia wsparcie przy tworzeniu zawartości witryny docs.microsoft.com w języku Markdown w systemie Open Publishing System (OPS), w tym zapewnia podstawową obsługę języka Markdown oraz obsługę niestandardowej składni języka Markdown w systemie OPS. W pozostałej części tego tematu opisano rozszerzenie Docs Markdown.
- [Docs Article Templates](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): umożliwia użytkownikom wykorzystanie szkieletu Markdown w nowych plikach.

## <a name="prerequisites-and-assumptions"></a>Wymagania wstępne i założenia

Aby precyzyjnie wstawiać linki względne, obrazy i inną zawartość osadzoną przy użyciu rozszerzenia Docs Markdown, musisz mieć obszar roboczy programu VS Code w zakresie folderu głównego sklonowanego repozytorium OPS (Open Publishing System).

Niektóre przypadki składni obsługiwanej przez rozszerzenie, np. alerty i fragmenty kodu, są niestandardowymi elementami języka Markdown dla systemu OPS i nie będą prawidłowo renderowane, chyba że zostaną opublikowane za pośrednictwem systemu OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Sposób użycia rozszerzenia Docs Markdown

Aby uzyskać dostęp do menu rozszerzenia Docs Markdown, wpisz `ALT+M`. Możesz kliknąć lub użyć strzałek w górę/w dół, aby wybrać żądaną funkcję, lub wpisać tekst, aby rozpocząć filtrowanie, a następnie nacisnąć przycisk `ENTER`, kiedy żądana funkcja zostanie podświetlona w menu. Dostępne są następujące funkcje:

|Funkcja     |Opis           |
|-------------|----------------------|
|Podgląd      |Wyświetlanie podglądu aktywnego tematu w oknie obok przy użyciu rozszerzenia Doc Preview. Ta opcja jest dostępna tylko wtedy, gdy zainstalowano rozszerzenie Docs Preview.|
|Pogrubienie         |Formatuje tekst jako **pogrubiony**.|
|Kursywa       |Formatuje tekst jako *kursywę*.|
|Kod         |W przypadku zaznaczenia jednego wiersza lub mniej formatuje tekst jako `inline code`.<br><br>Jeśli zostanie zaznaczonych wiele wierszy, funkcja sformatuje je jako odgrodzony blok kodu oraz umożliwi opcjonalne wybranie języka programowania obsługiwanego przez system OPS.|
|Alert        |Wstawia alerty Uwaga, Ważne, Ostrzeżenie lub Porada.<br><br>Wybierz opcję Alert z menu, a następnie wybierz typ alertu. Jeśli wcześniej zaznaczono tekst, zostanie on otoczony składnią wybranego alertu. Jeśli nie wybrano tekstu, zostanie dodany nowy alert z tekstem zastępczym.|
|Lista numerowana|Wstawia nową listę numerowaną.<br><br> Jeśli zaznaczono wiele wierszy, każdy z nich będzie pozycją na liście. Zauważ, że listy numerowane są wyświetlane w języku Markdown jako same numery 1, ale będą renderowane w witrynie docs.microsoft.com jako kolejne liczby lub, w przypadku list zagnieżdżonych, litery. Aby utworzyć zagnieżdżoną listę numerowaną, naciśnij klawisz TAB z pozycji listy nadrzędnej.|
|Lista punktowana|Wstawia nową listę punktowaną.|
|Tabela        |Wstawia strukturę tabeli języka Markdown.<br><br>Po wybraniu polecenia tabeli określ liczbę kolumn i wierszy w formacie kolumny:wiersze, np. 3:4. Zauważ, że maksymalna liczba kolumn, które możesz określić za pośrednictwem rozszerzenia, to 5 — jest to też zalecane maksimum zapewniające czytelność.|
|Link do pliku w repozytorium|Wstawia link względny do innego pliku w bieżącym repozytorium. Po wybraniu tej opcji wpisz tekst w oknie polecenia, aby filtrować pliki według nazwy, a następnie wybierz żądany plik. Jeśli masz już zaznaczony tekst, stanie się on tekstem przypisanym do linku. W przeciwnym razie jako tekst linku w pliku docelowym zostanie użyty tekst oznaczony jako H1.|
|Link do strony sieci Web    |Wstawia link do strony sieci Web. Po wybraniu tej opcji wklej lub wpisz do okna poleceń identyfikator URI. Ciąg `https://` jest wymagany. Jeśli masz już zaznaczony tekst, stanie się on tekstem przypisanym do linku. W przeciwnym razie jako tekst linku zostanie wykorzystany identyfikator URI.|
|Link do nagłówka     |Tworzy link do zakładki w bieżącym pliku lub w innym pliku w repozytorium.<br>`Bookmark in this file`: wybierz z listy nagłówków w bieżącym pliku, aby wstawić prawidłowo sformatowaną zakładkę.<br>`Bookmark in another file`: najpierw odfiltruj według nazwy pliku i wybierz plik do połączenia, a następnie wybierz odpowiedni nagłówek w wybranym pliku.|
|Obraz        |Wpisz tekst alternatywny (wymagany na potrzeby ułatwień dostępu) i wybierz go, a następnie wywołaj to polecenie, aby odfiltrować listę obsługiwanych plików obrazów w repozytorium i wybrać żądany plik. Jeśli jeszcze nie wybrano tekstu alternatywnego podczas wywoływania tego polecenia, pojawi się monit o wprowadzenie tekstu, zanim będzie można wybrać plik obrazu.|
|Uwzględnij      |Znajdź plik do osadzenia w bieżącym pliku.|
|Fragment kodu      |Znajdź fragment kodu w repozytorium, aby osadzić go w bieżącym pliku.|
|Filmy        |Dodaj osadzone wideo.|
|Szablon     |Utwórz nowy plik i zastosuj szablon Markdown. Aby uzyskać więcej informacji, zobacz temat [Szablony](#how-to-use-docs-templates) poniżej.|

## <a name="how-to-assign-keyboard-shortcuts"></a>Jak przypisywać skróty klawiaturowe

1. Wpisz `CTRL+K` i `CTRL+S`, aby otworzyć listę skrótów klawiaturowych.
1. Wyszukaj polecenie, np. `formatBold`, dla którego chcesz utworzyć niestandardowe powiązanie klawiszy.
1. Kliknij znak plusa, który zostanie wyświetlony obok nazwy polecenia, kiedy przesuniesz wskaźnik myszy nad wiersz.
1. Kiedy nowe pole wejściowe będzie widoczne, wpisz skrót klawiaturowy, który chcesz powiązać z tym konkretnym poleceniem. Przykładowo aby użyć typowego skrótu dla pogrubienia, wpisz `ctrl+b`.
1. Dobrze jest też wstawić klauzulę `when` do powiązania klawiszy, aby nie było ono dostępne w plikach innych niż pliki języka Markdown. Aby to zrobić, otwórz plik *keybindings.json* i wstaw następujący wiersz pod nazwą polecenia (upewnij się, że pomiędzy wierszami dodano przecinek):
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    Gotowe niestandardowe powiązanie klawiszy powinno wyglądać następująco w pliku keybindings.json:

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. Zapisz plik keybindings.json.

Zobacz [Powiązania klawiszy](https://code.visualstudio.com/docs/getstarted/keybindings) w dokumentacji programu VS Code, aby uzyskać więcej informacji.

## <a name="how-to-show-the-legacy-toolbar"></a>Jak wyświetlić starszy pasek narzędzi

Użytkownicy wersji przedwdrożeniowej rozszerzenia zauważą, że po zainstalowaniu rozszerzenia Docs Markdown pasek narzędzi tworzenia nie pojawia się już u dołu okna programu VS Code. Dzieje się tak, ponieważ pasek narzędzi zajmował dużo miejsca na pasku stanu programu VS Code i nie korzystał z najlepszych rozwiązań środowiska użytkownika rozszerzenia, więc został uznany za przestarzały w nowym rozszerzeniu. Jednak możesz też opcjonalnie wyświetlić pasek narzędzi, aktualizując plik settings.json programu VS Code w następujący sposób:

1. W programie VS Code przejdź do pozycji Plik -> Preferencje -> Ustawienia (`CTRL+Comma`).
1. Wybierz pozycję Ustawienia użytkownika, aby zmienić ustawienia dla wszystkich obszarów roboczych programu VS Code, lub pozycję Ustawienia obszaru roboczego, aby zmienić ustawienia tylko dla bieżącego obszaru roboczego.
1. W okienku Ustawienia domyślne znajdź pozycję Konfiguracja rozszerzenia Docs Authoring i wybierz ikonę ołówka obok żądanego ustawienia. Następnie zobaczysz monit o wybranie opcji `true` lub `false`. Po dokonaniu wyboru program VS Code automatycznie doda wartość do pliku settings.json. Następnie pojawi się monit o ponowne załadowanie okna w celu wprowadzenia zmian.

## <a name="how-to-use-docs-templates"></a>Jak korzystać z szablonów rozszerzenia Docs

Rozszerzenie Docs Article Templates pozwala osobom piszącym w programie VS Code na ściągnięcie szablonu Markdown ze scentralizowanego magazynu i zastosowanie go do pliku. Użycie szablonów może zagwarantować, że w artykułach znajdą się wymagane metadane, że przestrzegane są standardy dotyczące zawartości i tak dalej. Szablony są zarządzane w publicznym repozytorium GitHub jako pliki Markdown.

### <a name="to-apply-a-template-in-vs-code"></a>Aby zastosować szablon w programie VS Code

1. Jeśli nie masz zainstalowanego rozszerzenia Docs Markdown, naciśnij klawisz F1, aby otworzyć paletę poleceń, zacznij wpisywać „template”, aby wprowadzić filtrowanie, a następnie kliknij opcję `Docs: Template`. Jeśli masz zainstalowane rozszerzenie Docs Markdown, możesz skorzystać z palety poleceń lub kliknąć opcję `Alt+M`, aby przywołać menu szybkiego wyboru rozszerzenia Docs Markdown, a następnie wybrać z listy pozycję `Template`.
1. Wybierz żądany szablon z wyświetlonej listy.

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>Aby dodać identyfikator GitHub i/lub alias Microsoft do ustawień programu VS Code

Rozszerzenie szablonów obsługuje trzy dynamiczne pola metadanych: author, ms.author i ms.date. Oznacza to, że jeśli kreator szablonów korzysta z tych pól w nagłówku metadanych szablonu Markdown, zostaną one automatycznie wypełnione w Twoim pliku, gdy zastosujesz szablon, zgodnie z poniższym schematem:

|Metadane  |Wartość|
|----------|---------------|
|author    |Twój identyfikator GitHub, jeśli został określony w pliku ustawień programu VS Code.|
|ms.author |Twój alias Microsoft, jeśli został określony w pliku ustawień programu VS Code. Jeśli nie jesteś pracownikiem firmy Microsoft, pozostaw to pole nieokreślone.|
|ms.date   |Bieżąca data w formacie obsługiwanym przez rozszerzenie Docs, MM/DD/RRRR. Zwróć uwagę, że data nie jest automatycznie aktualizowana podczas dokonywania przez Ciebie kolejnych aktualizacji pliku — musisz aktualizować ją ręcznie, aby wskazać datę odświeżenia datę artykułu.|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>Aby ustawić wartości pól author (identyfikator GitHub) i/lub ms.author (alias Microsoft)

1. W programie VS Code przejdź do pozycji Plik -> Preferencje -> Ustawienia (`CTRL+Comma`).
1. Wybierz pozycję Ustawienia użytkownika, aby zmienić ustawienia dla wszystkich obszarów roboczych programu VS Code, lub pozycję Ustawienia obszaru roboczego, aby zmienić ustawienia tylko dla bieżącego obszaru roboczego.
1. W okienku Ustawienia domyślne z lewej strony znajdź konfigurację rozszerzenia Docs Article Templates, kliknij ikonę ołówka znajdującą się obok żądanego ustawienia, a następnie w obszarze Ustawienia kliknij opcję Zamień.
1. Obok zostanie otwarte okno Ustawienia użytkownika z nowym wpisem na dole.
1. Dodaj swój identyfikator GitHub lub alias Microsoft używany w poczcie e-mail i zapisz plik.
1. Aby zmiany odniosły skutek, może okazać się konieczne zamknięcie i ponowne uruchomienie programu VS Code.
1. Od tej pory, po zastosowaniu szablonu, który wykorzystuje pola dynamiczne, Twój identyfikator GitHub ID i/lub alias Microsoft będą automatycznie wypełniane w nagłówku metadanych.
