---
title: Instalowanie narzędzi do tworzenia zawartości
description: Ten artykuł zawiera informacje przydatne podczas pobierania i instalowania narzędzi klienta potrzebnych do programu Git oraz edytowania plików ze znacznikami języka Markdown.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 01/04/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 0ca942e557640db1ba36d3f5b1064656ed3dea8d
ms.sourcegitcommit: 3ec397fab57ea582edb03a59609f62d886410ee8
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/28/2018
---
# <a name="install-content-authoring-tools"></a>Instalowanie narzędzi do tworzenia zawartości

W tym artykule opisano kroki interaktywnego instalowania narzędzi klienta Git i Visual Studio Code.
> [!div class="checklist"]
> * Instalowanie programu [Git dla systemu Windows](https://git-scm.com/download/win)
> * [Instalowanie narzędzia Visual Studio Code](https://code.visualstudio.com/)

>[!IMPORTANT]
> Jeśli wprowadzasz tylko drobne zmiany w artykule, *nie musisz* wykonywać kroków opisanych w tym artykule i możesz przejść bezpośrednio do [przepływu pracy dla drobnych zmian](index.md#quick-edits-to-existing-documents).
>
> Zaleca się, aby kroki te wykonali najważniejsi współautorzy. Pozwoli to na użycie [przepływu pracy dla znacznych/długofalowych zmian](how-to-write-workflows-major.md). Nawet jeśli masz uprawnienia do zapisu w repozytorium głównym, *zdecydowanie zalecamy rozwidlenie i sklonowanie repozytorium*, dzięki czemu będziesz mieć uprawnienia do odczytu/zapisu. Pozwoli to na przechowywanie proponowanych zmian w Twoim rozwidleniu. W tym przewodniku założono, że czynności te zostały wykonane.

## <a name="install-git-client-tools-on-windows"></a>Instalowanie narzędzi klienckich usługi Git w systemie Windows

 Zainstaluj najnowszą wersję [narzędzi klienckich dla systemu Git organizacji Software Freedom Conservancy](https://git-scm.com/download/). Ta instalacja obejmuje system kontroli wersji Git oraz powłokę Git Bash, czyli aplikację wiersza polecenia służącą do interakcji z lokalnym repozytorium Git.

Jeśli wolisz graficzny interfejs użytkownika od interfejsu wiersza polecenia, zobacz [stronę z informacjami o dostępnych klientach z graficznym interfejsem użytkownika organizacji Software Freedom Conservancy](https://git-scm.com/downloads/guis) i zapoznaj się z takimi popularnymi rozwiązaniami, jak [program GitHub Desktop dla usługi GitHub](https://desktop.github.com/) lub [edytor Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx).

Postępuj zgodnie z instrukcjami dla wybranego klienta dotyczącymi instalacji i konfiguracji.

Z następnego artykułu dowiesz się, jak wykonać [konfigurowanie lokalnego repozytorium Git](get-started-setup-local.md).

   Dodatkowe zasoby dotyczące systemu Git są dostępne w tym miejscu: [Terminologia Git](https://help.github.com/articles/github-glossary) | [Podstawy Git](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Szkolenia dotyczące Git i GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>Zrozumienie edytorów języka Markdown

Markdown to prosty język znaczników, łatwy do odczytywania oraz do nauczenia się. Z tego powodu stał się on szybko standardem w branży. W celu pisania artykułów w języku Markdown dobrze jest najpierw pobrać i zainstalować edytor tego języka.  Preferowanym narzędziem do edycji języka Markdown w firmie Microsoft jest [Visual Studio Code](https://code.visualstudio.com/). Innym popularnym narzędziem do edytowania języka Markdown jest [Atom](https://atom.io).

Teksty w języku Markdown są zapisywane w plikach z rozszerzeniem .md.

Dodatkowe szczegółowe informacje dotyczące pisania w języku Markdown, m.in. podstawowe informacje dotyczące języka Markdown oraz informacje o funkcjach obsługiwanych przez niestandardowe rozszerzenia języka Markdown na platformie OPS, zostały omówione w artykule [Jak używać języka Markdown](how-to-write-use-markdown.md).

## <a name="visual-studio-code"></a>Visual Studio Code

Narzędzie [Visual Studio Code](https://code.visualstudio.com/), znane także jako VS Code, to lekki edytor, który działa w systemach Windows, Linux i na komputerach Mac. Obejmuje integrację z usługą Git oraz obsługę rozszerzeń.

Pobierz i zainstaluj program [VS Code](https://code.visualstudio.com/). Strona główna programu VS Code powinna prawidłowo wykryć system operacyjny.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> Aby uruchomić program VS Code i otworzyć bieżący folder, uruchom polecenie `code .` w wierszu polecenia lub powłoce bash. Jeśli bieżący folder jest częścią lokalnego repozytorium usługi Git, integracja z usługą GitHub automatycznie pojawi się w programie Visual Studio Code.

## <a name="next-steps"></a>Kolejne kroki

Teraz możesz przystąpić do [konfigurowania lokalnego repozytorium Git](get-started-setup-local.md).
