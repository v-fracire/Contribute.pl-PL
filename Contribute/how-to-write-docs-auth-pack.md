---
title: Docs Authoring Pack for VS Code
description: W tym artykule opisano pakiet rozszerzenia programu VS Code ułatwiający tworzenie dokumentów w formacie Markdown dla witryny docs.microsoft.com.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: d0d61db2faf88598ecd2c800fb5fbe8df8ec44f5
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/22/2018
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs Authoring Pack for VS Code

Docs Authoring Pack to kolekcja rozszerzeń programu VS Code, które wspomagają tworzenie dokumentów w formacie Markdown dla witryny docs.microsoft.com. Pakiet jest [dostępny w witrynie VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) i zawiera następujące rozszerzenia:

- **DocFx:** zapewnia wersję zapoznawczą języka Markdown dla witryny docs.microsoft.com. Aby uzyskać więcej informacji, zobacz [DocFx](https://marketplace.visualstudio.com/items?itemName=ms-docfx.DocFX).
- **markdownlint:** popularny linter języka Markdown autorstwa Davida Ansona, który pomaga w korzystaniu z najlepszych rozwiązań języka Markdown. Aby uzyskać więcej informacji, zobacz [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint).
- **Docs Markdown:** zapewnia wsparcie przy tworzeniu zawartości witryny docs.microsoft.com w języku Markdown w systemie Open Publishing System (OPS), w tym zapewnia podstawową obsługę języka Markdown oraz obsługę niestandardowej składni języka Markdown w systemie OPS. W pozostałej części tego tematu opisano rozszerzenie Docs Markdown.

## <a name="prerequisites-and-assumptions"></a>Wymagania wstępne i założenia

Aby precyzyjnie wstawiać linki względne, obrazy i inną zawartość osadzoną przy użyciu rozszerzenia Docs Markdown, musisz mieć obszar roboczy VS Code w zakresie folderu głównego sklonowanego repozytorium OPS.

Niektóre przypadki składni obsługiwanej przez rozszerzenie, np. alerty i fragmenty kodu, są niestandardowymi elementami języka Markdown dla systemu OPS i nie będą prawidłowo renderowane, chyba że zostaną opublikowane za pośrednictwem systemu OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Sposób użycia rozszerzenia Docs Markdown

Aby uzyskać dostęp do menu rozszerzenia Docs Markdown, wpisz `ALT+M`. Możesz kliknąć lub użyć strzałek w górę/w dół, aby wybrać żądaną funkcję, lub wpisać tekst, aby rozpocząć filtrowanie, a następnie nacisnąć przycisk `ENTER`, kiedy żądana funkcja zostanie podświetlona w menu. Dostępne są następujące funkcje:

|Funkcja     |Polecenie             |Opis           |
|-------------|--------------------|----------------------|
|Pogrubienie         |`formatBold`        |Formatuje tekst jako **pogrubiony**.|
|Kursywa       |`formatItalic`      |Formatuje tekst jako *kursywę*.|
|Kod         |`formatCode`        |W przypadku zaznaczenia jednego wiersza lub mniej formatuje tekst jako `inline code`.<br><br>Jeśli zostanie zaznaczonych wiele wierszy, funkcja sformatuje je jako odgrodzony blok kodu oraz umożliwi opcjonalne wybranie języka programowania obsługiwanego przez system OPS.|
|Alert        |`insertAlert`       |Wstawia alerty Uwaga, Ważne, Ostrzeżenie lub Porada.<br><br>Wybierz opcję Alert z menu, a następnie wybierz typ alertu. Jeśli wcześniej zaznaczono tekst, zostanie on otoczony składnią wybranego alertu. Jeśli nie wybrano tekstu, zostanie dodany nowy alert z tekstem zastępczym.|
|Lista numerowana|`insertNumberedList` |Wstawia nową listę numerowaną.<br><br> Jeśli zaznaczono wiele wierszy, każdy z nich będzie pozycją na liście. Zauważ, że listy numerowane są wyświetlane w języku Markdown jako same numery 1, ale będą renderowane w witrynie docs.microsoft.com jako kolejne liczby lub, w przypadku list zagnieżdżonych, litery. Aby utworzyć zagnieżdżoną listę numerowaną, naciśnij klawisz TAB z pozycji listy nadrzędnej.|
|Lista punktowana|`insertBulletedList` |Wstawia nową listę punktowaną.|
|Tabela        |`insertTable`        |Wstawia strukturę tabeli języka Markdown.<br><br>Po wybraniu polecenia tabeli określ liczbę kolumn i wierszy w formacie kolumny:wiersze, np. 3:4. Zauważ, że maksymalna liczba kolumn, które możesz określić za pośrednictwem rozszerzenia, to 5 — jest to też zalecane maksimum zapewniające czytelność.|
|Link         |`selectLinkType`      |Wstawia link. Po wybraniu tego polecenia zostanie wyświetlone następujące podmenu.<br><br>`External`: link do strony internetowej według identyfikatora URI. Musi zawierać ciąg „http” lub „https”.<br>`Internal`: wstaw link względny do innego pliku w tym samym repozytorium. Po wybraniu tej opcji wpisz tekst w oknie polecenia, aby filtrować pliki według nazwy, a następnie wybierz żądany plik. <br>`Bookmark in this file`: wybierz z listy nagłówków w bieżącym pliku, aby wstawić prawidłowo sformatowaną zakładkę.<br>`Bookmark in another file`: najpierw odfiltruj według nazwy pliku i wybierz plik do połączenia, a następnie wybierz odpowiedni nagłówek w wybranym pliku.|
|Obraz        |`insertImage`     |Wpisz tekst alternatywny (wymagany na potrzeby ułatwień dostępu) i wybierz go, a następnie wywołaj to polecenie, aby odfiltrować listę obsługiwanych plików obrazów w repozytorium i wybrać żądany plik. Jeśli jeszcze nie wybrano tekstu alternatywnego podczas wywoływania tego polecenia, pojawi się monit o wprowadzenie tekstu, zanim będzie można wybrać plik obrazu.|
|Uwzględnij      |`insertInclude`   |Znajdź plik do osadzenia w bieżącym pliku.|
|Fragment kodu      |`insertSnippet`   |Znajdź fragment kodu w repozytorium, aby osadzić go w bieżącym pliku.|
|Filmy        |`insertVideo`     |Dodaj osadzone wideo.|
|Podgląd      |`previewTopic`    |Wyświetl podgląd aktywnego tematu w oknie obok siebie przy użyciu rozszerzenia DocFX.  Jeśli rozszerzenie DocFX nie zostało zainstalowane lub jest zainstalowane i wyłączone, temat nie zostanie wyrenderowany.


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

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>Sposób wyświetlania starszego paska narzędzi „Gauntlet”

Byli użytkownicy kodu rozszerzenia o nazwie „Gauntlet” zauważą, że pasek narzędzi tworzenia nie pojawia się już u dołu okna programu VS Code, kiedy zostanie zainstalowane rozszerzenie Docs Markdown. Dzieje się tak, ponieważ pasek narzędzi zajmował dużo miejsca na pasku stanu programu VS Code i nie korzystał z najlepszych rozwiązań środowiska użytkownika rozszerzenia, więc został uznany za przestarzały w nowym rozszerzeniu. Jednak możesz też opcjonalnie wyświetlić pasek narzędzi, aktualizując plik settings.json programu VS Code w następujący sposób:

1. W programie VS Code przejdź do pozycji Plik -> Preferencje -> Ustawienia (`CTRL+Comma`).
1. Wybierz pozycję Ustawienia użytkownika, aby zmienić ustawienia dla wszystkich obszarów roboczych programu VS Code, lub pozycję Ustawienia obszaru roboczego, aby zmienić ustawienia tylko dla bieżącego obszaru roboczego.
1. W okienku Ustawienia domyślne znajdź pozycję Konfiguracja rozszerzenia Docs Authoring i wybierz ikonę ołówka obok żądanego ustawienia. Następnie zobaczysz monit o wybranie opcji `true` lub `false`. Po dokonaniu wyboru program VS Code automatycznie doda wartość do pliku settings.json. Następnie pojawi się monit o ponowne załadowanie okna w celu wprowadzenia zmian.

## <a name="known-issues"></a>Znane problemy

- DocFX — wersja zapoznawcza: w systemach MacOS i Linux wersja zapoznawcza rozszerzenia DocFX nie uruchamia prawidłowo podglądu (domyślnie podgląd jest przekierowywany do podglądu języka Markdown programu VS Code dla tych platform).
- DocFX — wersja zapoznawcza: na wszystkich platformach niektóre przypadki składni, np. linki xref (odsyłacze) do interfejsów API, nie są renderowane prawidłowo w podglądzie. W niektórych przypadkach powoduje to powstanie luk w zawartości.
- Zakładki zewnętrzne: w systemie Linux lista plików jest wyświetlana, ale nie ma widocznych nagłówków do wybrania.
- Uwzględnij: w systemie Linux lista plików jest wyświetlana, ale po dokonaniu wyboru nie zostaje dodany link.
